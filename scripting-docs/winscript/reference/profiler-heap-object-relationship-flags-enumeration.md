---
title: "PROFILER_HEAP_OBJECT_RELATIONSHIP_FLAGS 열거형 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 1a41b642-c9a9-4d83-b943-d59b232eebf6
caps.latest.revision: 4
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 4
---
# PROFILER_HEAP_OBJECT_RELATIONSHIP_FLAGS 열거형
개체 관계에서 가리킨 힙 개체가 getter 메서드인지 setter 메서드인지 나타내는 플래그입니다.  사용 된  [EnumHeap2](../../winscript/reference/iactivescriptprofilercontrol5-enumheap2-method.md) PROFILER\_HEAP\_OBJECT\_RELATIONSHIP\_FLAGS 값에 지정 된 메서드는 `enumFlags` 매개 변수.  
  
## 구문  
  
```  
typedef [v1_enum] enum {  
    PROFILER_HEAP_OBJECT_RELATIONSHIP_FLAGS_NONE                      = 0x00000000,  
    PROFILER_HEAP_OBJECT_RELATIONSHIP_FLAGS_IS_GET_ACCESSOR           = 0x00010000,  
    PROFILER_HEAP_OBJECT_RELATIONSHIP_FLAGS_IS_SET_ACCESSOR           = 0x00020000,  
} PROFILER_HEAP_OBJECT_RELATIONSHIP_FLAGS;  
  
```  
  
## Members  
  
|멤버|값|설명|  
|--------|-------|--------|  
|PROFILER\_HEAP\_OBJECT\_RELATIONSHIP\_FLAGS\_NONE|0x00000000|개체 관계에서 지정된 이 힙 개체는 getter 또는 setter 메서드로 식별되지 않습니다.|  
|PROFILER\_HEAP\_OBJECT\_RELATIONSHIP\_FLAGS\_IS\_GET\_ACCESSOR|0x00010000|개체 관계에서 가리킨 힙 개체는 getter 메서드입니다.  이 정보는의 높은 2 바이트 \(16 비트\)에 저장 됩니다의  [PROFILER\_HEAP\_OBJECT\_RELATIONSHIP.relationshipInfo](../../winscript/reference/profiler-heap-object-relationship-structure.md) 필드입니다.|  
|PROFILER\_HEAP\_OBJECT\_RELATIONSHIP\_FLAGS\_IS\_SET\_ACCESSOR|0x00020000|개체 관계에서 가리킨 힙 개체는 setter 메서드입니다.  이 정보는의 높은 2 바이트 \(16 비트\)에 저장 됩니다의 `PROFILER_HEAP_OBJECT_RELATIONSHIP.relationshipInfo` 필드입니다.|