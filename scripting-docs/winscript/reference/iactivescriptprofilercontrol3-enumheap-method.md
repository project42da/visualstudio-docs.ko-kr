---
title: "IActiveScriptProfilerControl3::EnumHeap 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 2799d06d-20dd-4c12-9646-554c0ea3606e
caps.latest.revision: 5
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 5
---
# IActiveScriptProfilerControl3::EnumHeap 메서드
반환 된 인터페이스 \([IActiveScriptProfilerHeapEnum 인터페이스](../../winscript/reference/iactivescriptprofilerheapenum-interface.md)\) GC 힙에 개체 컨텍스트에 연결 된 스크립트 엔진의 반복에 사용할 수 있습니다.  
  
 두 디버그에이 메서드를 호출 하거나 릴리스 모드로 수 있습니다.  UI 스레드가 유휴 상태일 때이 메서드를 호출 해야 합니다.  메서드가 호출 된 후 작업을 제외 하 고 스크립트 엔진에 대해 수행 해야 [IActiveScriptProfilerHeapEnum::Next 메서드](../../winscript/reference/iactivescriptprofilerheapenum-next-method.md) 때까지 [IActiveScriptProfilerHeapEnum::Next 메서드](../../winscript/reference/iactivescriptprofilerheapenum-next-method.md) S\_FALSE를 반환 또는 [IActiveScriptProfilerHeapEnum 인터페이스](../../winscript/reference/iactivescriptprofilerheapenum-interface.md) 인터페이스 포인터가 해제 됩니다.  
  
## 구문  
  
```  
HRESULT EnumHeap([out] IActiveScriptProfilerHeapEnum** ppEnum);  
  
```  
  
#### 매개 변수  
 ppEnum  
 \[out\] [IActiveScriptProfilerHeapEnum 인터페이스](../../winscript/reference/iactivescriptprofilerheapenum-interface.md)를 반환합니다.  
  
## 반환 값  
 HRESULT입니다.