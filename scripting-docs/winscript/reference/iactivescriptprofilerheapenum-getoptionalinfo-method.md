---
title: "IActiveScriptProfilerHeapEnum::GetOptionalInfo 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 99ed9df5-71cf-4c25-b189-af9accc466ee
caps.latest.revision: 6
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 6
---
# IActiveScriptProfilerHeapEnum::GetOptionalInfo 메서드
지정된 개체에 대한 선택적 정보를 가져옵니다 \(힙 개체에서 반환 된 집합에서의 [IActiveScriptProfilerControl3::EnumHeap 메서드](../../winscript/reference/iactivescriptprofilercontrol3-enumheap-method.md)\).  
  
 반환된 개체에 할당된 메모리를 해제해야 합니다.  그 대신 [IActiveScriptProfilerHeapEnum::FreeObjectAndOptionalInfo 메서드](../../winscript/reference/iactivescriptprofilerheapenum-freeobjectandoptionalinfo-method.md)을 호출해야 합니다.  
  
## 구문  
  
```  
HRESULT GetOptionalInfo (  
    [in] PROFILER_HEAP_OBJECT* heapObject,  
    [in] ULONG celt,  
    [out, size_is(celt)] PROFILER_HEAP_OBJECT_OPTIONAL_INFO* optionalInfo);  
  
```  
  
#### 매개 변수  
 `heapObject`  
 정보가 반환되기 위한 [PROFILER\_HEAP\_OBJECT 구조체](../../winscript/reference/profiler-heap-object-structure.md) 입니다.  
  
 `celt`  
 반환할 [PROFILER\_HEAP\_OBJECT\_OPTIONAL\_INFO 구조체](../../winscript/reference/profiler-heap-object-optional-info-structure.md) 구조체의 수입니다.  
  
 `optionalInfo`  
 \[out\] 지정된 개체에 대한 [PROFILER\_HEAP\_OBJECT\_OPTIONAL\_INFO 구조체](../../winscript/reference/profiler-heap-object-optional-info-structure.md) 구조의 배열입니다.  
  
## 반환 값  
 HRESULT입니다.