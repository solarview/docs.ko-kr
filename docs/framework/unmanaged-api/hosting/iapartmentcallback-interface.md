---
title: "IApartmentCallback 인터페이스"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: IApartmentCallback
api_location: mscoree.dll
api_type: COM
f1_keywords: IApartmentCallback
helpviewer_keywords: IApartmentCallback interface [.NET Framework hosting]
ms.assetid: 57c33c58-bf0b-4533-b569-e6a682d02cba
topic_type: apiref
caps.latest.revision: "9"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 5d2f2ea73da2273ff6f0abb725ec3e3fb8ca79ca
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="iapartmentcallback-interface"></a><span data-ttu-id="2a3b7-102">IApartmentCallback 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2a3b7-102">IApartmentCallback Interface</span></span>
<span data-ttu-id="2a3b7-103">콜백을 아파트 내에서 수행 하기 위한 메서드를 제공 합니다.</span><span class="sxs-lookup"><span data-stu-id="2a3b7-103">Provides methods for making callbacks within an apartment.</span></span> <span data-ttu-id="2a3b7-104">*아파트* 는 같은 스레드 액세스 요구 사항을 공유 하는 개체에 대 한 프로세스 내에서 논리적 컨테이너입니다.</span><span class="sxs-lookup"><span data-stu-id="2a3b7-104">An *apartment* is a logical container within a process for objects that share the same thread access requirements.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="2a3b7-105">메서드</span><span class="sxs-lookup"><span data-stu-id="2a3b7-105">Methods</span></span>  
  
|<span data-ttu-id="2a3b7-106">메서드</span><span class="sxs-lookup"><span data-stu-id="2a3b7-106">Method</span></span>|<span data-ttu-id="2a3b7-107">설명</span><span class="sxs-lookup"><span data-stu-id="2a3b7-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="2a3b7-108">DoCallback 메서드</span><span class="sxs-lookup"><span data-stu-id="2a3b7-108">DoCallback Method</span></span>](../../../../docs/framework/unmanaged-api/hosting/iapartmentcallback-docallback-method.md)|<span data-ttu-id="2a3b7-109">아파트 내에서 지정된 된 함수를 실행합니다.</span><span class="sxs-lookup"><span data-stu-id="2a3b7-109">Executes the specified function within an apartment.</span></span>|  
  
## <a name="requirements"></a><span data-ttu-id="2a3b7-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="2a3b7-110">Requirements</span></span>  
 <span data-ttu-id="2a3b7-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="2a3b7-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="2a3b7-112">**헤더:** MSCorEE.h</span><span class="sxs-lookup"><span data-stu-id="2a3b7-112">**Header:** MSCorEE.h</span></span>  
  
 <span data-ttu-id="2a3b7-113">**라이브러리:** MSCorEE.dll에 리소스로 포함</span><span class="sxs-lookup"><span data-stu-id="2a3b7-113">**Library:** Included as a resource in MSCorEE.dll</span></span>  
  
 <span data-ttu-id="2a3b7-114">**.NET framework 버전:**[!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="2a3b7-114">**.NET Framework Versions:** [!INCLUDE[net_current_v20plus](../../../../includes/net-current-v20plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="2a3b7-115">참고 항목</span><span class="sxs-lookup"><span data-stu-id="2a3b7-115">See Also</span></span>  
 [<span data-ttu-id="2a3b7-116">호스팅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="2a3b7-116">Hosting Interfaces</span></span>](../../../../docs/framework/unmanaged-api/hosting/hosting-interfaces.md)