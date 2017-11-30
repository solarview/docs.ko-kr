---
title: "ICorDebugStringValue::GetString 메서드"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: ICorDebugStringValue.GetString
api_location: mscordbi.dll
api_type: COM
f1_keywords: ICorDebugStringValue::GetString
helpviewer_keywords:
- ICorDebugStringValue::GetString method [.NET Framework debugging]
- GetString method, ICorDebugStringValue interface [.NET Framework debugging]
ms.assetid: 2b94bda7-09ee-435d-91b9-c4e31af1896c
topic_type: apiref
caps.latest.revision: "10"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: 077f8488419cee434a8dc8266b0814dfd4196b03
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/18/2017
---
# <a name="icordebugstringvaluegetstring-method"></a><span data-ttu-id="49be6-102">ICorDebugStringValue::GetString 메서드</span><span class="sxs-lookup"><span data-stu-id="49be6-102">ICorDebugStringValue::GetString Method</span></span>
<span data-ttu-id="49be6-103">이 ICorDebugStringValue이 참조 하는 문자열을 가져옵니다.</span><span class="sxs-lookup"><span data-stu-id="49be6-103">Gets the string referenced by this ICorDebugStringValue.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="49be6-104">구문</span><span class="sxs-lookup"><span data-stu-id="49be6-104">Syntax</span></span>  
  
```  
HRESULT GetString (  
    [in] ULONG32    cchString,  
    [out] ULONG32   *pcchString,  
    [out, size_is(cchString), length_is(*pcchString)]   
        WCHAR       szString[]  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="49be6-105">매개 변수</span><span class="sxs-lookup"><span data-stu-id="49be6-105">Parameters</span></span>  
 `cchString`  
 <span data-ttu-id="49be6-106">[in] `szString` 배열의 크기입니다.</span><span class="sxs-lookup"><span data-stu-id="49be6-106">[in] The size of the `szString` array.</span></span>  
  
 `pcchString`  
 <span data-ttu-id="49be6-107">[out] 반환 된 문자 수에 대 한 포인터는 `szString` 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="49be6-107">[out] A pointer to the number of characters returned in the `szString` array.</span></span>  
  
 `szString`  
 <span data-ttu-id="49be6-108">[out] 검색 된 문자열을 저장 하는 배열입니다.</span><span class="sxs-lookup"><span data-stu-id="49be6-108">[out] An array that stores the retrieved string.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="49be6-109">요구 사항</span><span class="sxs-lookup"><span data-stu-id="49be6-109">Requirements</span></span>  
 <span data-ttu-id="49be6-110">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="49be6-110">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="49be6-111">**헤더:** CorDebug.idl, CorDebug.h</span><span class="sxs-lookup"><span data-stu-id="49be6-111">**Header:** CorDebug.idl, CorDebug.h</span></span>  
  
 <span data-ttu-id="49be6-112">**라이브러리:** CorGuids.lib</span><span class="sxs-lookup"><span data-stu-id="49be6-112">**Library:** CorGuids.lib</span></span>  
  
 <span data-ttu-id="49be6-113">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="49be6-113">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>