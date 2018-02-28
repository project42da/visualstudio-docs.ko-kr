---
title: IWebAppDiagnosticsSetup::CreateObjectWithSiteAtWebApp | Microsoft Docs
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords:
- IWebAppDiagnosticsSetup::CreateObjectWithSiteAtWebApp
ms.assetid: 30975973-acb1-48f4-8266-5e097a57db22
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1442297fcacb3a9464f9ea67489c91c8ab64ad78
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iwebappdiagnosticssetupcreateobjectwithsiteatwebapp"></a>IWebAppDiagnosticsSetup::CreateObjectWithSiteAtWebApp
이 메서드는 함께 사용 하 여 전달 ID를 가진 클래스 만듭니다 `rclsid` 를 사용 하 여 `dwClsContext`합니다. 이 방식과 유사 하 게 [IRemoteDebugApplication::CreateInstanceAtApplication](../../winscript/reference/iremotedebugapplication-createinstanceatapplication.md) 작동 하는 경우를 제외 하 고 `CreateObjectWithSiteAtWebApp` 개체가 웹 응용 프로그램의 UI 스레드에서 비동기적으로 생성 됩니다. 클래스 ID가 지정한 개체를 구현 해야 [IWebAppDiagnosticsObjectInitialization 인터페이스](../../winscript/reference/iwebappdiagnosticsobjectinitialization-interface.md)합니다. 개체를 만든 후 [IWebAppDiagnosticsObjectInitialization::Initialize](../../winscript/reference/iwebappdiagnosticsobjectinitialization-initialize.md) PDM 디버그 응용 프로그램에 대 한 참조를 사용 하 여 호출 되 고 `hPassToObject` 의 매개 변수 `CreateObjectWithSiteAtWebApp`합니다. 이 메서드를 사용 하 여 익명 파이프를 사용 하 여 복사 된에 대 한 핸들을는 응용 프로그램에 전달할 [DuplicateHandle](http://go.microsoft.com/fwlink/?LinkId=232450)합니다.  
  
> [!IMPORTANT]
>  [IWebAppDiagnosticsSetup 인터페이스](../../winscript/reference/iwebappdiagnosticssetup-interface.md) 구현 PDM v11.0 이상에 됩니다. activdbg100.h에서 찾을 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```cpp  
HRESULT CreateObjectWithSiteAtWebApp(        [in] REFCLSID rclsid,         [in] DWORD dwClsContext,         [in] REFIID riid,         [in] DWORD_PTR hPassToObject        );  
```  
  
#### <a name="parameters"></a>매개 변수  
 `rclsid`  
 만들 클래스의 클래스 ID입니다.  
  
 `dwClsContext`  
 코드가 실행 되는 컨텍스트. 대부분의 경우에서 위해 CLSCTX_INPROC_SERVER 것합니다.  
  
 `riid`  
 사용되지 않습니다.  
  
 `hPassToObject`  
 전달 되는 개체에는 UI 스레드에서 만들어진 개체가 구현 하는 경우 값 [IWebAppDiagnosticsObjectInitialization 인터페이스](../../winscript/reference/iwebappdiagnosticsobjectinitialization-interface.md)합니다.