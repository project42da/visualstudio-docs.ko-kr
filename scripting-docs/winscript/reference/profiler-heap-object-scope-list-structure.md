---
title: "PROFILER_HEAP_OBJECT_SCOPE_LIST 구조체 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 33ebaa31-0a35-47d5-a4e3-afd83e16f53e
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 67f0972faee11e15bd5d0e9a219e439df49d9672
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="profilerheapobjectscopelist-structure"></a>PROFILER_HEAP_OBJECT_SCOPE_LIST 구조체
이 구조는 함수 개체와 연결 합니다. 범위 목록 클로저를 함수에 대 한 각 범위는 각 지정 된 범위에서 변수를 나타내는 연결 된 속성 목록 사용 하 여 힙 개체 범위 목록을 나타냅니다. 경우에 따라 범위를 사용할 수 없습니다 수의 개체 및 속성 목록에만 해당 인덱스의 이름을 ´ ù.  
  
## <a name="syntax"></a>구문  
  
```  
typedef struct _PROFILER_HEAP_OBJECT_SCOPE_LIST{    UINT count;    [size_is(count)] PROFILER_HEAP_OBJECT_ID scopes[];} PROFILER_HEAP_OBJECT_SCOPE_LIST;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|형식|설명|  
|------------|----------|-----------------|  
|count|UINT|범위 개수|  
|scopes|[PROFILER_HEAP_OBJECT_ID 형식](../../winscript/reference/profiler-heap-object-id-type.md)|배열 범위입니다.|