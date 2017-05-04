---
title: "PROFILER_RELATIONSHIP_INFO 열거형 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: fae69317-6224-4a6a-8e9e-ccaa6a330818
caps.latest.revision: 6
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 4
---
# PROFILER_RELATIONSHIP_INFO 열거형
관계에서 개체에 대 한 정보를 나타냅니다.  [PROFILER\_HEAP\_OBJECT\_RELATIONSHIP 구조체](../../winscript/reference/profiler-heap-object-relationship-structure.md)에 사용됩니다.  
  
## 구문  
  
```  
typedef [v1_enum] enum {  
    PROFILER_PROPERTY_TYPE_NUMBER = 0x01,  
    PROFILER_PROPERTY_TYPE_STRING = 0x02,  
    PROFILER_PROPERTY_TYPE_HEAP_OBJECT = 0x03,  
    PROFILER_PROPERTY_TYPE_EXTERNAL_OBJECT = 0x04,  
    PROFILER_PROPERTY_TYPE_BSTR = 0x05,  
} PROFILER_RELATIONSHIP_INFO;  
  
```  
  
## Members  
  
|멤버|값|설명|  
|--------|-------|--------|  
|PROFILER\_PROPERTY\_TYPE\_NUMBER|0x01|개체 수입니다.|  
|PROFILER\_PROPERTY\_TYPE\_STRING|0x02|개체는 문자열입니다.|  
|PROFILER\_PROPERTY\_TYPE\_HEAP\_OBJECT|0 x 03|개체는 힙에 개체가입니다.|  
|PROFILER\_PROPERTY\_TYPE\_EXTERNAL\_OBJECT|0x04|즉, 가비지 수집 힙에 외부 개체가 없습니다.|  
|PROFILER\_PROPERTY\_TYPE\_BSTR|같습니다.|개체가 BSTR입니다.|