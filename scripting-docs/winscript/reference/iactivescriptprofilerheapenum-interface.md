---
title: "IActiveScriptProfilerHeapEnum 인터페이스 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
ms.assetid: 16756d0e-547a-4825-8b7b-a7e0e4708a04
caps.latest.revision: "6"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4761e8c7d4cc9c3372c7906e1503b8dbd059ca33
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iactivescriptprofilerheapenum-interface"></a>IActiveScriptProfilerHeapEnum 인터페이스
관련 스크립트 엔진에 의해 수집 된 힙에 대 한 반복기 개체는 [iactivescriptprofilercontrol3:: Enumheap 메서드](../../winscript/reference/iactivescriptprofilercontrol3-enumheap-method.md)합니다.  
  
## <a name="syntax"></a>구문  
  
```vb  
interface IActiveScriptProfilerHeapEnum : IUnknown  
```  
  
## <a name="methods"></a>메서드  
 [IActiveScriptProfilerHeapEnum::Next 메서드](../../winscript/reference/iactivescriptprofilerheapenum-next-method.md)  
 에 의해 수집 되는 힙 개체의 집합의 개체 또는 개체를 가져옵니다는 [iactivescriptprofilercontrol3:: Enumheap 메서드](../../winscript/reference/iactivescriptprofilercontrol3-enumheap-method.md)합니다.  
  
 [IActiveScriptProfilerHeapEnum::GetOptionalInfo 메서드](../../winscript/reference/iactivescriptprofilerheapenum-getoptionalinfo-method.md)  
 에 의해 수집 되는 힙 개체의 집합에 지정된 된 개체에 대 한 선택적 정보를 가져옵니다는 [iactivescriptprofilercontrol3:: Enumheap 메서드](../../winscript/reference/iactivescriptprofilercontrol3-enumheap-method.md)합니다.  
  
 [IActiveScriptProfilerHeapEnum::FreeObjectAndOptionalInfo 메서드](../../winscript/reference/iactivescriptprofilerheapenum-freeobjectandoptionalinfo-method.md)  
 지정 된 실행을 해제 [PROFILER_HEAP_OBJECT 구조체](../../winscript/reference/profiler-heap-object-structure.md) 구조 및 이와 관련 된 [PROFILER_HEAP_OBJECT_OPTIONAL_INFO 구조체](../../winscript/reference/profiler-heap-object-optional-info-structure.md) 요소입니다.  
  
 [IActiveScriptProfilerHeapEnum::GetNameIdMap](../../winscript/reference/iactivescriptprofilerheapenum-getnameidmap.md)  
 에 해당 하는 문자열 이름을 반환 합니다. [PROFILER_HEAP_OBJECT_NAME_ID 형식](../../winscript/reference/profiler-heap-object-name-id-type.md) 값...