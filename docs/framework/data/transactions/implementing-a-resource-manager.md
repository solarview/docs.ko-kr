---
title: 리소스 관리자 구현
ms.date: 03/30/2017
ms.assetid: d5c153f6-4419-49e3-a5f1-a50ae4c81bf3
ms.openlocfilehash: f3e29dae095fbe56181cf7b67787c1044efa07ae
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
ms.locfileid: "33363265"
---
# <a name="implementing-a-resource-manager"></a>리소스 관리자 구현
트랜잭션에 사용되는 각 리소스는 리소스 관리자에 의해 관리되고, RM의 작업은 트랜잭션 관리자에 의해 조정됩니다. 리소스 관리자는 트랜잭션 관리자와 함께 작업하여 응용 프로그램에 원자성 및 격리를 보장합니다. Microsoft SQL Server, 지속적인 메시지 큐, 메모리 내 해시 테이블 등이 모두 리소스 관리자의 예입니다.  
  
 리소스 관리자는 지속적인 데이터나 일시적인 데이터를 관리합니다. 리소스 관리자의 지속성(또는 일시성)은 리소스 관리자가 오류 복구를 지원하는지 여부를 나타냅니다. 오류 복구를 지원하는 경우 리소스 관리자는 Phase1(준비) 중에 지속적인 저장소에 데이터를 저장하여 리소스 관리자가 작동하지 않으면 복구 시 트랜잭션에 다시 참여하고 트랜잭션 관리자에서 받은 알림을 기반으로 적절한 작업을 수행할 수 있도록 합니다. 일반적으로 일시적인 리소스 관리자는 메모리 내 데이터 구조(예: 트랜잭션된 메모리 내 해시 테이블) 같은 일시적인 리소스를 관리하고 지속적인 리소스 관리자는 보다 지속적인 백업 저장소(예: 백업 저장소가 디스크인 데이터베이스)가 있는 리소스를 관리합니다.  
  
 리소스가 트랜잭션에 참가하려면 트랜잭션에 참여해야 합니다. <xref:System.Transactions.Transaction> 클래스 이름이로 시작 하는 메서드 집합을 정의 **Enlist** 이 기능을 제공 합니다. 서로 다른 **Enlist** 다양 한 유형의 리소스 관리자를 가질 수 있는 인 리스트 먼 트에 해당 하는 방법입니다. 특히 일시적인 리소스에는 <xref:System.Transactions.Transaction.EnlistVolatile%2A> 메서드를 사용하고 지속적인 리소스에는 <xref:System.Transactions.Transaction.EnlistDurable%2A> 메서드를 사용합니다. 단순성을 위해 리소스의 지속성 지원을 기반으로 <xref:System.Transactions.Transaction.EnlistDurable%2A> 또는 <xref:System.Transactions.Transaction.EnlistVolatile%2A> 메서드를 사용할지 결정한 후 리소스 관리자에 대한 <xref:System.Transactions.IEnlistmentNotification> 인터페이스를 구현하여 2PC(2단계 커밋)에 참가할 리소스를 참여시켜야 합니다. 2PC에 대 한 자세한 내용은 참조 하십시오. [단일 단계 및 다중 단계에서 트랜잭션 커밋](../../../../docs/framework/data/transactions/committing-a-transaction-in-single-phase-and-multi-phase.md)합니다.  
  
 인리스트먼트를 통해 리소스 관리자는 트랜잭션이 커밋 또는 중단될 때 트랜잭션 관리자로부터 콜백을 가져옵니다. 인리스트먼트당 하나의 <xref:System.Transactions.IEnlistmentNotification> 인스턴스가 있습니다. 일반적으로 트랜잭션당 하나의 인리스트먼트가 있지만 리소스 관리자는 동일한 트랜잭션에 여러 번 참여하도록 선택할 수 있습니다.  
  
 인리스트먼트 후에 리소스 관리자는 트랜잭션의 요청에 응답합니다. 지속적인 리소스 관리자는 관리하는 리소스에 대한 트랜잭션의 작업을 취소하거나 다시 실행할 수 있는 충분한 정보를 저장합니다. 이 작업을 수행하는 여러 가지 방법이 있으며, 두 가지 일반적인 기술은 데이터 버전 유지 또는 변경 내용 로그 유지입니다.  
  
 응용 프로그램이 트랜잭션을 커밋하면 트랜잭션 관리자가 2단계 커밋 프로토콜을 시작합니다. 트랜잭션 관리자는 먼저 참여하는 각 리소스 관리자에게 트랜잭션을 커밋할 준비가 되었는지 묻습니다. 리소스 관리자가 커밋을 준비해야 합니다. 리소스 관리자는 트랜잭션을 커밋 또는 중단할 준비를 합니다.  
  
 준비 단계 중에 지속적인 리소스 관리자는 이전 데이터와 새 데이터를 안정적인 저장소에 기록하여 시스템이 실패한 경우에도 리소스 관리자가 복구할 수 있도록 합니다. 준비할 수 있는 경우 리소스 관리자는 트랜잭션을 커밋 또는 중단할지에 대한 응답을 트랜잭션 관리자에게 알립니다. 준비하지 못했다고 보고하는 리소스 관리자가 하나라도 있으면 트랜잭션 관리자는 각 리소스 관리자에게 롤백 명령을 보내고 응용 프로그램에 커밋 실패를 나타냅니다.  
  
 준비가 되면 리소스 관리자는 2단계에서 트랜잭션 관리자로부터 커밋 또는 중단 콜백을 가져올 때까지 기다려야 합니다. 일반적으로 1초 미만의 시간에 전체 준비 및 커밋 프로토콜이 완료됩니다. 시스템 또는 통신 오류가 있는 경우 커밋 또는 중단 알림이 몇 분 또는 몇 시간동안 도착하지 않을 수도 있습니다. 이 기간 중에 리소스 관리자는 트랜잭션의 결과에 대해 확신하지 못하며 트랜잭션이 커밋 또는 중단되었는지 알 수 없습니다. 리소스 관리자는 트랜잭션에 대해 확신하지 못하지만 트랜잭션 잠금을 유지하고 이러한 변경 내용을 다른 트랜잭션에서 격리하여 수정된 데이터를 유지합니다.  
  
 리소스 관리자가 실패하면 오류 전에 준비 또는 커밋된 트랜잭션을 제외하고 참여하는 모든 트랜잭션이 중단됩니다. 지속적인 리소스 관리자는 다시 시작될 경우 준비 단계에서 작성된 준비 정보를 검색하여 관리하는 리소스의 커밋된 상태를 다시 생성하고 이러한 트랜잭션을 적절하게 커밋 또는 중단합니다.  
  
 요약하면 2단계 커밋 프로토콜과 리소스 관리자가 결합되어 트랜잭션의 원자성과 지속성을 유지합니다.  
  
 <xref:System.Transactions.Transaction> 클래스는 PSPE(승격 가능한 단일 단계 인리스트먼트)를 참여시키는 <xref:System.Transactions.Transaction.EnlistPromotableSinglePhase%2A> 메서드도 제공합니다. 이 메서드를 사용하면 지속적인 RM(리소스 관리자)이 트랜잭션을 호스팅하고 "소유"할 수 있으며, 필요한 경우 MSDTC에서 관리하도록 나중에 해당 트랜잭션을 에스컬레이션할 수 있습니다. 이 대 한 자세한 내용은 참조 하십시오. [단일 단계 커밋 및 승격 가능한 단일 단계 알림을 사용 하 여 최적화](../../../../docs/framework/data/transactions/optimization-spc-and-promotable-spn.md)합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 일반적으로 리소스 관리자가 수행하는 단계에 대해서는 다음 항목에서 간략하게 설명합니다.  
  
 [리소스를 트랜잭션에 참가 요소로 등록](../../../../docs/framework/data/transactions/enlisting-resources-as-participants-in-a-transaction.md)  
  
 지속적인 리소스나 일시적인 리소스가 트랜잭션에 참여할 수 있는 방법에 대해 설명합니다.  
  
 [단일 단계 및 다단계 트랜잭션 커밋](../../../../docs/framework/data/transactions/committing-a-transaction-in-single-phase-and-multi-phase.md)  
  
 리소스 관리자가 커밋 알림에 응답하고 커밋을 준비하는 방법에 대해 설명합니다.  
  
 [복구 수행](../../../../docs/framework/data/transactions/performing-recovery.md)  
  
 지속적인 리소스 관리자가 오류를 복구하는 방법에 대해 설명합니다.  
  
 [리소스 액세스의 보안 신뢰 수준](../../../../docs/framework/data/transactions/security-trust-levels-in-accessing-resources.md)  
  
 System.Transactions의 세 가지 신뢰 수준이 <xref:System.Transactions>에서 노출하는 리소스 형식에 대한 액세스를 제한하는 방법에 대해 설명합니다.  
  
 [단일 단계 커밋 및 승격 가능한 단일 단계 알림을 사용한 최적화](../../../../docs/framework/data/transactions/optimization-spc-and-promotable-spn.md)  
  
 리소스 관리자 구현에서 사용할 수 있는 최적화 방법에 대해 설명합니다.
