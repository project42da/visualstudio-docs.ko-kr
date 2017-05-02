---
title: "PROFILER_HEAP_OBJECT_SCOPE_LIST 구조체 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 33ebaa31-0a35-47d5-a4e3-afd83e16f53e
caps.latest.revision: 5
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 5
---
# PROFILER_HEAP_OBJECT_SCOPE_LIST 구조체
이 구조 함수 개체와 연결 됩니다.  범위 목록 범위는 힙 개체 변수에 지정 된 각 범위를 나타내는 연결 된 속성 목록을 각 범위는 목록으로 클로저를 함수를 나타냅니다.  일부 경우에 이름 개체 범위를 사용할 수 있습니다 및 해당 인덱스 속성 목록에만 사용할 수 있습니다.  
  
## 구문  
  
```  
typedef struct _PROFILER_HEAP_OBJECT_SCOPE_LIST  
{  
    UINT count;  
    [size_is(count)] PROFILER_HEAP_OBJECT_ID scopes[];  
} PROFILER_HEAP_OBJECT_SCOPE_LIST;  
  
```  
  
## Members  
  
|멤버|형식|설명|  
|--------|--------|--------|  
|count|UINT|범위 수|  
|scopes|[PROFILER\_HEAP\_OBJECT\_ID 형식](../../winscript/reference/profiler-heap-object-id-type.md)|배열 범위입니다.|