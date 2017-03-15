---
title: "방법: ASP.NET 프로세스의 이름 찾기 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "ASP.NET 디버깅, ASP.NET 프로세스"
  - "ASP.NET 프로세스"
ms.assetid: 931a7597-b0f0-4a28-931d-46e63344435f
caps.latest.revision: 29
caps.handback.revision: 29
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 방법: ASP.NET 프로세스의 이름 찾기
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

실행 중인 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 응용 프로그램에 연결하려면 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 프로세스의 이름을 알고 있어야 합니다.  
  
-   IIS 6.0 또는 IIS 7.0을 실행하는 경우 이 이름은 w3wp.exe입니다.  
  
-   이전 버전의 IIS를 실행하는 경우 이 이름은 aspnet\_wp.exe입니다.  
  
 [!INCLUDE[vsprvslong](../code-quality/includes/vsprvslong_md.md)] 이상 버전을 사용하여 빌드한 응용 프로그램의 경우 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 코드는 파일 시스템에 상주하며 WebDev.WebServer.exe 테스트 서버에서 실행될 수 있습니다.  이 경우 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 프로세스가 아닌 WebDev.WebServer.exe에 연결해야 합니다.  이 시나리오는 로컬 디버깅에만 적용됩니다.  
  
 이전 버전의 ASP 응용 프로그램은 in\-process로 실행되는 경우 IIS 프로세스 inetinfo.exe 내에서 실행됩니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다.  설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기**를 선택합니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
### 프로젝트 코드가 파일 시스템에 상주하는지 아니면 IIS에 상주하는지 확인하려면  
  
1.  Visual Studio에서 **솔루션 탐색기**가 열려 있지 않으면 엽니다.  
  
2.  응용 프로그램의 이름이 들어 있는 최상위 노드를 선택합니다.  
  
3.  **속성** 창 제목에 파일 경로가 표시되면 해당 응용 프로그램 코드는 파일 시스템에 상주합니다.  
  
     그렇지 않으면 **속성** 창 제목에 웹 사이트의 이름이 표시됩니다.  
  
### 응용 프로그램이 실행되는 IIS 버전을 확인하려면  
  
1.  **관리 도구**를 찾아서 실행합니다.  관리 도구는 사용 중인 운영 체제에 따라 **제어판** 내의 아이콘이나, **시작** 단추를 클릭할 때 나타나는 메뉴 항목으로 표시될 수 있습니다.  
  
     Windows XP의 경우 **제어판**이 종류별 보기나 클래식 보기로 표시될 수 있습니다.  종류별 보기에서 **관리 도구** 아이콘을 보려면 **클래식 보기로 전환** 또는 **성능 및 유지 관리**를 클릭해야 합니다.  
  
2.  **관리 도구**에서 IIS\(인터넷 정보 서비스\)를 실행합니다.  MMC 대화 상자가 나타납니다.  
  
3.  왼쪽 창에 컴퓨터 목록이 표시되면 응용 프로그램 코드가 상주하는 컴퓨터를 선택합니다.  
  
4.  IIS 버전은 오른쪽 창의 **버전** 열에 있습니다.  
  
## 참고 항목  
 [웹 응용 프로그램 원격 디버깅의 필수 구성 요소](../debugger/prerequistes-for-remote-debugging-web-applications.md)   
 [시스템 요구 사항](../debugger/aspnet-debugging-system-requirements.md)   
 [ASP.NET 디버깅 준비](../debugger/preparing-to-debug-aspnet.md)   
 [웹 응용 프로그램 및 스크립트 디버깅](../debugger/debugging-web-applications-and-script.md)