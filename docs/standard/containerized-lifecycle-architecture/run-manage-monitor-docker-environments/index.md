---
title: Docker 프로덕션 환경 실행, 관리 및 모니터링
description: Microsoft 플랫폼 및 도구를 사용하여 컨테이너화된 Docker 응용 프로그램 수명 주기
author: CESARDELATORRE
ms.author: wiwagn
ms.date: 09/22/2017
ms.openlocfilehash: 2f29119e102bbb62e96da6b3c00f9c53c0a270a2
ms.sourcegitcommit: ccd8c36b0d74d99291d41aceb14cf98d74dc9d2b
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/10/2018
ms.locfileid: "53130952"
---
# <a name="run-manage-and-monitor-docker-production-environments"></a>Docker 프로덕션 환경 실행, 관리 및 모니터링

비전: 엔터프라이즈 응용 프로그램 고가용성 및 높은 확장성을 사용 하 여 실행 해야 합니다. IT 운영 환경 및 응용 프로그램 자체 관리 및 모니터링 하는 일을 할 수 해야 합니다.

컨테이너화된 Docker 응용 프로그램 수명 주기의 이 마지막 단계에서는 확장 가능한 고가용성(HA) 프로덕션 환경에서 응용 프로그램을 실행, 관리 및 모니터링할 수 있는 방법을 중점적으로 살펴봅니다.

프로덕션 환경(인프라 아키텍처 및 플랫폼 기술)에서 컨테이너화된 응용 프로그램을 실행하는 방법은 이 전자책의 챕터 1에서 살펴본 선택된 아키텍처와 개발 플랫폼에 따라 완전히 달라지며, 매우 깊은 연관성이 있습니다. 이 챕터에서는 고확장성, HA를 지원하는 분산 응용 프로그램을 효과적으로 실행하는 데 사용할 수 있는 Microsoft 및 다른 공급업체의 특정 제품 및 기술을 살펴보고, 이러한 제품 및 기술을 관리하고 모니터링하는 방법을 IT 관점에서 살펴봅니다.

>[!div class="step-by-step"]
>[이전](../docker-devops-workflow/docker-application-outer-loop-devops-workflow.md)
>[다음](run-microservices-based-applications-in-production.md)