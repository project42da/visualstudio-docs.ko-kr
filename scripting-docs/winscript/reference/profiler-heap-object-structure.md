---
title: "PROFILER_HEAP_OBJECT 구조체 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 9f35362c-6856-4cfb-b990-031a156a58eb
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ad50f03806cbf98450c0fc917f1a97ca7305d05c
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="profilerheapobject-structure"></a>PROFILER_HEAP_OBJECT 구조체
힙 개체에 의해 수집 나타냅니다 [iactivescriptprofilercontrol3:: Enumheap 메서드](../../winscript/reference/iactivescriptprofilercontrol3-enumheap-method.md)합니다.  
  
## <a name="syntax"></a>구문  
  
```  
typedef struct _PROFILER_HEAP_OBJECT  
{  
    UINT size;    union {        PROFILER_HEAP_OBJECT_ID objectId;        PROFILER_EXTERNAL_OBJECT_ADDRESS externalObjectAddress;    };    PROFILER_HEAP_OBJECT_NAME_ID typeNameId;    USHORT flags;     USHORT optionalInfoCount;} PROFILER_HEAP_OBJECT;  
```  
  
## <a name="members"></a>멤버  
  
|멤버|형식|설명|  
|------------|----------|-----------------|  
|objectId|[PROFILER_HEAP_OBJECT_ID 형식](../../winscript/reference/profiler-heap-object-id-type.md)|힙 개체의 ID입니다.|  
|externalObjectAddress|[PROFILER_EXTERNAL_OBJECT_ADDRESS 형식](../../winscript/reference/profiler-external-object-address-type.md)|외부 개체의 주소는 JavaScript 힙을 밖에 있는 c + +에서 할당 된 개체 등의 개체입니다.|  
|typeNameId|[PROFILER_HEAP_OBJECT_NAME_ID 형식](../../winscript/reference/profiler-heap-object-name-id-type.md)|검색 된 힙 개체 형식 이름의 ID [IActiveScriptProfilerHeapEnum::GetNameIdMap](../../winscript/reference/iactivescriptprofilerheapenum-getnameidmap.md)합니다. 중 하나에만 `externalObjectAddress` 또는 `typeName` 에 따라는 `flags` 값입니다.|  
|플래그|[PROFILER_HEAP_OBJECT_FLAGS 열거형](../../winscript/reference/profiler-heap-object-flags-enumeration.md)|힙 개체에 대 한 기본 정보를 포함 하는 플래그입니다.|  
|optionalInfoCount|USHORT|수가 [PROFILER_HEAP_OBJECT_OPTIONAL_INFO 구조체](../../winscript/reference/profiler-heap-object-optional-info-structure.md) 레코드가 힙 개체에 사용할 수 있습니다.|