---
title: "ICorDebugEnum::GetCount 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugEnum.GetCount
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugEnum::GetCount
helpviewer_keywords:
- ICorDebugEnum::GetCount method [.NET Framework debugging]
- GetCount method, ICorDebugEnum interface [.NET Framework debugging]
ms.assetid: d8a74304-1cb2-4977-a21d-e1af48c563ff
topic_type: apiref
caps.latest.revision: "11"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: bca3631f9c7a8f6ec3d145f8573241642cb1b1c0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugenumgetcount-method"></a><span data-ttu-id="db8b1-102">ICorDebugEnum::GetCount 메서드</span><span class="sxs-lookup"><span data-stu-id="db8b1-102">ICorDebugEnum::GetCount Method</span></span>
<span data-ttu-id="db8b1-103">열거형에서 항목의 수를 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="db8b1-103">Gets the number of items in the enumeration.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="db8b1-104">구문</span><span class="sxs-lookup"><span data-stu-id="db8b1-104">Syntax</span></span>  
  
```  
HRESULT GetCount (  
    [out] ULONG *pcelt  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="db8b1-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="db8b1-105">Parameters</span></span>  
 `pcelt`  
 <span data-ttu-id="db8b1-106">[out] 열거형에는 항목 수에 대 한 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="db8b1-106">[out] A pointer to the number of items in the enumeration.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="db8b1-107">요구 사항</span><span class="sxs-lookup"><span data-stu-id="db8b1-107">Requirements</span></span>  
 <span data-ttu-id="db8b1-108">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="db8b1-108">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="db8b1-109">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="db8b1-109">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="db8b1-110">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="db8b1-110">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="db8b1-111">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="db8b1-111">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>