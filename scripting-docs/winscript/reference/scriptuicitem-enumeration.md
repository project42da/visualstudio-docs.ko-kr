---
title: "SCRIPTUICITEM 열거형 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
ms.assetid: fbf01f1b-5d7f-4d92-8d10-3da65e352d93
caps.latest.revision: 3
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 3
---
# SCRIPTUICITEM 열거형
UI 항목 유형을 나타냅니다.  사용 되는 [IActiveScriptSiteUIControl::GetUIBehavior 메서드](../../winscript/reference/iactivescriptsiteuicontrol-getuibehavior-method.md).  
  
## 구문  
  
```vb  
typedef enum tagSCRIPTUICITEM {   
    SCRIPTUICITEM_INPUTBOX = 1,   
    SCRIPTUICITEM_MSGBOX = 2,   
    } SCRIPTUICITEM;  
  
```  
  
## 열거형 값  
  
|||  
|-|-|  
|SCRIPTUICITEM\_INPUTBOX|입력된 컨트롤입니다.|  
|SCRIPTUICITEM\_MSGBOX|메시지 상자입니다.|