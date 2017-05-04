---
title: "IWebAppDiagnosticsObjectInitialization 인터페이스 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "IWebAppDiagnosticsObjectInitialization 인터페이스"
ms.assetid: 32847838-01d9-4205-a811-3043d8c7a917
caps.latest.revision: 5
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 5
---
# IWebAppDiagnosticsObjectInitialization 인터페이스
이 인터페이스를 구현 하는 클래스에서 구현할 수 있습니다 [IWebAppDiagnosticsSetup::CreateObjectWithSiteAtWebApp](../../winscript/reference/iwebappdiagnosticssetup-createobjectwithsiteatwebapp.md).  [IWebAppDiagnosticsSetup 인터페이스](../../winscript/reference/iwebappdiagnosticssetup-interface.md)구현 하는 개체에서 구현 된 [IDebugApplication 인터페이스](../../winscript/reference/idebugapplication-interface.md).  대부분의 경우가이 개체는 PDM입니다.  
  
 개체를 만든 후 [IWebAppDiagnosticsObjectInitialization::Initialize](../../winscript/reference/iwebappdiagnosticsobjectinitialization-initialize.md) PDM 디버그 응용 프로그램에 대 한 참조를 호출 하 여 `hPassToObject` 매개 변수를 `CreateObjectWithSiteAtWebApp`.  
  
> [!IMPORTANT]
>  `IWebAppDiagnosticsObjectInitialization`activdbg100.h에서 찾을 수 없습니다.  
  
## 메서드  
 이 인터페이스는 다음 메서드를.  
  
|메서드|설명|  
|---------|--------|  
|[IWebAppDiagnosticsObjectInitialization::Initialize](../../winscript/reference/iwebappdiagnosticsobjectinitialization-initialize.md)|개체를 초기화합니다.|