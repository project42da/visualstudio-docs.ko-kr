---
title: "액티브 스크립트 프로파일러 상수, 열거형 및 구조체 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 6e079d84-9dde-46fc-8a6a-18e902f60ecc
caps.latest.revision: 12
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 10
---
# 액티브 스크립트 프로파일러 상수, 열거형 및 구조체
다음과 같은 열거형은 Active 스크립트 프로파일러 인터페이스에서 사용됩니다.  
  
## 상수, 열거형 및 구조체  
  
|상수|설명|  
|--------|--------|  
|[PROFILER\_EXTERNAL\_OBJECT\_ADDRESS 형식](../../winscript/reference/profiler-external-object-address-type.md)|프로파일러 개체 외부 주소입니다.  [PROFILER\_HEAP\_OBJECT 구조체](../../winscript/reference/profiler-heap-object-structure.md) 및 [PROFILER\_HEAP\_OBJECT\_RELATIONSHIP 구조체](../../winscript/reference/profiler-heap-object-relationship-structure.md)에서 사용됩니다.|  
|[PROFILER\_HEAP\_OBJECT\_ID 형식](../../winscript/reference/profiler-heap-object-id-type.md)|힙 개체의 ID를 가져옵니다.  [PROFILER\_HEAP\_OBJECT 구조체](../../winscript/reference/profiler-heap-object-structure.md) [PROFILER\_HEAP\_OBJECT\_SCOPE\_LIST 구조체](../../winscript/reference/profiler-heap-object-scope-list-structure.md), [PROFILER\_HEAP\_OBJECT\_OPTIONAL\_INFO 구조체](../../winscript/reference/profiler-heap-object-optional-info-structure.md) 및 [PROFILER\_HEAP\_OBJECT\_RELATIONSHIP 구조체](../../winscript/reference/profiler-heap-object-relationship-structure.md)에서 사용됩니다.|  
|[PROFILER\_HEAP\_OBJECT\_NAME\_ID 형식](../../winscript/reference/profiler-heap-object-name-id-type.md)|힙 개체 이름의 ID입니다.  [PROFILER\_HEAP\_OBJECT 구조체](../../winscript/reference/profiler-heap-object-structure.md)에 사용됩니다.|  
  
|열거형|설명|  
|---------|--------|  
|[PROFILER\_EVENT\_MASK 열거형](../../winscript/reference/profiler-event-mask-enumeration.md)|프로필을 작성해야 하는 이벤트의 형식을 나타냅니다.|  
|[PROFILER\_HEAP\_ENUM\_FLAGS 열거형](../../winscript/reference/profiler-heap-enum-flags-enumeration.md)|개체 관계에서 가리킨 힙 개체에 대한 추가 정보가 노출되는지 여부를 나타내는 플래그입니다.  [IActiveScriptProfilerControl5::EnumHeap2 메서드](../../winscript/reference/iactivescriptprofilercontrol5-enumheap2-method.md)에서 사용됩니다.|  
|[PROFILER\_HEAP\_OBJECT\_FLAGS 열거형](../../winscript/reference/profiler-heap-object-flags-enumeration.md)|힙의 개체에 대한 기본 정보를 나타내는 플래그입니다.  [PROFILER\_HEAP\_OBJECT 구조체](../../winscript/reference/profiler-heap-object-structure.md)에서 사용됩니다.|  
|[PROFILER\_HEAP\_OBJECT\_OPTIONAL\_INFO\_TYPE 열거형](../../winscript/reference/profiler-heap-object-optional-info-type-enumeration.md)|여러 종류를의 선택적 정보를 나타냅니다.  [PROFILER\_HEAP\_OBJECT\_OPTIONAL\_INFO 구조체](../../winscript/reference/profiler-heap-object-optional-info-structure.md)에 사용됩니다.|  
|[PROFILER\_RELATIONSHIP\_INFO 열거형](../../winscript/reference/profiler-relationship-info-enumeration.md)|관계에서 개체에 대한 정보를 나타냅니다.  [PROFILER\_HEAP\_OBJECT\_RELATIONSHIP 구조체](../../winscript/reference/profiler-heap-object-relationship-structure.md)에 사용됩니다.|  
|[PROFILER\_SCRIPT\_TYPE 열거형](../../winscript/reference/profiler-script-type-enumeration.md)|스크립트의 형식을 지정합니다.|  
  
|구조체|설명|  
|---------|--------|  
|[PROFILER\_HEAP\_OBJECT 구조체](../../winscript/reference/profiler-heap-object-structure.md)|[IActiveScriptProfilerControl3::EnumHeap 메서드](../../winscript/reference/iactivescriptprofilercontrol3-enumheap-method.md)에서 수집한 힙 개체를 나타냅니다.|  
|[PROFILER\_HEAP\_OBJECT\_OPTIONAL\_INFO 구조체](../../winscript/reference/profiler-heap-object-optional-info-structure.md)|힙의 개체에 대한 선택적 정보를 나타냅니다.|  
|[PROFILER\_HEAP\_OBJECT\_RELATIONSHIP 구조체](../../winscript/reference/profiler-heap-object-relationship-structure.md)|힙 개체의 관계를 나타냅니다.|  
|[PROFILER\_HEAP\_OBJECT\_RELATIONSHIP\_LIST 구조체](../../winscript/reference/profiler-heap-object-relationship-list-structure.md)|힙의 개체에 속해 있는 관계의 목록을 나타냅니다.|  
|[PROFILER\_HEAP\_OBJECT\_SCOPE\_LIST 구조체](../../winscript/reference/profiler-heap-object-scope-list-structure.md)|이 구조는 함수 개체에만 연결되어 있습니다.  범위 목록은 각 주어진된 범위에 있는 변수를 나타내는 연결된 속성 목록 가진 힙 개체 목록의 함수 클로저를 나타냅니다.  경우에 따라 해당 범위에 있는 개체의 이름을 사용할 수 없고 id만 사용할 수 있습니다.|  
  
## 참고 항목  
 [액티브 스크립트 프로파일러 인터페이스](../../winscript/reference/active-script-profiler-interfaces.md)