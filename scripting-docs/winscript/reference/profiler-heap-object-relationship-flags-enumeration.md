---
title: "PROFILER_HEAP_OBJECT_RELATIONSHIP_FLAGS 열거형 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 1a41b642-c9a9-4d83-b943-d59b232eebf6
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ab542225e0238dbd40f90d9de66d43d0791e05e0
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="profilerheapobjectrelationshipflags-enumeration"></a>PROFILER_HEAP_OBJECT_RELATIONSHIP_FLAGS 열거형
개체 관계에서 가리키는 힙 개체 여부를 나타내는 플래그는 getter 또는 setter 메서드입니다. 사용 되는 [EnumHeap2](../../winscript/reference/iactivescriptprofilercontrol5-enumheap2-method.md) PROFILER_HEAP_OBJECT_RELATIONSHIP_FLAGS 값이 지정 된 경우 메서드는 `enumFlags` 매개 변수입니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef [v1_enum] enum {    PROFILER_HEAP_OBJECT_RELATIONSHIP_FLAGS_NONE                      = 0x00000000,    PROFILER_HEAP_OBJECT_RELATIONSHIP_FLAGS_IS_GET_ACCESSOR           = 0x00010000,    PROFILER_HEAP_OBJECT_RELATIONSHIP_FLAGS_IS_SET_ACCESSOR           = 0x00020000,} PROFILER_HEAP_OBJECT_RELATIONSHIP_FLAGS;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|값|설명|  
|------------|-----------|-----------------|  
|PROFILER_HEAP_OBJECT_RELATIONSHIP_FLAGS_NONE|0x00000000|개체 관계에서 가리키는이 힙 개체 getter 또는 setter 메서드 단어로 식별 되지 않습니다.|  
|PROFILER_HEAP_OBJECT_RELATIONSHIP_FLAGS_IS_GET_ACCESSOR|0x00010000|Getter 메서드가 개체 관계에서 가리키는 힙 개체입니다. 이 정보는 높은 2 바이트 (16 비트)에 저장 된 [PROFILER_HEAP_OBJECT_RELATIONSHIP.relationshipInfo](../../winscript/reference/profiler-heap-object-relationship-structure.md) 필드입니다.|  
|PROFILER_HEAP_OBJECT_RELATIONSHIP_FLAGS_IS_SET_ACCESSOR|0x00020000|개체 관계에서 가리키는 힙 개체는 setter 메서드입니다. 이 정보는 높은 2 바이트 (16 비트)에 저장 된 `PROFILER_HEAP_OBJECT_RELATIONSHIP.relationshipInfo` 필드입니다.|