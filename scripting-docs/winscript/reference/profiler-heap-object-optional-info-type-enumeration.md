---
title: "PROFILER_HEAP_OBJECT_OPTIONAL_INFO_TYPE 열거형 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: fcb55f5f-ce75-4d05-9ce9-ba28c622f97d
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a73d6917f78a85bee1471fc54b01d5e691be8cdc
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="profilerheapobjectoptionalinfotype-enumeration"></a>PROFILER_HEAP_OBJECT_OPTIONAL_INFO_TYPE 열거형
여러 가지를 선택적 정보를 나타냅니다. 에 사용 된 [PROFILER_HEAP_OBJECT_OPTIONAL_INFO 구조체](../../winscript/reference/profiler-heap-object-optional-info-structure.md)합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef [v1_enum] enum {    PROFILER_HEAP_OBJECT_OPTIONAL_INFO_PROTOTYPE                    = 0x00000001,    PROFILER_HEAP_OBJECT_OPTIONAL_INFO_FUNCTION_NAME                = 0x00000002,    PROFILER_HEAP_OBJECT_OPTIONAL_INFO_SCOPE_LIST                   = 0x00000003,    PROFILER_HEAP_OBJECT_OPTIONAL_INFO_INTERNAL_PROPERTY            = 0x00000004,    PROFILER_HEAP_OBJECT_OPTIONAL_INFO_NAME_PROPERTIES              = 0x00000005,    PROFILER_HEAP_OBJECT_OPTIONAL_INFO_INDEX_PROPERTIES             = 0x00000006,    PROFILER_HEAP_OBJECT_OPTIONAL_INFO_ELEMENT_ATTRIBUTES_SIZE      = 0x00000007,    PROFILER_HEAP_OBJECT_OPTIONAL_INFO_ELEMENT_TEXT_CHILDREN_SIZE   = 0x00000008,    PROFILER_HEAP_OBJECT_OPTIONAL_INFO_RELATIONSHIPS                = 0x00000009,    PROFILER_HEAP_OBJECT_OPTIONAL_INFO_WINRTEVENTS                  = 0x0000000A,    PROFILER_HEAP_OBJECT_OPTIONAL_INFO_MAX_VALUE                    = PROFILER_HEAP_OBJECT_OPTIONAL_INFO_WINRTEVENTS} PROFILER_HEAP_OBJECT_OPTIONAL_INFO_TYPE;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|값|설명|  
|------------|-----------|-----------------|  
|PROFILER_HEAP_OBJECT_OPTIONAL_INFO_PROTOTYPE|0x00000001|힙 개체의 프로토타입에 대 한 정보입니다.|  
|PROFILER_HEAP_OBJECT_OPTIONAL_INFO_FUNCTION_NAME|0x00000002|힙 개체의 함수 이름에 대 한 정보입니다.|  
|PROFILER_HEAP_OBJECT_OPTIONAL_INFO_SCOPE_LIST|0x00000003|힙 개체에 대 한 내용은 [PROFILER_HEAP_OBJECT_SCOPE_LIST 구조체](../../winscript/reference/profiler-heap-object-scope-list-structure.md)합니다.|  
|PROFILER_HEAP_OBJECT_OPTIONAL_INFO_INTERNAL_PROPERTY|0x00000004|힙 개체의 내부 속성에 대 한 정보입니다.|  
|PROFILER_HEAP_OBJECT_OPTIONAL_INFO_NAME_PROPERTIES|0x00000005|힙 개체의 이름 속성에 대 한 정보입니다.|  
|PROFILER_HEAP_OBJECT_OPTIONAL_INFO_INDEX_PROPERTIES|0x00000006|힙 개체의 인덱스 속성에 대 한 정보입니다.|  
|PROFILER_HEAP_OBJECT_OPTIONAL_INFO_ELEMENT_ATTRIBUTES_SIZE|0x00000007|DOM 요소와 연결 된 특성의 크기입니다.|  
|PROFILER_HEAP_OBJECT_OPTIONAL_INFO_ELEMENT_TEXT_CHILDREN_SIZE|0x00000008|DOM 요소와 연결 된 텍스트의 크기입니다.|  
|PROFILER_HEAP_OBJECT_OPTIONAL_INFO_RELATIONSHIPS|0x00000009|힙 개체의 관계에 대 한 정보입니다.|  
|ROFILER_HEAP_OBJECT_OPTIONAL_INFO_WINRTEVENTS|0x0000000A|힙 개체의 Windows 런타임 이벤트에 대 한 정보입니다.|  
|PROFILER_HEAP_OBJECT_OPTIONAL_INFO_MAX_VALUE|PROFILER_HEAP_OBJECT_OPTIONAL_INFO_WINRTEVENTS|이 열거형의 최대값입니다.|