---
title: "IActiveScriptProfilerHeapEnum 인터페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 16756d0e-547a-4825-8b7b-a7e0e4708a04
caps.latest.revision: 6
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 6
---
# IActiveScriptProfilerHeapEnum 인터페이스
반복기 힙의 개체 스크립트 엔진에서 수집, 연관 된 [IActiveScriptProfilerControl3::EnumHeap 메서드](../../winscript/reference/iactivescriptprofilercontrol3-enumheap-method.md).  
  
## 구문  
  
```vb  
interface IActiveScriptProfilerHeapEnum : IUnknown  
```  
  
## 메서드  
 [IActiveScriptProfilerHeapEnum::Next 메서드](../../winscript/reference/iactivescriptprofilerheapenum-next-method.md)  
 다음 개체 또는 개체 집합에 의해 수집 된 힙의 개체를 가져옵니다는 [IActiveScriptProfilerControl3::EnumHeap 메서드](../../winscript/reference/iactivescriptprofilercontrol3-enumheap-method.md).  
  
 [IActiveScriptProfilerHeapEnum::GetOptionalInfo 메서드](../../winscript/reference/iactivescriptprofilerheapenum-getoptionalinfo-method.md)  
 선택적 정보를 지정 된 개체를 가져옵니다 집합에 의해 수집 된 힙의 개체는 [IActiveScriptProfilerControl3::EnumHeap 메서드](../../winscript/reference/iactivescriptprofilercontrol3-enumheap-method.md).  
  
 [IActiveScriptProfilerHeapEnum::FreeObjectAndOptionalInfo 메서드](../../winscript/reference/iactivescriptprofilerheapenum-freeobjectandoptionalinfo-method.md)  
 지정 된 해제 [PROFILER\_HEAP\_OBJECT 구조체](../../winscript/reference/profiler-heap-object-structure.md) 구조와 관련 된 [PROFILER\_HEAP\_OBJECT\_OPTIONAL\_INFO 구조체](../../winscript/reference/profiler-heap-object-optional-info-structure.md) 요소.  
  
 [IActiveScriptProfilerHeapEnum::GetNameIdMap](../../winscript/reference/iactivescriptprofilerheapenum-getnameidmap.md)  
 해당 문자열 이름을 반환 하는 [PROFILER\_HEAP\_OBJECT\_NAME\_ID 형식](../../winscript/reference/profiler-heap-object-name-id-type.md) 값.