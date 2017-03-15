---
title: "ClickOnce 배포 시 서버 및 클라이언트 구성 문제 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-deployment"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "ClickOnce 배포, 문제 해결"
  - "응용 프로그램 배포, ClickOnce"
  - "ClickOnce 배포 문제 해결"
  - "Windows 응용 프로그램, ClickOnce 배포"
ms.assetid: 929e5fcc-dd56-409c-bb57-00bd9549b20b
caps.latest.revision: 33
caps.handback.revision: 33
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# ClickOnce 배포 시 서버 및 클라이언트 구성 문제
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Windows Server에서 IIS\(인터넷 정보 서비스\)를 사용하는 경우 Microsoft Word 파일 같이 Windows에서 인식할 수 없는 파일 형식이 배포에 포함되어 있으면 IIS에서 이 파일의 전송을 거부하므로 배포에 실패합니다.  
  
 또한 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 같은 일부 웹 서버 및 웹 응용 프로그램 소프트웨어에는 다운로드할 수 없는 파일 및 파일 형식의 목록이 들어 있습니다.  예를 들어, [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)]에서는 모든 Web.config 파일의 다운로드를 방지합니다.  이러한 파일에는 사용자 이름과 암호 같은 중요한 정보가 포함되어 있을 수 있습니다.  
  
 이러한 제한으로 인해 매니페스트와 어셈블리 같은 핵심 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 파일을 다운로드하는 데는 문제가 없더라도 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램의 일부로 포함된 데이터 파일을 다운로드하지 못할 수 있습니다.  [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)]의 경우 IIS 구성 관리자에서 해당 파일의 다운로드를 금지하는 처리기를 제거하면 이 오류를 해결할 수 있습니다.  자세한 내용은 IIS 서버 설명서를 참조하십시오.  
  
 일부 웹 서버에서는 확장명이 .dll, .config, .mdf 등인 파일을 차단할 수 있습니다.  Windows 기반 응용 프로그램에는 보통 이와 같은 확장명을 가진 파일이 포함되어 있습니다.  사용자가 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램을 실행하여 웹 서버의 차단된 파일에 액세스하려고 하면 오류가 발생합니다.  이 경우 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]에서는 모든 파일 확장명을 차단 해제하는 것이 아니라 기본적으로 파일 확장명이 ".deploy"인 모든 응용 프로그램 파일을 게시합니다.  따라서 관리자는 다음 세 가지 파일 확장명이 차단되지 않도록 웹 서버를 구성하기만 하면 됩니다.  
  
-   .application  
  
-   .manifest  
  
-   .deploy  
  
 그러나 웹 서버에서 응용 프로그램에 사용되는 모든 파일 확장명을 차단하지 않도록 구성해야 하는 경우에는 [Publish Options Dialog Box](http://msdn.microsoft.com/ko-kr/fd9baa1b-7311-4f9e-8ffb-ae50cf110592)에서 **".deploy" 파일 확장명 사용** 옵션의 선택을 취소하여 이 옵션을 사용하지 않을 수 있습니다.  
  
 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]를 설치하지 않고 IIS를 사용하거나 Apache 등 다른 웹 서버를 사용하는 경우에는 .manifest, .application 및 .deploy를 구성해야 합니다.  
  
## ClickOnce 및 SSL\(Secure Sockets Layer\)  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램은 Internet Explorer에서 SSL 인증서에 대한 프롬프트를 표시하는 경우를 제외하면 SSL에서 문제 없이 작동합니다.  사이트 이름이 일치하지 않거나 인증서가 만료되는 등 인증서에 문제가 있는 경우 프롬프트가 표시될 수 있습니다.  SSL 연결을 통해 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]가 작동하도록 하려면 최신 인증서가 있는지와 인증서 데이터가 사이트 데이터와 일치하는지를 확인합니다.  
  
## ClickOnce 및 프록시 인증  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]는 .NET Framework 3.5부터 Windows 통합 프록시 인증을 지원합니다.  특정 machine.config 지시문이 필요하지 않습니다.  [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]는 Basic이나 Digest 등의 다른 인증 프로토콜은 지원하지 않습니다.  
  
 또한 .NET Framework 2.0에 핫픽스를 적용하여 이 기능을 사용하도록 설정할 수도 있습니다.  자세한 내용은 http:\/\/go.microsoft.com\/fwlink\/?LinkId\=158730을 참조하십시오.  
  
 자세한 내용은 [\<defaultProxy\> 요소\(네트워크 설정\)](../Topic/%3CdefaultProxy%3E%20Element%20\(Network%20Settings\).md)를 참조하십시오.  
  
## ClickOnce 및 웹 브라우저 호환성  
 현재는 배포 매니페스트에 대한 URL이 Internet Explorer를 사용하여 열린 경우에만 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 설치가 시작됩니다.  배포 URL이 Microsoft Office Outlook 등의 다른 응용 프로그램에서 시작될 경우에는 Internet Explorer가 기본 웹 브라우저로 설정된 경우에만 배포가 올바르게 시작됩니다.  
  
> [!NOTE]
>  Mozilla Firefox는 배포 공급자가 비어 있지 않거나 Microsoft .NET Framework Assistant 확장이 설치된 경우에 지원됩니다.  이 확장은 .NET Framework 3.5 SP1과 함께 패키지되어 있습니다.  XBAP 지원의 경우 NPWPF 플러그 인은 필요할 때 활성화됩니다.  
  
## 브라우저 스크립팅을 통한 ClickOnce 응용 프로그램 활성화  
 액티브 스크립팅을 사용하여 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램을 시작하는 사용자 지정 웹 페이지를 개발한 경우 일부 컴퓨터에서 해당 응용 프로그램이 시작되지 않는 경우가 있을 수 있습니다.  Internet Explorer에는 이 동작에 영향을 주는 **파일 다운로드 시 자동으로 사용자에게 확인**이라는 설정이 있습니다.  이 동작에 영향을 주는 이 설정은 **옵션** 메뉴의 **보안** 탭에서 사용할 수 있습니다.  이 설정을 **파일 다운로드 시 자동으로 사용자에게 확인**이라고 하고 **다운로드** 범주 아래에 표시됩니다.  이 속성은 기본적으로 인트라넷 웹 페이지의 경우 **사용**으로, 인터넷 웹 페이지의 경우 **사용 안 함**으로 설정됩니다.  이 설정을 **사용 안 함**으로 설정하면 해당 URL을 `document.location` 속성에 할당하는 경우와 같이 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램을 프로그래밍 방식으로 활성화하려는 모든 시도가 차단됩니다.  이 경우 사용자는 응용 프로그램의 URL로 설정된 하이퍼링크를 클릭하는 경우와 같이 사용자가 시작한 다운로드를 통해서만 응용 프로그램을 시작할 수 있습니다.  
  
## 추가적인 서버 구성 문제  
  
##### 관리자 권한 필요  
 HTTP를 사용하여 게시할 경우 대상 서버에 대한 관리자 권한이 있어야 합니다.  IIS에는 이 권한 수준이 있어야 합니다.  HTTP를 사용하여 게시하지 않는 경우에는 대상 경로에 대한 쓰기 권한만 있으면 됩니다.  
  
##### 서버 인증 문제  
 "익명 액세스"를 해제하고 원격 서버에 게시하는 경우 다음과 같은 경고를 받게 됩니다.  
  
```  
"The files could not be downloaded from http://<remoteserver>/<myapplication>/.  The remote server returned an error: (401) Unauthorized."  
```  
  
> [!NOTE]
>  사이트에서 기본 자격 증명이 아닌 다른 자격 증명을 입력하라는 메시지를 표시하는 경우 NTLM\(NT challenge\-response\) 인증이 작동하도록 할 수 있으며, 보안 대화 상자에서 제공된 자격 증명을 앞으로의 세션을 위해 저장할 것인지 묻는 메시지가 표시되면 **확인**을 클릭합니다.  그러나 기본 인증의 경우에는 이 방법으로 해결되지 않습니다.  
  
## 타사 웹 서버 사용  
 IIS가 아닌 다른 웹 서버에서 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램을 배포하는 경우 서버가 배포 매니페스트 및 응용 프로그램 매니페스트와 같은 주요 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 파일에 대해 잘못된 콘텐츠 형식을 반환하면 문제가 발생할 수 있습니다.  이 문제를 해결하려면 웹 서버의 도움말 설명서에 있는 서버에 새 콘텐츠 형식을 추가하는 방법을 참조하여 다음 표에 나열된 모든 파일 확장명 매핑이 해당 위치에 있는지 확인합니다.  
  
|파일 확장명|콘텐츠 형식|  
|------------|------------|  
|`.application`|`application/x-ms-application`|  
|`.manifest`|`application/x-ms-manifest`|  
|`.deploy`|`application/octet-stream`|  
|`.msu`|`application/octet-stream`|  
|`.msp`|`application/octet-stream`|  
  
## ClickOnce 및 매핑된 드라이브  
 Visual Studio를 사용하여 ClickOnce 응용 프로그램을 게시하는 경우 매핑된 드라이브를 설치 위치로 지정할 수 없습니다.  그러나 매니페스트 생성기 및 편집기\(Mage.exe 및 MageUI.exe\)를 사용하여 매핑된 드라이브에서 설치하도록 ClickOnce 응용 프로그램을 수정할 수 있습니다.  자세한 내용은 [Mage.exe\(매니페스트 생성 및 편집 도구\)](../Topic/Mage.exe%20\(Manifest%20Generation%20and%20Editing%20Tool\).md) 및 [MageUI.exe \(매니페스트 생성 및 편집 도구, 그래픽 클라이언트\)](../Topic/MageUI.exe%20\(Manifest%20Generation%20and%20Editing%20Tool,%20Graphical%20Client\).md)를 참조하십시오.  
  
## 응용 프로그램 설치에 지원되지 않는 FTP 프로토콜  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]는 모든 HTTP 1.1 웹 서버 또는 파일 서버에서의 응용 프로그램 설치를 지원하지만  FTP\(파일 전송 프로토콜\)는 응용 프로그램 설치에 지원되지 않습니다.  FTP를 응용 프로그램을 게시하는 데만 사용할 수 있습니다.  다음 표에서는 이러한 차이점을 요약하여 보여 줍니다.  
  
|URL 형식|설명|  
|------------|--------|  
|ftp:\/\/|이 프로토콜을 사용하여 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램을 게시할 수 있습니다.|  
|http:\/\/|이 프로토콜을 사용하여 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램을 설치할 수 있습니다.|  
|https:\/\/|이 프로토콜을 사용하여 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램을 설치할 수 있습니다.|  
|file:\/\/|이 프로토콜을 사용하여 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램을 설치할 수 있습니다.|  
  
## Windows XP SP2: Windows 방화벽  
 기본적으로 Windows XP SP2는 Windows 방화벽을 사용합니다.  Windows XP가 설치된 컴퓨터에서 응용 프로그램을 개발하는 경우에도 IIS를 실행하고 있는 로컬 서버에서 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램을 게시 및 실행할 수는 있습니다.  그러나 Windows 방화벽을 열지 않으면 다른 컴퓨터에서 IIS를 실행하고 있는 서버에 액세스할 수 없습니다.  Windows 도움말에서 Windows 방화벽 관리에 대한 지침을 참조하십시오.  
  
## Windows Server: FrontPage Server Extensions 사용  
 HTTP를 사용하는 Windows 웹 서버에 응용 프로그램을 게시하려면 Microsoft의 FrontPage Server Extensions가 있어야 합니다.  
  
 기본적으로 Windows Server에는 FrontPage Server Extensions가 설치되어 있지 않습니다.  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서 FrontPage Server Extensions를 통해 HTTP를 사용하는 Windows Server 웹 서버에 게시하려는 경우 우선 FrontPage Server Extensions를 설치해야 합니다.  Windows Server의 사용자 서버 관리라는 관리 도구를 사용하여 설치를 수행할 수 있습니다.  
  
## Windows Server: 잠겨 있는 콘텐츠 형식  
 [!INCLUDE[WinXPSvr](../debugger/includes/winxpsvr_md.md)]의 IIS에서는 알려진 일부 콘텐츠 형식\(예: .htm, .html, .txt 등\)을 제외한 모든 파일 형식이 잠겨 있습니다.  이 서버를 사용하여 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램을 배포하려면 .application, .manifest를 비롯하여 응용 프로그램에서 사용하는 다른 모든 사용자 지정 형식의 파일을 다운로드할 수 있도록 IIS 설정을 변경해야 합니다.  
  
 IIS 서버를 사용하여 배포할 경우 inetmgr.exe를 실행하고 기본 웹 페이지의 새 파일 형식을 추가합니다.  
  
-   .application 및 .manifest 확장명에 대한 MIME 형식은 "application\/x\-ms\-application"이어야 합니다. 다른 파일 형식에 대한 MIME 형식은 "application\/octet\-stream"입니다.  
  
-   확장명이 "\*"인 MIME 형식과 "application\/octet\-stream"인 MIME 형식을 만들면 차단되지 않은 형식의 파일을 다운로드할 수 있습니다.  그러나 .aspx 및 .asmx 같은 차단된 파일 형식은 다운로드할 수 없습니다.  
  
 Windows Server의 MIME 형식 구성과 관련된 지침은 [http:\/\/support.microsoft.com\/kb\/326965\/ko\-kr](http://support.microsoft.com/kb/326965/ko-kr)에 있는 Microsoft 기술 자료 문서 KB326965 "IIS 6.0에서는 알 수 없는 MIME 형식을 처리하지 않는다"를 참조하십시오.  
  
## 콘텐츠 형식 매핑  
 HTTP를 통해 게시하는 경우 .application 파일의 콘텐츠 형식\(MME 형식이라고도 함\)은 application\/x\-ms\-application이어야 합니다. 서버에 [!INCLUDE[dnprdnlong](../code-quality/includes/dnprdnlong_md.md)]이 설치되어 있으면 MIME 형식이 자동으로 설정됩니다.  그러나 설치되어 있지 않으면 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램 vroot나 전체 서버에 대해 MIME 형식 연결을 만들어야 합니다.  
  
 IIS 서버를 사용하여 배포하는 경우 inetmgr.exe를 실행하고 .application 확장명의 새 콘텐츠 형식 "application\/x\-ms\-application"을 추가합니다.  
  
## HTTP 압축 문제  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]를 사용하면 GZIP 알고리즘을 통해 데이터 스트림을 압축한 다음 클라이언트에 보내는 웹 서버 기술인 HTTP 압축을 사용하는 다운로드를 수행할 수 있습니다.  클라이언트\(이 경우 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]\)에서는 파일을 읽기 전에 스트림의 압축을 해제합니다.  
  
 IIS를 사용하는 경우 HTTP 압축을 쉽게 활성화할 수 있습니다.  그러나, HTTP 압축은 특정 파일 형식, 즉 HTML 및 텍스트 파일에 대해서만 활성화됩니다.  어셈블리\(.dll\), XML\(.xml\), 배포 매니페스트\(.application\) 및 응용 프로그램 매니페스트\(.manifest\)에 대해 압축을 활성화하려면 이러한 파일 형식을 IIS의 압축할 형식 목록에 추가해야 합니다.  파일 형식을 배포에 추가할 때까지는 텍스트와 HTML 파일만 압축됩니다.  
  
 IIS에 대한 자세한 지침은 [HTTP 압축을 위해 추가 문서 형식을 지정하는 방법](http://go.microsoft.com/fwlink/?LinkId=178459)을 참조하십시오.  
  
## 참고 항목  
 [ClickOnce 배포 문제 해결](../deployment/troubleshooting-clickonce-deployments.md)   
 [ClickOnce 배포 전략 선택](../deployment/choosing-a-clickonce-deployment-strategy.md)   
 [응용 프로그램 배포 필수 구성 요소](../deployment/application-deployment-prerequisites.md)