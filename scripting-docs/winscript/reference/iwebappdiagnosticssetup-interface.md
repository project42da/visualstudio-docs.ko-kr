---
title: "IWebAppDiagnosticsSetup 인터페이스 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-script-interfaces
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
helpviewer_keywords: IWebAppDiagnosticsSetup Interface
ms.assetid: ec7359f2-633e-4d59-b64b-9cab0134dfd0
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6e273f29bee6e4d2aae26c01c477373a735624c8
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iwebappdiagnosticssetup-interface"></a>IWebAppDiagnosticsSetup 인터페이스
이 인터페이스는 PDM 디버그 응용 프로그램 디버깅 중인 프로세스에서 COM 개체를 생성 하 고 웹 진단을 사용 하 여 구현 됩니다. PDM 디버깅 응용 프로그램 개체를 구현 하는 경우 [IObjectWithSite](http://go.microsoft.com/fwlink/?LinkId=232438), Internet Explorer 호출 [SetSite](http://go.microsoft.com/fwlink/?LinkId=232439) 을 만든 후에 그에 대 한 참조를 전달 [IWebBrowser2](http://go.microsoft.com/fwlink/?LinkId=232449). WWA 응용 프로그램 호출 [SetSite](http://go.microsoft.com/fwlink/?LinkId=232439) 및 패스는 WWA 인터페이스 IWebApplicationHost 대신 합니다. 경우 [SetSite](http://go.microsoft.com/fwlink/?LinkId=232439) 가 NULL이 아닌 값으로 호출 된 [IWebAppDiagnosticsSetup::DiagnosticsSupported](../../winscript/reference/iwebappdiagnosticssetup-diagnosticssupported.md) true를 반환 합니다. False를 반환 고에 대 한 호출이 그렇지 않은 경우 [IWebAppDiagnosticsSetup::CreateObjectWithSiteAtWebApp](../../winscript/reference/iwebappdiagnosticssetup-createobjectwithsiteatwebapp.md) 실패 합니다.  
  
> [!IMPORTANT]
>  `IWebAppDiagnosticsSetup`PDM v11.0 이상에 의해 구현 됩니다. activdbg100.h에서 찾을 수 있습니다.  
  
## <a name="methods"></a>메서드  
 이 인터페이스는 다음 메서드를 노출 합니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[IWebAppDiagnosticsSetup::CreateObjectWithSiteAtWebApp](../../winscript/reference/iwebappdiagnosticssetup-createobjectwithsiteatwebapp.md)|지정한 필터에 의해 숨겨져 있는 텍스트 문서를 가져옵니다.|  
|[IWebAppDiagnosticsSetup::DiagnosticsSupported](../../winscript/reference/iwebappdiagnosticssetup-diagnosticssupported.md)|지정된 된 문서가 노드의 자식 노드 중 하나에 속하는지 여부를 결정 합니다.|