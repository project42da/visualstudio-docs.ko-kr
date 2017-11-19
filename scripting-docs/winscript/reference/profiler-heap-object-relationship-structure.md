---
title: "PROFILER_HEAP_OBJECT_RELATIONSHIP 구조체 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 3ab3d986-3314-4c7b-a1c8-18ed691a8b9c
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2b992b020c0aa42a6f27e484d55fe89a514c0198
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="profilerheapobjectrelationship-structure"></a>PROFILER_HEAP_OBJECT_RELATIONSHIP 구조체
힙 개체의 관계를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef struct _PROFILER_HEAP_OBJECT_RELATIONSHIP{    PROFILER_HEAP_OBJECT_NAME_ID relationshipId;    PROFILER_RELATIONSHIP_INFO relationshipInfo;    [switch_type(PROFILER_RELATIONSHIP_INFO), switch_is(relationshipInfo)] union    {        [case(PROFILER_PROPERTY_TYPE_NUMBER)] double numberValue;        [case(PROFILER_PROPERTY_TYPE_STRING)] LPCWSTR stringValue;        [case(PROFILER_PROPERTY_TYPE_HEAP_OBJECT)] PROFILER_HEAP_OBJECT_ID objectId;        [case(PROFILER_PROPERTY_TYPE_EXTERNAL_OBJECT)] PROFILER_EXTERNAL_OBJECT_ADDRESS externalObjectAddress;    };} PROFILER_HEAP_OBJECT_RELATIONSHIP;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|값|설명|  
|------------|-----------|-----------------|  
|relationshipId|[PROFILER_HEAP_OBJECT_NAME_ID 형식](../../winscript/reference/profiler-heap-object-name-id-type.md)|관계의 ID 이름에서 [IActiveScriptProfilerHeapEnum::GetNameIdMap](../../winscript/reference/iactivescriptprofilerheapenum-getnameidmap.md)합니다.|  
|relationshipInfo|[PROFILER_RELATIONSHIP_INFO 열거형](../../winscript/reference/profiler-relationship-info-enumeration.md)|관계에 대 한 정보입니다.|  
|numberValue|double|숫자 값입니다. 중 하나에만 `numberValue` / `stringValue` / `objectId` / `externalObjectAddress` 기반을 설정 되는 `relationshipInfo` 값입니다.|  
|StringValue|LPCWSTR|문자열 값입니다.|  
|objectId|[PROFILER_HEAP_OBJECT_ID 형식](../../winscript/reference/profiler-heap-object-id-type.md)|힙 개체의 ID입니다.|  
|externalObjectAddress|[PROFILER_EXTERNAL_OBJECT_ADDRESS 형식](../../winscript/reference/profiler-external-object-address-type.md)|외부 개체 주소입니다.|  
|부분 문자열|[PROFILER_PROPERTY_TYPE_SUBSTRING_INFO 구조체](../../winscript/reference/profiler-property-type-substring-info-structure.md)|부분 문자열 형식에 대 한 정보입니다.|