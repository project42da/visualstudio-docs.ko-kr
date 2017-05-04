---
title: "PROFILER_HEAP_OBJECT 구조체 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 9f35362c-6856-4cfb-b990-031a156a58eb
caps.latest.revision: 4
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 4
---
# PROFILER_HEAP_OBJECT 구조체
힙 개체를 수집 하 여 나타내는 [IActiveScriptProfilerControl3::EnumHeap 메서드](../../winscript/reference/iactivescriptprofilercontrol3-enumheap-method.md).  
  
## 구문  
  
```  
typedef struct _PROFILER_HEAP_OBJECT  
{  
    UINT size;  
    union {  
        PROFILER_HEAP_OBJECT_ID objectId;  
        PROFILER_EXTERNAL_OBJECT_ADDRESS externalObjectAddress;  
    };  
    PROFILER_HEAP_OBJECT_NAME_ID typeNameId;  
    USHORT flags;   
    USHORT optionalInfoCount;  
} PROFILER_HEAP_OBJECT;  
```  
  
## Members  
  
|멤버|형식|설명|  
|--------|--------|--------|  
|objectId|[PROFILER\_HEAP\_OBJECT\_ID 형식](../../winscript/reference/profiler-heap-object-id-type.md)|힙 개체의 ID입니다.|  
|externalObjectAddress|[PROFILER\_EXTERNAL\_OBJECT\_ADDRESS 형식](../../winscript/reference/profiler-external-object-address-type.md)|외부 개체 주소 같은 외부 JavaScript 힙입니다 C\+\+에서 할당 된 개체를 개체입니다.|  
|typeNameId|[PROFILER\_HEAP\_OBJECT\_NAME\_ID 형식](../../winscript/reference/profiler-heap-object-name-id-type.md)|힙 개체 형식 이름의 ID 검색에서 [IActiveScriptProfilerHeapEnum::GetNameIdMap](../../winscript/reference/iactivescriptprofilerheapenum-getnameidmap.md).  중 하나만 `externalObjectAddress` 또는 `typeName` 에 따라 제공 되는 `flags` 값.|  
|플래그|[PROFILER\_HEAP\_OBJECT\_FLAGS 열거형](../../winscript/reference/profiler-heap-object-flags-enumeration.md)|힙의 개체에 대 한 기본 정보를 포함 하는 플래그입니다.|  
|optionalInfoCount|USHORT|수 [PROFILER\_HEAP\_OBJECT\_OPTIONAL\_INFO 구조체](../../winscript/reference/profiler-heap-object-optional-info-structure.md) 힙 개체에 대해 사용할 수 있는 레코드.|