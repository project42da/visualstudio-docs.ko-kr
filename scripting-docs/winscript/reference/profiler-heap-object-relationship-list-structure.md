---
title: "PROFILER_HEAP_OBJECT_RELATIONSHIP_LIST 구조체 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 46ca87ea-5b0f-437d-a33f-b2d9a457e036
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9fdad752587869fbdd1edfa325ddc1282cfa3a95
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="profilerheapobjectrelationshiplist-structure"></a>PROFILER_HEAP_OBJECT_RELATIONSHIP_LIST 구조체
힙 개체에 속하는 관계의 목록을 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef struct _PROFILER_HEAP_OBJECT_RELATIONSHIP_LIST{    UINT count;    [size_is(count)] PROFILER_HEAP_OBJECT_RELATIONSHIP elements[];} PROFILER_HEAP_OBJECT_RELATIONSHIP_LIST;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|형식|설명|  
|------------|----------|-----------------|  
|count|UINT|힙 개체의 관계 수를 지정 합니다.|  
|요소|[PROFILER_HEAP_OBJECT_RELATIONSHIP 구조체](../../winscript/reference/profiler-heap-object-relationship-structure.md)|힙 개체의 관계를 지정 합니다.|