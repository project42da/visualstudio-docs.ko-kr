---
title: "디버깅 준비: ASP.NET 웹 응용 프로그램 | Microsoft Docs"
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
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "디버깅[Visual Studio], 웹 응용 프로그램"
  - "ASP.NET 웹 응용 프로그램 디버깅"
ms.assetid: bcfb1080-98d1-42f9-96af-186fb14f232a
caps.latest.revision: 35
caps.handback.revision: 35
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 디버깅 준비: ASP.NET 웹 응용 프로그램
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

[!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 웹 사이트 템플릿은 Web Form 응용 프로그램을 만듭니다.  이 템플릿을 사용하여 웹 사이트를 만드는 경우 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서는 디버깅을 위한 기본 설정을 만듭니다.  **프로젝트 속성** 대화 상자에서 이 웹 페이지를 시작 페이지로 만들지 여부를 지정할 수 있습니다.  이러한 기본 설정을 적용하여 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 웹 사이트 디버깅을 시작하면 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서 Internet Explorer가 실행되고 디버거가 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 작업자 프로세스\(aspnet\_wp.exe 또는 w3wp.exe\)에 연결됩니다.  자세한 내용은 [시스템 요구 사항](../debugger/aspnet-debugging-system-requirements.md)을 참조하십시오.  
  
### Web Forms 응용 프로그램을 만들려면  
  
1.  **파일** 메뉴에서 **새 웹 사이트**를 선택합니다.  
  
2.  **새 웹 사이트** 대화 상자에서 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] **웹 사이트**를 선택합니다.  
  
3.  **확인**을 클릭합니다.  
  
### Web Form을 디버깅하려면  
  
1.  함수와 이벤트 처리기에서 하나 이상의 중단점을 설정합니다.  
  
     자세한 내용은 [Breakpoints and Tracepoints](http://msdn.microsoft.com/ko-kr/fe4eedc1-71aa-4928-962f-0912c334d583)을 참조하십시오.  
  
2.  중단점에 도달하면 함수 내부에서 코드를 단계별로 실행합니다.  문제가 해결될 때까지 코드의 실행을 확인합니다.  
  
     자세한 내용은 [Stepping](http://msdn.microsoft.com/ko-kr/8791dac9-64d1-4bb9-b59e-8d59af1833f9) 및 [웹 응용 프로그램 및 스크립트 디버깅](../debugger/debugging-web-applications-and-script.md)을 참조하십시오.  
  
## 기본 구성 변경  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서 만든 기본 디버그 및 릴리스 구성을 변경해야 하는 경우 이를 수행할 수 있습니다.  자세한 내용은 [방법: 디버그 및 릴리스 구성 설정](../debugger/how-to-set-debug-and-release-configurations.md)을 참조하십시오.  
  
#### 기본 디버그 구성을 변경하려면  
  
1.  **솔루션 탐색기**에서 웹 사이트를 마우스 오른쪽 단추로 클릭하고 **속성 페이지**를 선택하여 **속성 페이지** 대화 상자를 엽니다.  
  
2.  **시작 옵션**을 클릭합니다.  
  
3.  처음에 표시하려는 웹 페이지로 **시작 작업**을 설정합니다.  
  
4.  **디버거** 아래에서 **ASP.NET 디버깅**이 선택되어 있는지 확인합니다.  
  
     자세한 내용은 [웹 프로젝트에 대한 속성 페이지 설정](../debugger/property-pages-settings-for-web-projects.md)을 참조하십시오.  
  
## 참고 항목  
 [디버그 설정 및 준비](../debugger/debugger-settings-and-preparation.md)   
 [디버거 기본 사항](../debugger/debugger-basics.md)   
 [디버거 보안](../debugger/debugger-security.md)   
 [관리 코드 디버깅](../debugger/debugging-managed-code.md)