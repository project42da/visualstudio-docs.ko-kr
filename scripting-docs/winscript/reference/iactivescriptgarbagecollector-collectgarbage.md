---
title: "IActiveScriptGarbageCollector::CollectGarbage | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 75f77c49-2190-4d49-a3e0-9dcf847c502b
caps.latest.revision: 3
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 3
---
# IActiveScriptGarbageCollector::CollectGarbage
액티브 스크립트 호스트는 가비지 수집을 시작 하려면이 메서드를 호출 합니다.  
  
## 구문  
  
```  
HRESULT CollectGarbage(  
        SCRIPTGCTYPE scriptgctype  
    );  
  
```  
  
#### 매개 변수  
 `scriptgctype`  
 \[in\] [SCRIPTGCTYPE 열거형](../../winscript/reference/scriptgctype-enumeration.md) 는 표준 또는 철저 한 가비지 수집을 수행 하는지 여부를 지정 합니다.  
  
## 반환 값  
 HRESULT를 반환합니다.  
  
## 참고 항목  
 [IActiveScriptGarbageCollector 인터페이스](../../winscript/reference/iactivescriptgarbagecollector-interface.md)