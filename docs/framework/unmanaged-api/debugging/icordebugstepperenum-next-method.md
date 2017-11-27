---
title: "ICorDebugStepperEnum::Next 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStepperEnum.Next
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStepperEnum::Next
helpviewer_keywords:
- Next method, ICorDebugStepperEnum interface [.NET Framework debugging]
- ICorDebugStepperEnum::Next method [.NET Framework debugging]
ms.assetid: d0ea0f30-e8d2-48b0-8477-e1a029ceb4dd
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: a0ad2e3361387875178e8261fad4159a3064da1b
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugstepperenumnext-method"></a><span data-ttu-id="4481e-102">ICorDebugStepperEnum::Next 메서드</span><span class="sxs-lookup"><span data-stu-id="4481e-102">ICorDebugStepperEnum::Next Method</span></span>
<span data-ttu-id="4481e-103">현재 위치부터 시작 하는 열거형에서 지정 된 ICorDebugStepper 인스턴스 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="4481e-103">Gets the specified number of ICorDebugStepper instances from the enumeration, starting at the current position.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="4481e-104">구문</span><span class="sxs-lookup"><span data-stu-id="4481e-104">Syntax</span></span>  
  
```  
HRESULT Next(  
    [in] ULONG  celt,  
    [out, size_is(celt), length_is(*pceltFetched)]  
        ICorDebugStepper *steppers[],  
    [out] ULONG *pceltFetched  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="4481e-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="4481e-105">Parameters</span></span>  
 `celt`  
 <span data-ttu-id="4481e-106">[in] 수가 `ICorDebugStepper` 인스턴스를 검색할 수 있습니다.</span><span class="sxs-lookup"><span data-stu-id="4481e-106">[in] The number of `ICorDebugStepper` instances to be retrieved.</span></span>  
  
 `steppers`  
 <span data-ttu-id="4481e-107">[out] 각각 가리키는 포인터의 배열은 `ICorDebugStepper` 개체입니다.</span><span class="sxs-lookup"><span data-stu-id="4481e-107">[out] An array of pointers, each of which points to an `ICorDebugStepper` object.</span></span>  
  
 `pceltFetched`  
 <span data-ttu-id="4481e-108">[out] 수에 대 한 포인터 `ICorDebugStepper` 실제로 반환 된 인스턴스.</span><span class="sxs-lookup"><span data-stu-id="4481e-108">[out] Pointer to the number of `ICorDebugStepper` instances actually returned.</span></span> <span data-ttu-id="4481e-109">이 값은 null 일 수 있으면 `celt` 하나입니다.</span><span class="sxs-lookup"><span data-stu-id="4481e-109">This value may be null if `celt` is one.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="4481e-110">요구 사항</span><span class="sxs-lookup"><span data-stu-id="4481e-110">Requirements</span></span>  
 <span data-ttu-id="4481e-111">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="4481e-111">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="4481e-112">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="4481e-112">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="4481e-113">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="4481e-113">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="4481e-114">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="4481e-114">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>