---
title: "CorBindToRuntimeHost 함수"
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: reference
api_name: CorBindToRuntimeHost
api_location: mscoree.dll
api_type: DLLExport
f1_keywords: CorBindToRuntimeHost
helpviewer_keywords: CorBindToRuntimeHost function [.NET Framework hosting]
ms.assetid: 5c826ba3-8258-49bc-a417-78807915fcaf
topic_type: apiref
caps.latest.revision: "28"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.openlocfilehash: eff6fdf0294e3b1cc9830e58bc8103a64102d5b1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/21/2017
---
# <a name="corbindtoruntimehost-function"></a><span data-ttu-id="68a83-102">CorBindToRuntimeHost 함수</span><span class="sxs-lookup"><span data-stu-id="68a83-102">CorBindToRuntimeHost Function</span></span>
<span data-ttu-id="68a83-103">호스트 프로세스에 지정된 된 버전의 공용 언어 런타임 (CLR)를 로드할 수 있도록 합니다.</span><span class="sxs-lookup"><span data-stu-id="68a83-103">Enables hosts to load a specified version of the common language runtime (CLR) into a process.</span></span>  
  
 <span data-ttu-id="68a83-104">이 함수에 더 이상 사용 되지는 [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)]합니다.</span><span class="sxs-lookup"><span data-stu-id="68a83-104">This function has been deprecated in the [!INCLUDE[net_v40_long](../../../../includes/net-v40-long-md.md)].</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="68a83-105">구문</span><span class="sxs-lookup"><span data-stu-id="68a83-105">Syntax</span></span>  
  
```  
HRESULT CorBindToRuntimeHost (  
    [in] LPCWSTR       pwszVersion,   
    [in] LPCWSTR       pwszBuildFlavor,   
    [in] LPCWSTR       pwszHostConfigFile,   
    [in] VOID*         pReserved,   
    [in] DWORD         startupFlags,   
    [in] REFCLSID      rclsid,   
    [in] REFIID        riid,   
    [out] LPVOID FAR  *ppv  
);  
```  
  
#### <a name="parameters"></a><span data-ttu-id="68a83-106">매개 변수</span><span class="sxs-lookup"><span data-stu-id="68a83-106">Parameters</span></span>  
 `pwszVersion`  
 <span data-ttu-id="68a83-107">[in] 로드 하려는 CLR의 버전을 설명 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="68a83-107">[in] A string that describes the version of the CLR you want to load.</span></span>  
  
 <span data-ttu-id="68a83-108">.NET Framework의 버전 번호는 마침표로 구분 된 4 개의 부분으로 구성 됩니다: *major.minor.build.revision*합니다.</span><span class="sxs-lookup"><span data-stu-id="68a83-108">A version number in the .NET Framework consists of four parts separated by periods: *major.minor.build.revision*.</span></span> <span data-ttu-id="68a83-109">로 전달 되는 문자열 `pwszVersion` 문자 "v" 뒤에 버전 번호 (예: "나옵니다 v1.0.1529")의 처음 세 부분이로 시작 해야 합니다.</span><span class="sxs-lookup"><span data-stu-id="68a83-109">The string passed as `pwszVersion` must start with the character "v" followed by the first three parts of the version number (for example, "v1.0.1529").</span></span>  
  
 <span data-ttu-id="68a83-110">일부 버전의 CLR CLR의 이전 버전과 호환성을 지정 하는 정책 설명을 함께 설치 됩니다.</span><span class="sxs-lookup"><span data-stu-id="68a83-110">Some versions of the CLR are installed with a policy statement that specifies compatibility with previous versions of the CLR.</span></span> <span data-ttu-id="68a83-111">기본적으로 시작 shim 평가 `pwszVersion` 정책 문을 부하에 대해 최신 버전의 런타임 호환 되는 요청 된 버전입니다.</span><span class="sxs-lookup"><span data-stu-id="68a83-111">By default, the startup shim evaluates `pwszVersion` against policy statements and loads the latest version of the runtime that is compatible with the version being requested.</span></span> <span data-ttu-id="68a83-112">호스트 정책 평가 건너뛰고에 지정 된 정확한 버전을 로드 하는 shim을 강제할 수 `pwszVersion` STARTUP_LOADER_SAFEMODE에 대 한 값을 전달 하 여는 `startupFlags` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="68a83-112">A host can force the shim to skip policy evaluation and load the exact version specified in `pwszVersion` by passing a value of STARTUP_LOADER_SAFEMODE for the `startupFlags` parameter.</span></span>  
  
 <span data-ttu-id="68a83-113">경우 `pwszVersion` 은 `null,` 메서드는 CLR의 버전을 로드 하지 않습니다.</span><span class="sxs-lookup"><span data-stu-id="68a83-113">If `pwszVersion` is `null,` the method does not load any version of the CLR.</span></span> <span data-ttu-id="68a83-114">대신, CLR_E_SHIM_RUNTIMELOAD 런타임을 로드 하지 못했음을 나타내는 반환 합니다.</span><span class="sxs-lookup"><span data-stu-id="68a83-114">Instead, it returns CLR_E_SHIM_RUNTIMELOAD, which indicates that it failed to load the runtime.</span></span>  
  
 `pwszBuildFlavor`  
 <span data-ttu-id="68a83-115">[in] Clr 서버 또는 워크스테이션을 로드할지 여부를 지정 하는 문자열입니다.</span><span class="sxs-lookup"><span data-stu-id="68a83-115">[in] A string that specifies whether to load the server or the workstation build of the CLR.</span></span> <span data-ttu-id="68a83-116">유효한 값은 `svr` 및 `wks`입니다.</span><span class="sxs-lookup"><span data-stu-id="68a83-116">Valid values are `svr` and `wks`.</span></span> <span data-ttu-id="68a83-117">서버 빌드는 가비지 컬렉션에 대 한 여러 프로세서를 활용 하도록 최적화 하 고 단일 프로세서 컴퓨터에서 실행 되는 클라이언트 응용 프로그램에 대 한 워크스테이션 빌드 최적화 됩니다.</span><span class="sxs-lookup"><span data-stu-id="68a83-117">The server build is optimized to take advantage of multiple processors for garbage collections, and the workstation build is optimized for client applications running on a single-processor machine.</span></span>  
  
 <span data-ttu-id="68a83-118">경우 `pwszBuildFlavor` 로 설정 된 워크스테이션 빌드가 null 로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="68a83-118">If `pwszBuildFlavor` is set to null, the workstation build is loaded.</span></span> <span data-ttu-id="68a83-119">를 단일 프로세서 컴퓨터에서 실행 하는 경우 워크스테이션 빌드 항상 로드, 경우에 `pwszBuildFlavor` 로 설정 된 `svr`합니다.</span><span class="sxs-lookup"><span data-stu-id="68a83-119">When running on a single-processor machine, the workstation build is always loaded, even if `pwszBuildFlavor` is set to `svr`.</span></span> <span data-ttu-id="68a83-120">그러나 경우 `pwszBuildFlavor` 로 설정 된 `svr` 동시 가비지 컬렉션이 지정 되 고 (의 설명을 참조는 `startupFlags` 매개 변수), 서버 빌드가 로드 됩니다.</span><span class="sxs-lookup"><span data-stu-id="68a83-120">However, if `pwszBuildFlavor` is set to `svr` and concurrent garbage collection is specified (see the description of the `startupFlags` parameter), the server build is loaded.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="68a83-121">동시 가비지 수집이 WOW64를 실행 하는 응용 프로그램에서 지원 되지 않습니다 x86 에뮬레이터 (이전의 ia-64) Intel Itanium 아키텍처를 구현 하는 64 비트 시스템에서 합니다.</span><span class="sxs-lookup"><span data-stu-id="68a83-121">Concurrent garbage collection is not supported in applications running the WOW64 x86 emulator on 64-bit systems that implement the Intel Itanium architecture (formerly called IA-64).</span></span> <span data-ttu-id="68a83-122">64 비트 Windows 시스템에서 w o w 64를 사용 하는 방법에 대 한 자세한 내용은 참조 [실행 중인 32 비트 응용 프로그램](http://msdn.microsoft.com/library/windows/desktop/aa384249.aspx)합니다.</span><span class="sxs-lookup"><span data-stu-id="68a83-122">For more information about using WOW64 on 64-bit Windows systems, see [Running 32-bit Applications](http://msdn.microsoft.com/library/windows/desktop/aa384249.aspx).</span></span>  
  
 `pwszHostConfigFile`  
 <span data-ttu-id="68a83-123">[in] 로드 하기 위해 CLR의 버전을 지정 하는 호스트 구성 파일의 이름입니다.</span><span class="sxs-lookup"><span data-stu-id="68a83-123">[in] The name of a host configuration file that specifies the version of the CLR to load.</span></span> <span data-ttu-id="68a83-124">파일 이름에 정규화 된 경로가 포함 되어 있지 않으면, 파일은 호출 하는 실행 파일과 동일한 디렉터리에 있는 것으로 간주 됩니다.</span><span class="sxs-lookup"><span data-stu-id="68a83-124">If the file name does not include a fully qualified path, the file is assumed to be in the same directory as the executable that is making the call.</span></span>  
  
 `pReserved`  
 <span data-ttu-id="68a83-125">[in] 다음 버전의 확장에 대 한 예약 되어 있습니다.</span><span class="sxs-lookup"><span data-stu-id="68a83-125">[in] Reserved for future extensibility.</span></span>  
  
 `startupFlags`  
 <span data-ttu-id="68a83-126">[in] 동시 가비지 수집, 도메인 중립 코드의 동작을 제어 하는 플래그 집합은 `pwszVersion` 매개 변수입니다.</span><span class="sxs-lookup"><span data-stu-id="68a83-126">[in] A set of flags that controls concurrent garbage collection, domain-neutral code, and the behavior of the `pwszVersion` parameter.</span></span> <span data-ttu-id="68a83-127">플래그가 설정 된 경우 기본값은 단일 도메인으로 지정 합니다.</span><span class="sxs-lookup"><span data-stu-id="68a83-127">The default is single domain if no flag is set.</span></span> <span data-ttu-id="68a83-128">지원 되는 값 목록에 대 한 참조는 [STARTUP_FLAGS 열거형](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="68a83-128">For a list of supported values, see the [STARTUP_FLAGS enumeration](../../../../docs/framework/unmanaged-api/hosting/startup-flags-enumeration.md).</span></span>  
  
 `rclsid`  
 <span data-ttu-id="68a83-129">[in] `CLSID` 중 하나를 구현 하는 coclass의는 [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) 또는 [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="68a83-129">[in] The `CLSID` of the coclass that implements either the [ICorRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md) or the [ICLRRuntimeHost](../../../../docs/framework/unmanaged-api/hosting/iclrruntimehost-interface.md) interface.</span></span> <span data-ttu-id="68a83-130">지원 되는 값은 CLSID_CorRuntimeHost 또는 CLSID_CLRRuntimeHost입니다.</span><span class="sxs-lookup"><span data-stu-id="68a83-130">Supported values are CLSID_CorRuntimeHost or CLSID_CLRRuntimeHost.</span></span>  
  
 `riid`  
 <span data-ttu-id="68a83-131">[in] `IID` 요청 하는 인터페이스입니다.</span><span class="sxs-lookup"><span data-stu-id="68a83-131">[in] The `IID` of the interface you are requesting.</span></span> <span data-ttu-id="68a83-132">지원 되는 값은 IID_ICorRuntimeHost 또는 IID_ICLRRuntimeHost입니다.</span><span class="sxs-lookup"><span data-stu-id="68a83-132">Supported values are IID_ICorRuntimeHost or IID_ICLRRuntimeHost.</span></span>  
  
 `ppv`  
 <span data-ttu-id="68a83-133">[out] 로드 된 런타임 버전을 사용 하는 인터페이스 포인터입니다.</span><span class="sxs-lookup"><span data-stu-id="68a83-133">[out] An interface pointer to the version of the runtime that was loaded.</span></span>  
  
## <a name="requirements"></a><span data-ttu-id="68a83-134">요구 사항</span><span class="sxs-lookup"><span data-stu-id="68a83-134">Requirements</span></span>  
 <span data-ttu-id="68a83-135">**플랫폼:** 참조 [시스템 요구 사항](../../../../docs/framework/get-started/system-requirements.md)합니다.</span><span class="sxs-lookup"><span data-stu-id="68a83-135">**Platforms:** See [System Requirements](../../../../docs/framework/get-started/system-requirements.md).</span></span>  
  
 <span data-ttu-id="68a83-136">**헤더:** MSCorEE.idl</span><span class="sxs-lookup"><span data-stu-id="68a83-136">**Header:** MSCorEE.idl</span></span>  
  
 <span data-ttu-id="68a83-137">**라이브러리:** MSCorEE.dll</span><span class="sxs-lookup"><span data-stu-id="68a83-137">**Library:** MSCorEE.dll</span></span>  
  
 <span data-ttu-id="68a83-138">**.NET framework 버전:**[!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span><span class="sxs-lookup"><span data-stu-id="68a83-138">**.NET Framework Versions:** [!INCLUDE[net_current_v10plus](../../../../includes/net-current-v10plus-md.md)]</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="68a83-139">참고 항목</span><span class="sxs-lookup"><span data-stu-id="68a83-139">See Also</span></span>  
 [<span data-ttu-id="68a83-140">CorBindToCurrentRuntime 함수</span><span class="sxs-lookup"><span data-stu-id="68a83-140">CorBindToCurrentRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtocurrentruntime-function.md)  
 [<span data-ttu-id="68a83-141">CorBindToRuntime 함수</span><span class="sxs-lookup"><span data-stu-id="68a83-141">CorBindToRuntime Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntime-function.md)  
 [<span data-ttu-id="68a83-142">CorBindToRuntimeByCfg 함수</span><span class="sxs-lookup"><span data-stu-id="68a83-142">CorBindToRuntimeByCfg Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimebycfg-function.md)  
 [<span data-ttu-id="68a83-143">CorBindToRuntimeEx 함수</span><span class="sxs-lookup"><span data-stu-id="68a83-143">CorBindToRuntimeEx Function</span></span>](../../../../docs/framework/unmanaged-api/hosting/corbindtoruntimeex-function.md)  
 [<span data-ttu-id="68a83-144">ICorRuntimeHost 인터페이스</span><span class="sxs-lookup"><span data-stu-id="68a83-144">ICorRuntimeHost Interface</span></span>](../../../../docs/framework/unmanaged-api/hosting/icorruntimehost-interface.md)  
 [<span data-ttu-id="68a83-145">사용 되지 않는 CLR 호스팅 함수</span><span class="sxs-lookup"><span data-stu-id="68a83-145">Deprecated CLR Hosting Functions</span></span>](../../../../docs/framework/unmanaged-api/hosting/deprecated-clr-hosting-functions.md)