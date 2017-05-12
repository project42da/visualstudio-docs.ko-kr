---
title: "PROFILER_HEAP_ENUM_FLAGS 열거형 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 17936b7a-40d5-4774-b92b-b24ee391591e
caps.latest.revision: 6
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 4
---
# PROFILER_HEAP_ENUM_FLAGS 열거형
개체 관계에서 가리킨 힙 개체에 대한 추가 정보가 노출되는지 여부를 나타내는 플래그입니다.  사용 된  [EnumHeap2](../../winscript/reference/iactivescriptprofilercontrol5-enumheap2-method.md) 메서드.  
  
## 구문  
  
```  
typedef [v1_enum] enum {  
    PROFILER_HEAP_ENUM_FLAGS_NONE                      = 0x00000000,  
    PROFILER_HEAP_ENUM_FLAGS_STORE_RELATIONSHIP_FLAGS  = 0x00000001,  
} PROFILER_HEAP_ENUM_FLAGS;  
  
```  
  
## Members  
  
|멤버|값|설명|  
|--------|-------|--------|  
|PROFILER\_HEAP\_ENUM\_FLAGS\_NONE|0x00000000|이 힙 개체는 개체 관계에 대해 추가 정보를 노출하지 않습니다.  이 힙 개체와 동일한 방식으로 작동  [IActiveScriptProfilerControl3::HeapEnum](../../winscript/reference/iactivescriptprofilercontrol3-enumheap-method.md).|  
|PROFILER\_HEAP\_ENUM\_ENUM\_ STORE\_RELATIONSHIP\_FLAGS|0x00000001|이 힙 개체는 개체 관계에서 지정된 개체가 getter 또는 setter 메서드인지 여부에 대한 정보를 노출합니다.  이 정보는의 높은 2 바이트 \(16 비트\)에 저장 됩니다의  [PROFILER\_HEAP\_OBJECT\_RELATIONSHIP.relationshipInfo](../../winscript/reference/profiler-heap-object-relationship-structure.md) 필드 중 하나로  [PROFILER\_HEAP\_OBJECT\_RELATIONSHIP\_FLAGS](../../winscript/reference/profiler-heap-object-relationship-flags-enumeration.md) 열거형 값입니다.|