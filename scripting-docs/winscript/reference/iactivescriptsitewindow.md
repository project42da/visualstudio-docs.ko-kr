---
title: "IActiveScriptSiteWindow | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "IActiveScriptSiteWindow 인터페이스"
ms.assetid: 96d5c493-2c0b-47e2-848b-4a8dacdcd65c
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# IActiveScriptSiteWindow
이 인터페이스와 같은 개체의 사용자 인터페이스를 지 원하는 호스트에 의해 구현 됩니다 [IActiveScriptSite](../../winscript/reference/iactivescriptsite.md) .  서버와 같이 사용자 인터페이스를 지원 하지 않는 호스트를 구현 하는 `IActiveScriptSiteWindow` 인터페이스.  스크립팅 엔진이이 인터페이스를 호출 하 여 액세스 하는 `QueryInterface` 에서 `IActiveScriptSite`.  
  
## Vtable 순서의 메서드  
  
|메서드|설명|  
|---------|--------|  
|[IActiveScriptSiteWindow::GetWindow](../../winscript/reference/iactivescriptsitewindow-getwindow.md)|스크립팅 엔진에 표시 해야 하는 팝업 창 소유자로 역할을 할 수 있는 창 핸들을 검색 합니다.|  
|[IActiveScriptSiteWindow::EnableModeless](../../winscript/reference/iactivescriptsitewindow-enablemodeless.md)|주 창으로 모덜리스 대화 상자를 사용 하지 않도록 설정 하는 호스트가 됩니다.|  
  
## 참고 항목  
 [액티브 스크립트 인터페이스](../../winscript/reference/active-script-interfaces.md)