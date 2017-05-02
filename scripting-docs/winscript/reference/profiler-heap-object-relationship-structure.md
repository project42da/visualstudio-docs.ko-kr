---
title: "PROFILER_HEAP_OBJECT_RELATIONSHIP 구조체 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 3ab3d986-3314-4c7b-a1c8-18ed691a8b9c
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 4
---
# PROFILER_HEAP_OBJECT_RELATIONSHIP 구조체
힙 개체의 관계를 나타냅니다.  
  
## 구문  
  
```  
typedef struct _PROFILER_HEAP_OBJECT_RELATIONSHIP  
{  
    PROFILER_HEAP_OBJECT_NAME_ID relationshipId;  
    PROFILER_RELATIONSHIP_INFO relationshipInfo;  
    [switch_type(PROFILER_RELATIONSHIP_INFO), switch_is(relationshipInfo)] union  
    {  
        [case(PROFILER_PROPERTY_TYPE_NUMBER)] double numberValue;  
        [case(PROFILER_PROPERTY_TYPE_STRING)] LPCWSTR stringValue;  
        [case(PROFILER_PROPERTY_TYPE_HEAP_OBJECT)] PROFILER_HEAP_OBJECT_ID objectId;  
        [case(PROFILER_PROPERTY_TYPE_EXTERNAL_OBJECT)] PROFILER_EXTERNAL_OBJECT_ADDRESS externalObjectAddress;  
    };  
} PROFILER_HEAP_OBJECT_RELATIONSHIP;  
  
```  
  
## Members  
  
|멤버|값|설명|  
|--------|-------|--------|  
|relationshipId|[PROFILER\_HEAP\_OBJECT\_NAME\_ID 형식](../../winscript/reference/profiler-heap-object-name-id-type.md)|ID는 관계의 이름에서 [IActiveScriptProfilerHeapEnum::GetNameIdMap](../../winscript/reference/iactivescriptprofilerheapenum-getnameidmap.md).|  
|relationshipInfo|[PROFILER\_RELATIONSHIP\_INFO 열거형](../../winscript/reference/profiler-relationship-info-enumeration.md)|관계에 대 한 정보를 제공 합니다.|  
|numberValue|double|숫자 값입니다.  Only one of `numberValue`\/`stringValue`\/`objectId`\/`externalObjectAddress` is set, based on the `relationshipInfo` value.|  
|stringValue|LPCWSTR|문자열 값입니다.|  
|objectId|[PROFILER\_HEAP\_OBJECT\_ID 형식](../../winscript/reference/profiler-heap-object-id-type.md)|힙 개체의 ID입니다.|  
|externalObjectAddress|[PROFILER\_EXTERNAL\_OBJECT\_ADDRESS 형식](../../winscript/reference/profiler-external-object-address-type.md)|외부 개체 주소입니다.|