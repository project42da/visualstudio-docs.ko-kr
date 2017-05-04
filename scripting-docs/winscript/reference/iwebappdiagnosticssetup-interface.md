---
title: "IWebAppDiagnosticsSetup 인터페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "IWebAppDiagnosticsSetup 인터페이스"
ms.assetid: ec7359f2-633e-4d59-b64b-9cab0134dfd0
caps.latest.revision: 4
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 4
---
# IWebAppDiagnosticsSetup 인터페이스
디버깅 중인 프로세스에서 COM 개체를 생성 하 고 웹에 대 한 진단 유틸리티를 사용 하 여 PDM 디버그 응용에서이 인터페이스를 구현 합니다.  응용 프로그램 개체 구현에서 PDM을 디버깅 하는 경우 [IObjectWithSite](http://go.microsoft.com/fwlink/?LinkId=232438), Internet Explorer 호출 합니다. [SetSite](http://go.microsoft.com/fwlink/?LinkId=232439) 을 만든 후 가공에 대 한 참조를 [IWebBrowser2](http://go.microsoft.com/fwlink/?LinkId=232449).  WWA 응용 프로그램을 호출 합니다. [SetSite](http://go.microsoft.com/fwlink/?LinkId=232439) 와 가공 패스는 WWA에서 IWebApplicationHost 대신 인터페이스.  경우 [SetSite](http://go.microsoft.com/fwlink/?LinkId=232439) 는 NULL이 아닌 값으로 호출 된 [IWebAppDiagnosticsSetup::DiagnosticsSupported](../../winscript/reference/iwebappdiagnosticssetup-diagnosticssupported.md) true를 반환 합니다.  않으면 false를 반환 하 고 호출 하는 경우 [IWebAppDiagnosticsSetup::CreateObjectWithSiteAtWebApp](../../winscript/reference/iwebappdiagnosticssetup-createobjectwithsiteatwebapp.md) 실패 합니다.  
  
> [!IMPORTANT]
>  `IWebAppDiagnosticsSetup`PDM v11.0와 큰 구현 됩니다.  Activdbg100.h에서 찾을 수 있습니다.  
  
## 메서드  
 이 인터페이스는 다음 메서드를.  
  
|메서드|설명|  
|---------|--------|  
|[IWebAppDiagnosticsSetup::CreateObjectWithSiteAtWebApp](../../winscript/reference/iwebappdiagnosticssetup-createobjectwithsiteatwebapp.md)|지정 된 필터에 의해 숨겨진 된 텍스트 문서를 가져옵니다.|  
|[IWebAppDiagnosticsSetup::DiagnosticsSupported](../../winscript/reference/iwebappdiagnosticssetup-diagnosticssupported.md)|지정 된 문서를이 노드의 자식 노드 중 하나에 속하는지 여부를 결정 합니다.|