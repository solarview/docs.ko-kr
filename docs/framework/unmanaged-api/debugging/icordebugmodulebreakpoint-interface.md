---
title: ICorDebugModuleBreakpoint Interface1
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugModuleBreakpoint
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugModuleBreakpoint
helpviewer_keywords: ICorDebugModuleBreakpoint interface [.NET Framework debugging]
ms.assetid: 34667162-f314-475f-ae1b-ce9cb0fcbb83
topic_type: apiref
caps.latest.revision: "13"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 3e3937c6c0baef4cc927b5c5d789826c70beebf2
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugmodulebreakpoint-interface1"></a><span data-ttu-id="8a69d-102">ICorDebugModuleBreakpoint Interface1</span><span class="sxs-lookup"><span data-stu-id="8a69d-102">ICorDebugModuleBreakpoint Interface1</span></span>
<span data-ttu-id="8a69d-103">특정 모듈에 대 한 액세스를 제공합니다.</span><span class="sxs-lookup"><span data-stu-id="8a69d-103">Provides access to specific modules.</span></span> <span data-ttu-id="8a69d-104">이 인터페이스는 ICorDebugBreakpoint 인터페이스의 서브 클래스입니다.</span><span class="sxs-lookup"><span data-stu-id="8a69d-104">This interface is a subclass of the ICorDebugBreakpoint interface.</span></span>  
  
## <a name="methods"></a><span data-ttu-id="8a69d-105">메서드</span><span class="sxs-lookup"><span data-stu-id="8a69d-105">Methods</span></span>  
  
|<span data-ttu-id="8a69d-106">메서드</span><span class="sxs-lookup"><span data-stu-id="8a69d-106">Method</span></span>|<span data-ttu-id="8a69d-107">설명</span><span class="sxs-lookup"><span data-stu-id="8a69d-107">Description</span></span>|  
|------------|-----------------|  
|[<span data-ttu-id="8a69d-108">GetModule 메서드</span><span class="sxs-lookup"><span data-stu-id="8a69d-108">GetModule Method</span></span>](../../../../docs/framework/unmanaged-api/debugging/icordebugmodulebreakpoint-getmodule-method.md)|<span data-ttu-id="8a69d-109">이 중단점이 설정 된 모듈을 참조 하는 ICorDebugModule에 대 한 인터페이스 포인터를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="8a69d-109">Gets an interface pointer to an ICorDebugModule that references the module where this breakpoint is set.</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="8a69d-110">설명</span><span class="sxs-lookup"><span data-stu-id="8a69d-110">Remarks</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="8a69d-111">이 인터페이스는 크로스 시스템 또는 크로스 프로세스 원격 호출을 지원하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="8a69d-111">This interface does not support being called remotely, either cross-machine or cross-process.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="8a69d-112">요구 사항</span><span class="sxs-lookup"><span data-stu-id="8a69d-112">Requirements</span></span>  
 <span data-ttu-id="8a69d-113">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="8a69d-113">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="8a69d-114">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="8a69d-114">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="8a69d-115">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="8a69d-115">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="8a69d-116">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8a69d-116">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8a69d-117">참고 항목</span><span class="sxs-lookup"><span data-stu-id="8a69d-117">See Also</span></span>  
 [<span data-ttu-id="8a69d-118">디버깅 인터페이스</span><span class="sxs-lookup"><span data-stu-id="8a69d-118">Debugging Interfaces</span></span>](../../../../docs/framework/unmanaged-api/debugging/debugging-interfaces.md)