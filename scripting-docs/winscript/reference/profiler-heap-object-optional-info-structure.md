---
title: "PROFILER_HEAP_OBJECT_OPTIONAL_INFO 구조체 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 77e638bd-ae36-4292-a170-90a0c500e610
caps.latest.revision: 5
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 5
---
# PROFILER_HEAP_OBJECT_OPTIONAL_INFO 구조체
힙의 개체에 대 한 선택적 정보를 나타냅니다.  
  
## 구문  
  
```  
typedef struct _PROFILER_HEAP_OBJECT_OPTIONAL_INFO  
{  
    PROFILER_HEAP_OBJECT_OPTIONAL_INFO_TYPE infoType;  
    [switch_type(PROFILER_HEAP_OBJECT_OPTIONAL_INFO_TYPE), switch_is(infoType)] union  
    {  
        [case(PROFILER_HEAP_OBJECT_OPTIONAL_INFO_PROTOTYPE)] PROFILER_HEAP_OBJECT_ID prototype;  
        [case(PROFILER_HEAP_OBJECT_OPTIONAL_INFO_FUNCTION_NAME)] LPCWSTR functionName;  
        [case(PROFILER_HEAP_OBJECT_OPTIONAL_INFO_ELEMENT_ATTRIBUTES_SIZE)] UINT elementAttributesSize;  
        [case(PROFILER_HEAP_OBJECT_OPTIONAL_INFO_ELEMENT_TEXT_CHILDREN_SIZE)] UINT elementTextChildrenSize;  
        [case(PROFILER_HEAP_OBJECT_OPTIONAL_INFO_SCOPE_LIST)] PROFILER_HEAP_OBJECT_SCOPE_LIST* scopeList;  
        [case(PROFILER_HEAP_OBJECT_OPTIONAL_INFO_INTERNAL_PROPERTY)] PROFILER_HEAP_OBJECT_RELATIONSHIP* internalProperty;  
        [case(PROFILER_HEAP_OBJECT_OPTIONAL_INFO_NAME_PROPERTIES)] PROFILER_HEAP_OBJECT_RELATIONSHIP_LIST* namePropertyList;  
        [case(PROFILER_HEAP_OBJECT_OPTIONAL_INFO_INDEX_PROPERTIES)] PROFILER_HEAP_OBJECT_RELATIONSHIP_LIST* indexPropertyList;  
        [case(PROFILER_HEAP_OBJECT_OPTIONAL_INFO_RELATIONSHIPS)] PROFILER_HEAP_OBJECT_RELATIONSHIP_LIST* relationshipList;  
        [case(PROFILER_HEAP_OBJECT_OPTIONAL_INFO_WINRTEVENTS)] PROFILER_HEAP_OBJECT_RELATIONSHIP_LIST* eventList;  
    };  
} PROFILER_HEAP_OBJECT_OPTIONAL_INFO;  
  
```  
  
## Members  
  
|멤버|형식|설명|  
|--------|--------|--------|  
|요약 정보 항목|[PROFILER\_HEAP\_OBJECT\_OPTIONAL\_INFO\_TYPE 열거형](../../winscript/reference/profiler-heap-object-optional-info-type-enumeration.md)|선택적 정보 유형을 지정 합니다.|  
|프로토타입\(Prototype\)|[PROFILER\_HEAP\_OBJECT\_ID 형식](../../winscript/reference/profiler-heap-object-id-type.md)|프로토타입 객체는 힙 개체의 ID입니다.|  
|functionName|LPCWSTR|힙 개체의 함수 이름입니다.|  
|elementAttributesSize|UINT|힙 개체의 요소 특성 크기입니다.|  
|elementTextChildrenSize|UINT|자식의 힙 개체의 텍스트 크기입니다.|  
|scopeList|[PROFILER\_HEAP\_OBJECT\_SCOPE\_LIST 구조체](../../winscript/reference/profiler-heap-object-scope-list-structure.md)|힙 개체의 범위 목록입니다.|  
|internalProperty|[PROFILER\_HEAP\_OBJECT\_RELATIONSHIP 구조체](../../winscript/reference/profiler-heap-object-relationship-structure.md)|힙 개체의 내부 속성입니다.|  
|namePropertyList|[PROFILER\_HEAP\_OBJECT\_RELATIONSHIP\_LIST 구조체](../../winscript/reference/profiler-heap-object-relationship-list-structure.md)|힙 개체의 이름 속성 목록이 있습니다.|  
|indexPropertyList|[PROFILER\_HEAP\_OBJECT\_RELATIONSHIP\_LIST 구조체](../../winscript/reference/profiler-heap-object-relationship-list-structure.md)|힙 개체의 인덱스 속성 목록이 있습니다.|  
|relationshipList|[PROFILER\_HEAP\_OBJECT\_RELATIONSHIP\_LIST 구조체](../../winscript/reference/profiler-heap-object-relationship-list-structure.md)|관계는 힙 개체의 목록입니다.|  
|eventList|[PROFILER\_HEAP\_OBJECT\_RELATIONSHIP\_LIST 구조체](../../winscript/reference/profiler-heap-object-relationship-list-structure.md)|힙 개체의 이벤트 목록을 제공 합니다.|