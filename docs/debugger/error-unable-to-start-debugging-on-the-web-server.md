---
title: "오류: 웹 서버에서 디버깅을 시작할 수 없습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.debug.error.http"
  - "vwd.nonadmin.error."
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "디버거, 웹 응용 프로그램 오류"
  - "디버깅[Visual Studio], 오류"
  - "ASP.NET 웹 응용 프로그램 디버깅, 디버깅 시작 실패 오류"
  - "오류[디버거], 디버깅을 시작할 수 없습니다."
  - "HTTP 서버, 디버깅 오류"
  - "인터넷 정보 서비스, DLL 디버깅"
  - "원격 디버깅, 오류"
  - "보안[디버거], 웹 응용 프로그램"
  - "보안 설정, 기본 웹 사이트 확인"
  - "디버깅 시작 실패 오류"
ms.assetid: f62e378a-3a99-4f78-9d97-8bb63a4da181
caps.latest.revision: 31
caps.handback.revision: 27
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 오류: 웹 서버에서 디버깅을 시작할 수 없습니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

웹 서버에서 실행 중인 ASP.NET 응용 프로그램을 디버깅하려고 하면 ‘웹 서버에서 디버깅을 시작할 수 없습니다.’라는 오류 메시지가 표시될 수 있습니다.  
  
 대부분의 경우 이 오류는 IIS가 올바르게 구성되지 않은 경우에 발생합니다.  
  
##  <a name="vxtbshttpservererrorsthingstocheck"></a> IIS가 제대로 구성되어 있는지 확인  
 MVC 5 앱에서 IIS 8에 배포하는 방법에 대한 자세한 내용은 [IIS에 게시](https://docs.asp.net/en/latest/publishing/iis.html)를 참조하세요.  
  
 IIS7.5에 배포하는 방법에 대한 자세한 내용은 [원격 IIS 7.5 컴퓨터의 원격 디버깅 ASP.NET](../debugger/remote-debugging-aspnet-on-a-remote-iis-7-5-computer.md)을 참조하세요.  
  
##  <a name="vxtbshttpservererrorswebapplicationsonremoteservers"></a> Visual Studio 원격 도구가 설치되어 있는지 확인  
 원격 웹 서버에서 디버깅하려면 Visual Studio 원격 도구를 설치해야 합니다. 원격 도구를 다운로드하여 설치하는 방법에 대한 자세한 내용은 [원격 디버깅](../debugger/remote-debugging.md)을 참조하세요.  
  
##  <a name="vxtbshttpservererrorsanchor2"></a> ASP.NET이 설치되어 있는지 확인  
 **IIS 8**  
  
 IIS 8의 경우 ASP.NET을 IIS의 일부로 설치합니다.  
  
1.  **서버 관리자** 타일에서 **대시보드**를 선택하고 **역할 및 기능 추가**를 클릭합니다.  
  
2.  **설치 유형** 페이지에서 **역할 기반 또는 기능 기반 설치**를 선택하고 **다음**을 클릭합니다.  
  
3.  **대상 서버 선택** 페이지에서 **서버 풀에서 서버 선택**을 선택하고 서버를 선택한 후 **다음**을 클릭합니다.  
  
4.  **서버 역할 선택** 페이지에서 **웹 서버\(IIS\)**를 선택하고 **다음**을 클릭합니다.  
  
5.  **기능 선택 페이지**에서 **다음**을 클릭합니다.  
  
6.  **웹 서버 역할\(IIS\)** 페이지에서 **다음**을 클릭합니다.  
  
7.  **역할 서비스 선택** 페이지에서 기본적으로 설치되는 미리 선택된 역할 서비스에 유의하고 **응용 프로그램 서버** 노드, **.NET Framework 4.5** 노드를 차례로 확장한 다음 **ASP.NET 4.5**를 선택합니다. .NET 3.5를 설치한 경우 **ASP.NET 3.5**도 선택합니다.  
  
8.  **설치 선택 확인** 페이지에서 **설치**를 클릭합니다.  
  
9. **설치 진행률** 페이지에서 웹 서버 \(IIS\) 역할 및 필수 역할 서비스가 설치되었는지 확인한 다음 **닫기**를 클릭합니다.  
  
 **IIS 7.5 이전 버전**  
  
 IIS 7.5 이전 버전의 경우 명령 프롬프트 창에서 다음 명령을 실행합니다.  
  
```  
systemroot\Microsoft.NET\Framework\ versionNumber \aspnet_regiis -i   
```  
  
## 기본 문제 해결  
 ASP.NET 응용 프로그램이 올바르게 배포되는지 확인하기 위해 다음과 같은 작업을 수행할 수 있습니다.  
  
## 브라우저에서 localhost 페이지 표시  
 IIS가 올바르게 설치되어 있지 않은 경우 브라우저에 `http://localhost`를 입력하면 오류가 발생합니다.  
  
## 브라우저에서 웹 페이지 표시  
 웹 브라우저를 시작하고 디버깅하려는 페이지의 URL\(예: `http://localhost/MyWebApplication`\)을 입력합니다. IIS가 올바르게 구성되지 않았거나 ASP.NET 응용 프로그램이 제대로 배포되지 않은 경우 IIS 설정 및 ASP.NET 배포 문제를 해결하는 데 도움이 되는 오류 메시지가 표시됩니다.  
  
## 서버에서 기본 ASP.NET 응용 프로그램 만들기  
 서버에서 로컬로 기본 ASP.NET 응용 프로그램을 만들어 디버깅해 보세요.  
  
## IP 주소만 사용하는 경우의 인증 오류 해결  
 웹 서버 디버깅에는 NTLM 인증이 필요합니다. 기본적으로 IP 주소는 인터넷의 일부로 인식되는데 인터넷에서는 NTLM 인증을 수행할 수 없습니다. 이 문제를 해결하려면 원격 컴퓨터의 이름을 지정할 수 있습니다.  
  
##  <a name="vxtbshttpservererrorsmanuallyattaching"></a> 프로세스에 수동으로 연결  
 여전히 디버깅을 시작할 때 오류 메시지가 나타나면 수동으로 프로세스에 연결하여 디버깅을 시도할 수 있습니다.  
  
-   디버깅하지 않고 응용 프로그램을 시작합니다.**디버그** 메뉴에서 **디버깅하지 않고 시작**을 선택합니다.  
  
-   **디버그\/프로세스에 연결**을 클릭합니다.  창이 표시되면 **모든 사용자의 프로세스 표시**를 사용하도록 설정합니다.  
  
-   적절한 프로세스를 찾아서 연결합니다. MVC 5 이전 ASP.NET 앱의 경우 프로세스는 w3wp.exe입니다. MVC 5의 경우 [IIS에 게시](https://docs.asp.net/en/latest/publishing/iis.html)를 참조하세요.  
  
## 참고 항목  
 [웹 응용 프로그램 디버깅: 오류 및 문제 해결](../debugger/debugging-web-applications-errors-and-troubleshooting.md)