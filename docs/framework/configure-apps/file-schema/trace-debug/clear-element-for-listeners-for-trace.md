---
title: '&lt;지우기&gt; 요소에 대 한 &lt;수신기&gt; 에 대 한 &lt;추적&gt;'
ms.date: 03/30/2017
f1_keywords:
- http://schemas.microsoft.com/.NetConfiguration/v2.0#configuration/system.diagnostics/trace/listeners/clear
helpviewer_keywords:
- clear element for <listeners> for <trace>
- <clear> element for <listeners> for <trace>
ms.assetid: b44732a8-271f-4a06-ba9e-fe3298d6f192
author: mcleblanc
ms.author: markl
ms.openlocfilehash: 91b4b4f132138fa6752c1da9b28e7a3ab7fad006
ms.sourcegitcommit: ea00c05e0995dae928d48ead99ddab6296097b4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/02/2018
ms.locfileid: "48033449"
---
# <a name="ltcleargt-element-for-ltlistenersgt-for-lttracegt"></a>&lt;지우기&gt; 요소에 대 한 &lt;수신기&gt; 에 대 한 &lt;추적&gt;
추적의 `Listeners` 컬렉션을 지웁니다.  
  
 \<configuration>  
\<system.diagnostics >  
\<추적 >  
\<수신기 >  
\<지우기 >  
  
## <a name="syntax"></a>구문  
  
```xml  
<clear/>  
```  
  
## <a name="attributes-and-elements"></a>특성 및 요소  
 다음 섹션에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### <a name="attributes"></a>특성  
 없음  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-elements"></a>부모 요소  
  
|요소|설명|  
|-------------|-----------------|  
|`configuration`|공용 언어 런타임 및 .NET Framework 응용 프로그램에서 사용하는 모든 구성 파일의 루트 요소입니다.|  
|`system.diagnostics`|메시지를 수집하고 저장하고 라우팅하는 추적 수신기를 지정하며, 추적 스위치가 설정되는 수준을 지정합니다.|  
|`trace`|추적 메시지를 수집하고 저장하고 라우팅하는 수신기가 포함되어 있습니다.|  
|`listeners`|수집, 저장 하 고 메시지를 라우팅하는 수신기를 포함 합니다. 수신기는 추적 출력을 적절 한 대상입니다.|  
  
## <a name="remarks"></a>설명  
 합니다 `<clear>` 에서 모든 수신기를 제거 하는 요소는 `Listeners` 추적에 대 한 컬렉션입니다. 사용할 수 있습니다를 `<clear>` 요소를 사용 하기 전에 `<add>` 요소 컬렉션에 다른 활성 수신기 수입니다.  
  
 지울 수 있습니다는 `Listeners` 호출 하 여 프로그래밍 방식으로 컬렉션을 <xref:System.Diagnostics.TraceListenerCollection.Clear%2A> 메서드를 <xref:System.Diagnostics.Trace.Listeners%2A?displayProperty=nameWithType> 속성 (`System.Diagnostics.Trace.Listeners.Clear()`).  
  
 이 요소는 응용 프로그램 구성 파일과 컴퓨터 구성 파일 (Machine.config)에서 사용할 수 있습니다.  
  
> [!NOTE]
>  `<clear>` 요소를 제거는 <xref:System.Diagnostics.DefaultTraceListener> 에서 `Listeners` 컬렉션의 동작 변경를 <xref:System.Diagnostics.Debug.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Trace.Assert%2A?displayProperty=nameWithType>, <xref:System.Diagnostics.Debug.Fail%2A?displayProperty=nameWithType>, 및 <xref:System.Diagnostics.Trace.Fail%2A?displayProperty=nameWithType> 메서드. 호출을 `Assert` 또는 `Fail` 메서드 일반적으로 메시지 상자를 표시 합니다. 그러나 messagebox 경우 표시 되지 않습니다 합니다 <xref:System.Diagnostics.DefaultTraceListener> 에 없는 경우는 `Listeners` 컬렉션입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 사용 하는 방법을 보여 줍니다는 `<clear>` 요소를 사용 하기 전에 `<add>` 수신기를 추가 하는 요소 `console` 에 `Listeners` 추적에 대 한 컬렉션입니다.  
  
```xml  
<configuration>  
  <system.diagnostics>  
    <trace autoflush="false" indentsize="4">  
      <listeners>  
        <clear/>  
        <add name="console"   
          type="System.Diagnostics.ConsoleTraceListener" >  
          <filter type="System.Diagnostics.EventTypeFilter"   
            initializeData="Error" />  
        </add>  
      </listeners>  
    </trace>  
  </system.diagnostics>  
</configuration>   
```  
  
## <a name="see-also"></a>참고 항목  
 <xref:System.Diagnostics.Trace.Listeners%2A>  
 <xref:System.Diagnostics.Trace>  
 <xref:System.Diagnostics.Debug>  
 <xref:System.Diagnostics.TraceSource>  
 [추적 및 디버그 설정 스키마](../../../../../docs/framework/configure-apps/file-schema/trace-debug/index.md)  
 [\<remove>](../../../../../docs/framework/configure-apps/file-schema/trace-debug/remove-element-for-listeners-for-trace.md)  
 [추적 수신기](../../../../../docs/framework/debug-trace-profile/trace-listeners.md)
