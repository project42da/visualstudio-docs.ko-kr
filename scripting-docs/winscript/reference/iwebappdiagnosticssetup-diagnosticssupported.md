---
title: "IWebAppDiagnosticsSetup::DiagnosticsSupported | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-script-interfaces"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "reference"
helpviewer_keywords: 
  - "IWebAppDiagnosticsSetup::DiagnosticsSupported"
ms.assetid: 5bbcd0d0-1460-4cf7-bbb1-f4f4a04f739a
caps.latest.revision: 5
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 5
---
# IWebAppDiagnosticsSetup::DiagnosticsSupported
진단이 응용이 프로그램에서 지원 되는지 여부를 결정 합니다.  경우 [SetSite](http://go.microsoft.com/fwlink/?LinkId=232439) 는 NULL이 아닌 값으로이 인터페이스를 구현 하는 개체에서 호출 된 [DiagnosticsSupported](../../winscript/reference/iwebappdiagnosticssetup-diagnosticssupported.md) 반환 `true`.  이 반환 하는 경우 `false` 를 호출 하 고 [IWebAppDiagnosticsSetup::CreateObjectWithSiteAtWebApp](../../winscript/reference/iwebappdiagnosticssetup-createobjectwithsiteatwebapp.md) 실패.  
  
> [!IMPORTANT]
>  [IWebAppDiagnosticsSetup 인터페이스](../../winscript/reference/iwebappdiagnosticssetup-interface.md)PDM v11.0와 큰 구현 됩니다.  Activdbg100에서 찾을 수 있습니다.  
  
## 구문  
  
```cpp  
HRESULT DiagnosticsSupported(  
        [out, retval] VARIANT_BOOL* pRetVal  
        );  
```  
  
#### 매개 변수  
 `pRetVal`  
 경우 [SetSite](http://go.microsoft.com/fwlink/?LinkId=232439) 는 NULL이 아닌 값으로이 인터페이스를 구현 하는 개체에서 호출 된 [DiagnosticsSupported](../../winscript/reference/iwebappdiagnosticssetup-diagnosticssupported.md) 반환 `true`.  않습니다,이 반환 하는 경우 `false`를 호출 하 고 [IWebAppDiagnosticsSetup::CreateObjectWithSiteAtWebApp](../../winscript/reference/iwebappdiagnosticssetup-createobjectwithsiteatwebapp.md) 실패.