---
title: "PROFILER_HEAP_OBJECT_OPTIONAL_INFO_TYPE 열거형 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: fcb55f5f-ce75-4d05-9ce9-ba28c622f97d
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# PROFILER_HEAP_OBJECT_OPTIONAL_INFO_TYPE 열거형
여러 종류를의 선택적 정보를 나타냅니다.  [PROFILER\_HEAP\_OBJECT\_OPTIONAL\_INFO 구조체](../../winscript/reference/profiler-heap-object-optional-info-structure.md)에 사용됩니다.  
  
## 구문  
  
```  
typedef [v1_enum] enum {  
    PROFILER_HEAP_OBJECT_OPTIONAL_INFO_PROTOTYPE                    = 0x00000001,  
    PROFILER_HEAP_OBJECT_OPTIONAL_INFO_FUNCTION_NAME                = 0x00000002,  
    PROFILER_HEAP_OBJECT_OPTIONAL_INFO_SCOPE_LIST                   = 0x00000003,  
    PROFILER_HEAP_OBJECT_OPTIONAL_INFO_INTERNAL_PROPERTY            = 0x00000004,  
    PROFILER_HEAP_OBJECT_OPTIONAL_INFO_NAME_PROPERTIES              = 0x00000005,  
    PROFILER_HEAP_OBJECT_OPTIONAL_INFO_INDEX_PROPERTIES             = 0x00000006,  
    PROFILER_HEAP_OBJECT_OPTIONAL_INFO_ELEMENT_ATTRIBUTES_SIZE      = 0x00000007,  
    PROFILER_HEAP_OBJECT_OPTIONAL_INFO_ELEMENT_TEXT_CHILDREN_SIZE   = 0x00000008,  
    PROFILER_HEAP_OBJECT_OPTIONAL_INFO_RELATIONSHIPS                = 0x00000009,  
    PROFILER_HEAP_OBJECT_OPTIONAL_INFO_WINRTEVENTS                  = 0x0000000A,  
    PROFILER_HEAP_OBJECT_OPTIONAL_INFO_MAX_VALUE                    = PROFILER_HEAP_OBJECT_OPTIONAL_INFO_WINRTEVENTS  
} PROFILER_HEAP_OBJECT_OPTIONAL_INFO_TYPE;  
  
```  
  
## Members  
  
|멤버|값|설명|  
|--------|-------|--------|  
|PROFILER\_HEAP\_OBJECT\_OPTIONAL\_INFO\_PROTOTYPE|0x00000001|힙 개체의 프로토타입에 대 한 정보입니다.|  
|PROFILER\_HEAP\_OBJECT\_OPTIONAL\_INFO\_FUNCTION\_NAME|0x00000002|힙 개체의 함수 이름에 대 한 정보를 제공 합니다.|  
|PROFILER\_HEAP\_OBJECT\_OPTIONAL\_INFO\_SCOPE\_LIST|0x00000003|힙의 개체에 대 한 정보 [PROFILER\_HEAP\_OBJECT\_SCOPE\_LIST 구조체](../../winscript/reference/profiler-heap-object-scope-list-structure.md).|  
|PROFILER\_HEAP\_OBJECT\_OPTIONAL\_INFO\_INTERNAL\_PROPERTY|0x00000004|힙 개체의 내부 속성에 대 한 정보를 제공 합니다.|  
|PROFILER\_HEAP\_OBJECT\_OPTIONAL\_INFO\_NAME\_PROPERTIES|0x00000005|힙 개체의 이름 속성에 대 한 정보를 제공 합니다.|  
|PROFILER\_HEAP\_OBJECT\_OPTIONAL\_INFO\_INDEX\_PROPERTIES|0x00000006|힙 개체의 인덱스 속성에 대 한 정보를 제공 합니다.|  
|PROFILER\_HEAP\_OBJECT\_OPTIONAL\_INFO\_ELEMENT\_ATTRIBUTES\_SIZE|0x00000007|DOM 요소와 연결 된 특성의 크기입니다.|  
|PROFILER\_HEAP\_OBJECT\_OPTIONAL\_INFO\_ELEMENT\_TEXT\_CHILDREN\_SIZE|0x00000008|DOM 요소와 연결 된 모든 텍스트의 크기입니다.|  
|PROFILER\_HEAP\_OBJECT\_OPTIONAL\_INFO\_RELATIONSHIPS|0x00000009|힙 개체의 관계에 대 한 정보를 제공 합니다.|  
|ROFILER\_HEAP\_OBJECT\_OPTIONAL\_INFO\_WINRTEVENTS|0x0000000A|힙 개체의 Windows 런타임 이벤트에 대 한 정보입니다.|  
|PROFILER\_HEAP\_OBJECT\_OPTIONAL\_INFO\_MAX\_VALUE|PROFILER\_HEAP\_OBJECT\_OPTIONAL\_INFO\_WINRTEVENTS|이 열거형의 최대값입니다.|