---
title: "IActiveScriptSiteWindow::GetWindow | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
apiname: IActiveScriptSiteWindow.GetWindow
apilocation: scrobj.dll
helpviewer_keywords: 
  - "IActiveScriptSiteWindow_GetWindow"
ms.assetid: 6284e38c-9dfb-4d69-903d-f243f78c0331
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# IActiveScriptSiteWindow::GetWindow
스크립팅 엔진에 표시 해야 하는 팝업 창 소유자로 역할을 할 수 있는 창 핸들을 검색 합니다.  
  
## 구문  
  
```  
HRESULT GetWindow(  
    HWND *phwnd  // address of variable for window handle  
);  
```  
  
#### 매개 변수  
 `phwnd`  
 \[out\] 변수의 주소를 해당 창 핸들을 받습니다.  
  
## 반환 값  
 반환 `S_OK` 면 또는 `E_FAIL` 오류가 발생 한 경우.  
  
## 설명  
 이 메서드는 `IOleWindow::GetWindow` 메서드와 비슷하며,  
  
## 참고 항목  
 [IActiveScriptSiteWindow](../../winscript/reference/iactivescriptsitewindow.md)