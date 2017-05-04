---
title: "IWebAppDiagnosticsSetup::CreateObjectWithSiteAtWebApp | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "IWebAppDiagnosticsSetup::CreateObjectWithSiteAtWebApp"
ms.assetid: 30975973-acb1-48f4-8266-5e097a57db22
caps.latest.revision: 5
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 5
---
# IWebAppDiagnosticsSetup::CreateObjectWithSiteAtWebApp
이 메서드는 클래스 ID를 사용 하 여 전달 co\-creates `rclsid` 를 사용 하는 `dwClsContext`.  마찬가지로 [IRemoteDebugApplication::CreateInstanceAtApplication](../../winscript/reference/iremotedebugapplication-createinstanceatapplication.md) 의 경우를 제외 하 고 작동 `CreateObjectWithSiteAtWebApp` 개체는 웹 응용 프로그램의 UI 스레드에서 비동기적으로 만들어집니다.  클래스 ID로 지정 된 개체를 구현 해야 [IWebAppDiagnosticsObjectInitialization 인터페이스](../../winscript/reference/iwebappdiagnosticsobjectinitialization-interface.md).  개체를 만든 후 [IWebAppDiagnosticsObjectInitialization::Initialize](../../winscript/reference/iwebappdiagnosticsobjectinitialization-initialize.md) PDM 디버그 응용 프로그램에 대 한 참조를 호출 하 여 `hPassToObject` 매개 변수를 `CreateObjectWithSiteAtWebApp`.  이 메서드를 사용 하 여 응용 프로그램은 익명 파이프를 사용 하 여 복사한 핸들을 전달할 수 [DuplicateHandle](http://go.microsoft.com/fwlink/?LinkId=232450).  
  
> [!IMPORTANT]
>  [IWebAppDiagnosticsSetup 인터페이스](../../winscript/reference/iwebappdiagnosticssetup-interface.md)PDM v11.0와 큰 구현 됩니다.  Activdbg100.h에서 찾을 수 있습니다.  
  
## 구문  
  
```cpp  
HRESULT CreateObjectWithSiteAtWebApp(  
        [in] REFCLSID rclsid,   
        [in] DWORD dwClsContext,   
        [in] REFIID riid,   
        [in] DWORD_PTR hPassToObject  
        );  
  
```  
  
#### 매개 변수  
 `rclsid`  
 만들 수 있는 클래스 ID 클래스입니다.  
  
 `dwClsContext`  
 컨텍스트는 코드를 실행 합니다.  대부분의 경우가 CLSCTX\_INPROC\_SERVER입니다.  
  
 `riid`  
 사용되지 않습니다.  
  
 `hPassToObject`  
 UI 스레드에서 만들어진 개체를 구현 하는 경우 개체에 전달할 값 [IWebAppDiagnosticsObjectInitialization 인터페이스](../../winscript/reference/iwebappdiagnosticsobjectinitialization-interface.md).