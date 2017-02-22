---
title: "방법: 웹 응용 프로그램 디버깅 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "ASP.NET Web Forms, 디버깅"
  - "ASP.NET, 웹 응용 프로그램 디버깅"
  - "ASP.NET 웹 응용 프로그램 디버깅, 개발 중"
  - "웹 서비스, 디버깅"
ms.assetid: 6440d12e-6b29-42c5-a958-99aeaaff480f
caps.latest.revision: 37
caps.handback.revision: 37
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 방법: 웹 응용 프로그램 디버깅
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

[!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)]은 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서 웹 응용 프로그램을 개발하는 기본 기술입니다.  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 디버거에서는 로컬 컴퓨터 또는 원격 서버에서 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 웹 응용 프로그램을 디버깅하는 강력한 도구를 제공합니다.  이 항목에서는 개발 중에 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 프로젝트를 디버깅하는 방법에 대해 설명합니다.  이미 프로덕션 서버에 배포된 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 웹 응용 프로그램을 디버깅하는 방법에 대한 자세한 내용은 [배포된 웹 응용 프로그램 디버깅](../debugger/debugging-deployed-web-applications.md)을 참조하십시오.  
  
 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 응용 프로그램을 디버깅하려면  
  
-   필요한 권한이 있어야 합니다.  자세한 내용은 [시스템 요구 사항](../debugger/aspnet-debugging-system-requirements.md)을 참조하십시오.  
  
-   [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 디버깅이 **프로젝트 속성**에서 활성화되어 있어야 합니다.  
  
-   응용 프로그램의 구성 파일\(Web.config\)이 디버그 모드로 설정되어 있어야 합니다.  디버그 모드를 설정하면 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)]에서 동적으로 생성된 파일에 대한 기호를 만들고 디버거가 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 응용 프로그램에 연결할 수 있도록 합니다.  웹 프로젝트 템플릿에서 프로젝트를 만든 경우 디버깅을 시작하면 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]가 이를 자동으로 설정합니다.  
  
-   자세한 내용은 [방법: ASP.NET 응용 프로그램에 디버깅 사용](../debugger/how-to-enable-debugging-for-aspnet-applications.md)을 참조하십시오.  
  
### 개발하는 동안 웹 응용 프로그램을 디버깅하려면  
  
1.  **디버그** 메뉴에서 **시작**을 클릭하여 웹 응용 프로그램 디버깅을 시작합니다.  
  
     [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서 웹 응용 프로그램 프로젝트를 빌드하고 필요한 경우 이 응용 프로그램을 배포한 다음, 사용자가 로컬로 디버깅하는 경우 ASP.NET Development Server를 시작하고 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 작업자 프로세스에 연결합니다.  
  
2.  다른 응용 프로그램을 디버깅할 때처럼 디버거를 사용하여 중단점을 설정하거나 지우고 단계별로 실행하며 기타 디버깅 작업을 수행합니다.  
  
     자세한 내용은 [디버거 기본 사항](../debugger/debugger-basics.md)을 참조하십시오.  
  
3.  디버깅 세션을 종료하려면 **디버그** 메뉴에서 **디버깅 중지**를 클릭하거나 Internet Explorer의 **파일** 메뉴에서 **닫기**를 클릭합니다.  
  
## 참고 항목  
 [웹 응용 프로그램 및 스크립트 디버깅](../debugger/debugging-web-applications-and-script.md)   
 [ASP.NET 및 AJAX 응용 프로그램 디버깅](../debugger/debugging-aspnet-and-ajax-applications.md)   
 [방법: ASP.NET 응용 프로그램에 디버깅 사용](../debugger/how-to-enable-debugging-for-aspnet-applications.md)