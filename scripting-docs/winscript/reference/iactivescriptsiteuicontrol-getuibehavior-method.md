---
title: "IActiveScriptSiteUIControl::GetUIBehavior 메서드 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: 9a944335-856a-4c6b-b2bc-8872542941b7
caps.latest.revision: 2
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 2
---
# IActiveScriptSiteUIControl::GetUIBehavior 메서드
가져옵니다는 [SCRIPTUICHANDLING 열거형](../../winscript/reference/scriptuichandling-enumeration.md) UI 컨트롤을 처리 하는 방법을 나타냅니다.  
  
## 구문  
  
```  
HRESULT GetUIBehavior(   
    [in] SCRIPTUICITEM UicItem,   
    [out] SCRIPTUICHANDLING * pUicHandling   
);  
  
```  
  
#### 매개 변수  
 `UicItem`  
 컨트롤의 형식입니다.  
  
 `pUicHandling`  
 컨트롤 방식으로 처리 되어야 합니다.