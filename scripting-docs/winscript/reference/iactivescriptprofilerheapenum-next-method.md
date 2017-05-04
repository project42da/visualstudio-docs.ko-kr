---
title: "IActiveScriptProfilerHeapEnum::Next 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 0336286f-1dcd-4df9-adf5-76b59b4e74bb
caps.latest.revision: 4
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 4
---
# IActiveScriptProfilerHeapEnum::Next 메서드
다음 개체나 개체 집합이 힙 개체에서 가져옵니다의 [IActiveScriptProfilerControl3::EnumHeap 메서드](../../winscript/reference/iactivescriptprofilercontrol3-enumheap-method.md).  
  
## 구문  
  
```  
HRESULT Next (  
    [in] ULONG celt,  
    [out, size_is(celt), length_is(*pceltFetched)] PROFILER_HEAP_OBJECT** heapObjects,   
    [out] ULONG *pceltFetched);  
  
```  
  
#### 매개 변수  
 `celt`  
 반환할 개체 수입니다.  
  
 `heapObjects`  
 \[out\] 다음 [PROFILER\_HEAP\_OBJECT 구조체](../../winscript/reference/profiler-heap-object-structure.md) 구조.  
  
 `pceltFetched`  
 \[out\] 반환 된 개체 수  
  
## 반환 값  
 HRESULT입니다.