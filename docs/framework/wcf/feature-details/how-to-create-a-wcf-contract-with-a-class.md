---
title: '방법: 클래스를 사용 하 여 Windows Communication Foundation 계약 만들기'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
ms.assetid: 1ad69393-3915-4e7f-9b91-b6fc59c6f5ba
ms.openlocfilehash: 90661b4e8f13f0aa3e613bd99bf57dfacdc1eeae
ms.sourcegitcommit: 0888d7b24f475c346a3f444de8d83ec1ca7cd234
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2018
ms.locfileid: "53773616"
---
# <a name="how-to-create-a-windows-communication-foundation-contract-with-a-class"></a>방법: 클래스를 사용 하 여 Windows Communication Foundation 계약 만들기
Windows Communication Foundation (WCF) 계약을 만드는 인터페이스를 사용 하는 것이 좋습니다. 자세한 내용은 [방법: 서비스 계약 정의](../../../../docs/framework/wcf/how-to-define-a-wcf-service-contract.md)합니다. 또는 다음에 요약한 대로 클래스를 만든 후 <xref:System.ServiceModel.ServiceContractAttribute> 특성을 직접 해당 클래스에 적용하고 <xref:System.ServiceModel.OperationContractAttribute> 특성을 계약의 일부인 클래스의 각 메서드에 적용합니다.  
  
> [!WARNING]
>  `[ServiceContract]` 및 `[ServiceContractAttribute]` 에 대해 동일한 작업을 수행합니다. 동일한 작업에 대 한 참인 `[OperationContract]` 고 `[OperationContractAttribute]`입니다. 각 경우 전자가 후자 보다 빠릅니다.  
  
 서비스 계약에 대 한 자세한 내용은 참조 하세요. [Designing Service Contracts](../../../../docs/framework/wcf/designing-service-contracts.md)합니다.  
  
### <a name="creating-a-windows-communication-foundation-contract-with-a-class"></a>클래스를 사용하여 Windows Communication Foundation 계약 만들기  
  
1.  Visual Basic을 사용 하 여 새 클래스를 만듭니다 C#, 또는 기타 공용 언어 런타임 언어입니다.  
  
2.  이 클래스에 <xref:System.ServiceModel.ServiceContractAttribute> 클래스를 적용합니다.  
  
3.  클래스에 메서드를 만듭니다.  
  
4.  적용 된 <xref:System.ServiceModel.OperationContractAttribute> 고 공개 WCF 계약의 일부로 노출 해야 하는 각 메서드에 클래스입니다.  
  
## <a name="example"></a>예제  
 다음 코드 예제에서는 서비스 계약을 정의하는 클래스를 보여 줍니다.  
  
 [!code-csharp[c_HowTo_CreateContractWithClass#1](../../../../samples/snippets/csharp/VS_Snippets_CFX/c_howto_createcontractwithclass/cs/source.cs#1)]
 [!code-vb[c_HowTo_CreateContractWithClass#1](../../../../samples/snippets/visualbasic/VS_Snippets_CFX/c_howto_createcontractwithclass/vb/source.vb#1)]  
  
 <xref:System.ServiceModel.OperationContractAttribute> 클래스가 적용된 메서드는 기본적으로 요청-회신 메시지 패턴을 사용합니다. 이 메시지 패턴에 대 한 자세한 내용은 참조 하세요. [방법: 요청-회신 계약을 만들려면](../../../../docs/framework/wcf/feature-details/how-to-create-a-request-reply-contract.md)합니다. 특성의 속성을 설정하여 다른 메시지 패턴을 만들고 사용할 수도 있습니다. 더 많은 예제를 참조 하세요. [방법: 단방향 계약을 만들려면](../../../../docs/framework/wcf/feature-details/how-to-create-a-one-way-contract.md) 고 [방법: 이중 계약 만들기](../../../../docs/framework/wcf/feature-details/how-to-create-a-duplex-contract.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.ServiceModel.ServiceContractAttribute>  
 <xref:System.ServiceModel.OperationContractAttribute>
