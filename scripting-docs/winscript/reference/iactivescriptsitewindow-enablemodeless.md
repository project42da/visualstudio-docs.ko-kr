---
title: "IActiveScriptSiteWindow::EnableModeless | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IActiveScriptSiteWindow.EnableModeless
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IActiveScriptSiteWindow_EnableModeless"
ms.assetid: 83fe4f62-8e97-4f03-bc6f-d90aa888657d
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# IActiveScriptSiteWindow::EnableModeless
주 창으로 모덜리스 대화 상자를 사용 하지 않도록 설정 하는 호스트가 됩니다.  
  
## 구문  
  
```  
HRESULT EnableModeless(  
    BOOL fEnable  // enable flag  
);  
```  
  
#### 매개 변수  
 `fEnable`  
 \[in\] 플래그를 경우 `TRUE`, 주 창 및 모덜리스 대화 상자 또는 if `FALSE`를 사용할 수 없습니다.  
  
## 반환 값  
 반환 `S_OK` 면 또는 `E_FAIL` 오류가 발생 한 경우.  
  
## 설명  
 이 메서드를 동일 하 여 `IOleInPlaceFrame::EnableModeless` 메서드.  
  
 이 메서드를 호출 하는 중첩 될 수 있습니다.  
  
## 참고 항목  
 [IActiveScriptSiteWindow](../../winscript/reference/iactivescriptsitewindow.md)