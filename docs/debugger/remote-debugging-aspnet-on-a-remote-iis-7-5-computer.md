---
title: "원격 IIS 7.5 컴퓨터의 원격 디버깅 ASP.NET | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "hero-article"
ms.assetid: 573a3fc5-6901-41f1-bc87-557aa45d8858
caps.latest.revision: 8
caps.handback.revision: 3
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 원격 IIS 7.5 컴퓨터의 원격 디버깅 ASP.NET
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

IIS 7.5가 있는 Windows Server 2008 R2 컴퓨터에 ASP.NET 웹 응용 프로그램을 배포하고 원격 디버깅에 대해 설정할 수 있습니다. 다음 지침에서는 Visual Studio 2015 MVC 4.5.2 응용 프로그램을 설정 및 구성하는 방법을 설명합니다.  
  
## Visual Studio 컴퓨터에서 응용 프로그램 만들기  
  
1.  새 MVC ASP.NET 응용 프로그램을 만듭니다.**파일 \/ 새로 만들기 \/ 프로젝트**, **Visual C\# \/ 웹 \/ ASP.NET 웹 응용 프로그램**을 차례로 선택합니다.**ASP.NET 4.5.2** 템플릿 섹션에서 **MVC**를 선택합니다.**Microsoft Azure 웹앱 구성** 페이지를 취소합니다. 이름을 **MyMVC**로 지정합니다.  
  
2.  HomeController.cs 파일을 열고 `About()` 메서드에 중단점을 설정합니다.  
  
3.  **솔루션 탐색기**에서 프로젝트 노드를 마우스 오른쪽 단추로 클릭하고 **게시**를 선택합니다.  
  
4.  **게시 대상 선택**에 대해 **사용자 지정**을 선택하고 프로필 이름을 **MyMVC**로 지정합니다.**다음**을 클릭합니다.  
  
5.  **연결** 탭에서 **게시 방법** 필드를 **파일 시스템**으로 설정하고 **대상 위치** 필드를 로컬 디렉터리로 설정합니다.**다음**을 클릭합니다.  
  
6.  구성을 **디버그**로 설정합니다.**게시**를 클릭합니다.  
  
     로컬 디렉터리에 응용 프로그램을 게시해야 합니다.  
  
## Windows Server 원격 컴퓨터에 응용 프로그램 배포  
 이 섹션에서는 Windows Server 2008 R2 컴퓨터에서 IIS를 이미 사용할 수 있다고 가정합니다.  
  
1.  ASP.NET을 설치합니다.  
  
     **C:\\Windows\\Microsoft.NET\\Framework\(64\)\\v4.0.30319\\aspnet\_regiis.exe \-ir**  
  
2.  Visual Studio 컴퓨터의 ASP.NET 프로젝트 디렉터리를 Windows Server 컴퓨터의 로컬 디렉터리\(**C:\\Publish**라고 함\)에 복사합니다.  
  
3.  web.config 파일에 올바른 버전의 .NET Framework가 표시되는지 확인합니다.  기본적으로 이 컴퓨터에 설치되는 .NET Framework 버전은 4.0.30319지만 ASP.NET 4.5.2 버전을 만들었습니다. 이 버전이 Windows Server 컴퓨터에 설치되어 있지 않으면 버전을 변경해야 합니다.  
  
    ```xml  
    <system.web> <authentication mode="None" /> <compilation debug="true" targetFramework="4.0.30319" /> <httpRuntime targetFramework="4.0.30319" /> </system.web>  
  
    ```  
  
4.  **IIS\(인터넷 정보 서비스\) 관리자**를 열고 **사이트**로 이동합니다.  
  
5.  **기본 웹 사이트** 노드를 마우스 오른쪽 단추로 클릭하고 **응용 프로그램 추가**를 선택합니다.  
  
6.  **별칭** 필드를 **MyMVC**로 설정하고 응용 프로그램 풀 필드를 **ASP.NET v4.0**으로 설정합니다.**실제 경로**를 **C:\\Publish**\(ASP.NET 프로젝트 디렉터리를 복사한 위치\)로 설정합니다.  
  
7.  배포를 테스트하려면 **기본 웹 사이트**를 마우스 오른쪽 단추로 클릭하고 **찾아보기**를 선택합니다. 웹 페이지가 표시됩니다.  
  
## Windows Server 컴퓨터에 원격 디버거 설치  
 원격 디버거를 다운로드하는 방법에 대한 지침은 [원격 디버깅](../debugger/remote-debugging.md)을 참조하세요.  
  
 ASP.NET 응용 프로그램의 원격 디버깅을 수행하려면 원격 디버거를 서비스로 시작하거나 관리자 권한으로 원격 디버거 응용 프로그램을 실행합니다. 원격 디버거를 서비스로 실행하는 방법에 대한 자세한 내용은 [원격 디버깅](../debugger/remote-debugging.md)에서 확인할 수 있습니다.  
  
## Visual Studio 컴퓨터에서 ASP.NET 응용 프로그램에 연결  
  
-   Visual Studio 컴퓨터에서 **MyMVC** 솔루션을 엽니다.  
  
-   Visual Studio에서 **디버그 \/ 프로세스에 연결**을 클릭합니다.  
  
-   한정자 필드를 **\<원격 컴퓨터 이름\>:4020**으로 설정합니다.  
  
-   일부 프로세스가 **사용 가능한 프로세스** 창에 표시됩니다.  
  
-   **모든 사용자의 프로세스 표시**를 선택합니다.  
  
-   **w3wp.exe**를 찾은 다음 **연결**을 클릭합니다.  
  
-   원격 컴퓨터의 웹 사이트를 엽니다. 브라우저에서 **http:\/\/\<원격 컴퓨터 이름\>**으로 이동합니다.  
  
-   ASP.NET 웹 페이지가 표시됩니다.**정보**를 클릭합니다.  
  
     Visual Studio에서 중단점이 적중됩니다.