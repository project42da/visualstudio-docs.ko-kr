---
title: "IActiveScriptProfilerControl5::EnumHeap2 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: a25859eb-ac28-4a97-bcb3-33788982a76b
caps.latest.revision: 4
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 4
---
# IActiveScriptProfilerControl5::EnumHeap2 메서드
연관된 스크립트 엔진의 컨텍스트에서 GC 힙 개체를 반복하는 데 사용할 수 있는 인터페이스\([IActiveScriptProfilerHeapEnum 인터페이스](../../winscript/reference/iactivescriptprofilerheapenum-interface.md)\)를 반환합니다.  
  
 디버그 또는 릴리스 모드에서 이 메서드를 호출할 수 있습니다.  이 메서드는 UI 스레드가 유휴 상태일 때 호출해야 합니다.  메서드가 호출된 후 [IActiveScriptProfilerHeapEnum::Next 메서드](../../winscript/reference/iactivescriptprofilerheapenum-next-method.md)에서 S\_FALSE를 반환하거나 [IActiveScriptProfilerHeapEnum 인터페이스](../../winscript/reference/iactivescriptprofilerheapenum-interface.md) 인터페이스 포인터가 릴리스될 때까지 [IActiveScriptProfilerHeapEnum::Next 메서드](../../winscript/reference/iactivescriptprofilerheapenum-next-method.md)를 제외하고 스크립트 엔진에 대해 수행할 작업이 없습니다.  
  
## 구문  
  
```  
HRESULT EnumHeap2(  
    [in] PROFILER_HEAP_ENUM_FLAGS enumFlags,  
    [out] IActiveScriptProfilerHeapEnum** ppEnum);  
  
```  
  
#### 매개 변수  
 enumFlags  
 개체 관계에서 가리킨 개체에 대한 추가 정보가 노출되는지 여부를 지정하는 값입니다.  추가 정보는 가리킨 개체가 getter 메서드인지 또는 setter 메서드인지를 나타낼 수 있습니다.  자세한 내용은 [PROFILER\_HEAP\_ENUM\_FLAGS 열거형](../../winscript/reference/profiler-heap-enum-flags-enumeration.md)을 참조하십시오.  
  
 ppEnum  
 \[out\] [IActiveScriptProfilerHeapEnum 인터페이스](../../winscript/reference/iactivescriptprofilerheapenum-interface.md)를 반환합니다.  
  
## 반환 값  
 HRESULT를 반환 합니다.  다음과 같은 값을 사용할 수 있습니다.  
  
|반환 값|의미|  
|----------|--------|  
|`S_OK`|힙 열거형 완료 되었습니다.|  
|`E_OUTOFMEMORY`|힙 열거 하는 데 사용할 수 있는 메모리가 부족 하 여 없습니다.|  
|`E_FAIL`|내부 오류가 발생했습니다.|