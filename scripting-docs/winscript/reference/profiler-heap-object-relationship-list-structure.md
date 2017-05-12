---
title: "PROFILER_HEAP_OBJECT_RELATIONSHIP_LIST 구조체 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 46ca87ea-5b0f-437d-a33f-b2d9a457e036
caps.latest.revision: 5
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 5
---
# PROFILER_HEAP_OBJECT_RELATIONSHIP_LIST 구조체
힙의 개체에 속하는 관계의 목록을 나타냅니다.  
  
## 구문  
  
```  
typedef struct _PROFILER_HEAP_OBJECT_RELATIONSHIP_LIST  
{  
    UINT count;  
    [size_is(count)] PROFILER_HEAP_OBJECT_RELATIONSHIP elements[];  
} PROFILER_HEAP_OBJECT_RELATIONSHIP_LIST;  
  
```  
  
## Members  
  
|멤버|형식|설명|  
|--------|--------|--------|  
|count|UINT|관계의 힙 개체의 수입니다.|  
|elements|[PROFILER\_HEAP\_OBJECT\_RELATIONSHIP 구조체](../../winscript/reference/profiler-heap-object-relationship-structure.md)|힙 개체의 관계입니다.|