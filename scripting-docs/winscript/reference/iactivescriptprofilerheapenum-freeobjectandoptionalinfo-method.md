---
title: "IActiveScriptProfilerHeapEnum::FreeObjectAndOptionalInfo 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: fdd5f7cc-be4e-4c13-a181-6320d26b44eb
caps.latest.revision: 3
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 3
---
# IActiveScriptProfilerHeapEnum::FreeObjectAndOptionalInfo 메서드
지정 된 해제 [PROFILER\_HEAP\_OBJECT 구조체](../../winscript/reference/profiler-heap-object-structure.md) 구조와 관련 된 [PROFILER\_HEAP\_OBJECT\_OPTIONAL\_INFO 구조체](../../winscript/reference/profiler-heap-object-optional-info-structure.md) 요소.  
  
## 구문  
  
```  
HRESULT FreeObjectAndOptionalInfo (  
    [in] ULONG celt,  
    [in, size_is(celt)] PROFILER_HEAP_OBJECT** heapObjects);  
  
```  
  
#### 매개 변수  
 `celt`  
 약속 개체의 수입니다.  
  
 `heapObjects`  
 [PROFILER\_HEAP\_OBJECT 구조체](../../winscript/reference/profiler-heap-object-structure.md) 구조체의 배열입니다.  
  
## 반환 값  
 HRESULT입니다.