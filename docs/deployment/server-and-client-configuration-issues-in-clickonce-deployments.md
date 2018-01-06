---
title: "서버 및 클라이언트 구성 문제 ClickOnce 배포에서 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- C++
helpviewer_keywords:
- deploying applications, ClickOnce
- troubleshooting ClickOnce deployments
- ClickOnce deployment, troubleshooting
- Windows applications, ClickOnce deployments
ms.assetid: 929e5fcc-dd56-409c-bb57-00bd9549b20b
caps.latest.revision: "33"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload: multiple
ms.openlocfilehash: b50dbe51f58af79b8c1074c592f98abccbe8ba7e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="server-and-client-configuration-issues-in-clickonce-deployments"></a>ClickOnce 배포 시 서버 및 클라이언트 구성 문제
인터넷 정보 서비스 (IIS)를 사용 하 여 Windows Server에서 배포에는 Windows에서 인식 하지 못하는 파일 형식을 포함 하는 경우 해당 파일을 전송 하는 데 Microsoft Word 파일을 같은 IIS 거부 합니다 및 배포에 실패 합니다.  
  
 일부 웹 서버 및 웹 응용 프로그램 소프트웨어를 같은 또한 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)], 파일 목록이 포함 되어 및 파일 형식을 다운로드할 수 없습니다. 예를 들어 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 모든 Web.config 파일의 다운로드를 차단 합니다. 이러한 파일에는 사용자 이름 및 암호 같은 중요 한 정보가 포함 될 수 있습니다.  
  
 이러한 제한 인해 코어를 다운로드 하는 데는 문제가 없지만 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 매니페스트 및 어셈블리와 같은 파일을이 제한으로 인해 수의 일부로 포함 된 데이터 파일을 다운로드 하면 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램입니다. [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)], IIS 구성 관리자에서 해당 파일의 다운로드를 금지 하는 처리기를 제거 하 여이 오류를 해결할 수 있습니다. 자세한 내용은 IIS 서버 설명서를 참조 하십시오.  
  
 일부 웹 서버에.dll,.config 등.mdf 확장명의 파일을 차단할 수 있습니다. Windows 기반 응용 프로그램에는 일반적으로 이러한 확장 중 일부가 파일 포함 됩니다. 사용자가을 실행 하는 경우는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 웹 서버에서 차단된 된 파일에 액세스 하는 응용 프로그램 오류가 발생 합니다. 모든 파일 확장명을 차단 하지 않는 대신 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 기본적으로 모든 응용 프로그램 파일이 ".deploy" 파일 확장명으로 게시 합니다. 따라서 관리자가 다음과 같은 세 가지 파일 확장명을 차단 해제 하도록 웹 서버를 구성 해야 하는:  
  
-   .application  
  
-   .manifest  
  
-   .deploy  
  
 그러나이 옵션 선택을 취소 하 여 해제할 수 있습니다는 **".deploy" 파일 확장명을 사용 하 여** 옵션에 [게시 옵션 대화 상자](http://msdn.microsoft.com/en-us/fd9baa1b-7311-4f9e-8ffb-ae50cf110592), 모든 파일 확장명을 차단 해제 하려면 웹 서버를 구성 해야 하는 경우 응용 프로그램에 사용 합니다.  
  
 IIS를 설치 하지 않은 위치를 사용 하는 경우.manifest,.application, 및 예를 들어.deploy를 구성 해야 할 됩니다는 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)], 또는 다른 웹 서버 (예를 들어 Apache)를 사용 하는 경우.  
  
## <a name="clickonce-and-secure-sockets-layer-ssl"></a>ClickOnce 및 Secure Sockets Layer (SSL)  
 A [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램이 제대로 작동 하므로 SSL을 통해 Internet Explorer를 SSL 인증서에 대 한 프롬프트를 발생 하는 때를 제외 하 고 있습니다. 프롬프트는 만료 된 경우 사이트 이름이 일치 하지 않는 같은 인증서 또는 인증서에 문제가 있을 때 발생할 수 있습니다. 있도록 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] SSL 연결을 통해 작업, 인증서, 최신 상태이 고 인증서 데이터에 사이트 데이터와 일치 하는지 확인 합니다.  
  
## <a name="clickonce-and-proxy-authentication"></a>ClickOnce 및 프록시 인증  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)].NET Framework 3.5부터 Windows 통합 프록시 인증에 대 한 지원을 제공 합니다. 특정 machine.config 지시문이 없는 필요 합니다. [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]기본 또는 다이제스트 등의 다른 인증 프로토콜에 대 한 지원을 제공 하지 않습니다.  
  
 또한이 기능을 사용 하도록 설정 하려면.NET Framework 2.0에는 핫픽스를 적용할 수 있습니다. 자세한 내용은 http://go.microsoft.com/fwlink/?LinkId=158730를 참조 하십시오.  
  
 자세한 내용은 참조 [ \<defaultProxy > 요소 (네트워크 설정)](/dotnet/framework/configure-apps/file-schema/network/defaultproxy-element-network-settings)합니다.  
  
## <a name="clickonce-and-web-browser-compatibility"></a>ClickOnce 및 웹 브라우저 호환성  
 현재 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 설치 Internet Explorer를 사용 하 여 배포 매니페스트의 URL를 열 경우에 시작 됩니다. Microsoft Office Outlook 같은 다른 응용 프로그램에서 URL를 시작 하는 배포는 Internet Explorer는 기본 웹 브라우저로 설정 된 경우에 성공적으로 시작 됩니다.  
  
> [!NOTE]
>  Mozilla Firefox는 배포 제공자 비어 있지 않은 경우 Microsoft.NET Framework 도우미 확장이 설치 되어 사용할 수 있습니다. 이 확장은.NET Framework 3.5 s p 1에 패키지 됩니다. XBAP 지원에 대 한 플러그 인 NPWPF 필요할 때 활성화 됩니다.  
  
## <a name="activating-clickonce-applications-through-browser-scripting"></a>브라우저에서 스크립팅을 통해 ClickOnce 응용 프로그램 활성화  
 시작 하는 사용자 지정 웹 페이지를 개발한 경우는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 액티브 스크립팅을 사용 하 여 응용 프로그램 일부 컴퓨터에서 응용 프로그램이 시작 되지 않는 경우가 있습니다. Internet Explorer 포함 이라는 설정 **파일 다운로드에 대 한 자동 확인**,이 동작에 영향을 주는 합니다. 이 설정은에서 사용할 수는 **보안** 탭에서 해당 **옵션** 이 동작에 영향을 주는 메뉴. 호출 될 **파일 다운로드에 대 한 자동 확인**, 아래에 표시 되는 **다운로드** 범주입니다. 속성이로 설정 되어 **사용** 인트라넷 웹 페이지에 대 한 및 기본적으로 **사용 하지 않도록 설정** 인터넷 웹 페이지에 대해 기본적으로 합니다. 이 설정은로 설정 된 경우 **사용 하지 않도록 설정**를 활성화 하려고 하면는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램 프로그래밍 방식으로 (예를 들어 해당 URL을 할당 하 여는 `document.location` 속성) 차단 됩니다. 이러한 상황에서는 사용자가 시작할 수만 사용자가 시작한 다운로드를 통해 응용 프로그램 예를 들어 응용 프로그램의 URL로 설정 된 하이퍼링크를 클릭 하 여 합니다.  
  
## <a name="additional-server-configuration-issues"></a>추가 서버 구성 문제  
  
##### <a name="administrator-permissions-required"></a>관리자 권한 필요  
 Http 게시 하는 경우 대상 서버에 대 한 관리자 권한이 있어야 합니다. IIS는이 권한 수준이 필요합니다. HTTP를 사용 하 여 게시 하지 않는 경우 한 쓰기 권한이 대상 경로에 있습니다.  
  
##### <a name="server-authentication-issues"></a>서버 인증 문제  
 "익명 액세스를" 해제 되어 있는 원격 서버에 게시할 때 다음과 같은 경고가 표시 됩니다.  
  
```  
"The files could not be downloaded from http://<remoteserver>/<myapplication>/.  The remote server returned an error: (401) Unauthorized."  
```  
  
> [!NOTE]
>  NTLM (NT 챌린지-응답) 인증 사이트에서 기본 자격 증명이 아닌 다른 자격 증명을 입력 해야 하 고 보안 대화 상자에서 클릭 하는 경우에 작동 가능 **확인** 때 메시지가 표시 되는 제공 된 저장 하려는 경우 이후 세션에서 사용할 자격 증명입니다. 그러나이 해결 방법을 기본 인증에 대 한 작동 하지 않습니다.  
  
## <a name="using-third-party-web-servers"></a>공급 업체 웹 서버를 사용 하 여  
 배포 하는 경우는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 이외의 IIS 웹 서버에서 응용 프로그램 서버 키에 대 한 잘못 된 콘텐츠 형식을 반환 하는 경우 문제가 발생할 수 있습니다 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 같은 배포 매니페스트와 응용 프로그램 매니페스트 파일. 이 문제를 해결 하려면 서버에 새 콘텐츠 형식을 추가 하 고 다음 표에 나열 된 모든 파일 이름 확장명 매핑이 있는지 확인 하는 방법에 대 한 설명서는 웹 서버의 도움말을 참조 하십시오.  
  
|파일 이름 확장명|콘텐츠 형식|  
|-------------------------|------------------|  
|`.application`|`application/x-ms-application`|  
|`.manifest`|`application/x-ms-manifest`|  
|`.deploy`|`application/octet-stream`|  
|`.msu`|`application/octet-stream`|  
|`.msp`|`application/octet-stream`|  
  
## <a name="clickonce-and-mapped-drives"></a>ClickOnce 및 매핑된 드라이브  
 ClickOnce 응용 프로그램을 게시 하려면 Visual Studio를 사용 하는 경우에 설치 위치로 매핑된 드라이브를 지정할 수 없습니다. 그러나 ClickOnce 응용 프로그램 매니페스트 생성기 및 (Mage.exe 및 MageUI.exe) 편집기를 사용 하 여 매핑된 드라이브에서 설치를 수정할 수 있습니다. 자세한 내용은 참조 [Mage.exe (매니페스트 생성 및 편집 도구)](/dotnet/framework/tools/mage-exe-manifest-generation-and-editing-tool) 및 [MageUI.exe (매니페스트 생성 및 편집 도구, 그래픽 클라이언트)](/dotnet/framework/tools/mageui-exe-manifest-generation-and-editing-tool-graphical-client)합니다.  
  
## <a name="ftp-protocol-not-supported-for-installing-applications"></a>FTP 프로토콜 응용 프로그램 설치에 지원 되지 않습니다.  
 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]모든 HTTP 1.1 웹 서버나 파일 서버에서 응용 프로그램을 설치 하도록 지원 합니다. FTP 파일 전송 프로토콜은 응용 프로그램 설치에 지원 되지 않습니다. FTP를 사용 하 여만 응용 프로그램을 게시할 수 있습니다. 다음 표에서 이러한 차이점을 보여 줍니다.  
  
|URL 형식|설명|  
|--------------|-----------------|  
|ftp: / /|게시할 수는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 이 프로토콜을 사용 하 여 응용 프로그램입니다.|  
|http://|설치할 수 있습니다는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 이 프로토콜을 사용 하 여 응용 프로그램입니다.|  
|https://|설치할 수 있습니다는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 이 프로토콜을 사용 하 여 응용 프로그램입니다.|  
|file://|설치할 수 있습니다는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 이 프로토콜을 사용 하 여 응용 프로그램입니다.|  
  
## <a name="windows-xp-sp2-windows-firewall"></a>Windows XP SP2: Windows 방화벽  
 기본적으로 Windows XP s p 2는 Windows 방화벽을 사용 합니다. Windows XP가 설치 하는 컴퓨터에서 응용 프로그램을 개발 하는 경우 못한 게시 하 고 실행 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] IIS를 실행 하는 로컬 서버에서 응용 프로그램입니다. 그러나 Windows 방화벽을 열지 않으면 다른 컴퓨터에서 IIS를 실행 되는 해당 서버를 액세스할 수 없습니다. Windows 방화벽 관리에 대 한 내용은 Windows 도움말을 참조 하십시오.  
  
## <a name="windows-server-enable-frontpage-server-extensions"></a>Windows Server: FrontPage server extensions 사용  
 Microsoft의 FrontPage Server Extensions가 HTTP를 사용 하는 Windows 웹 서버에 대 한 응용 프로그램 게시 필요 합니다.  
  
 기본적으로 Windows 서버에 없는 FrontPage Server Extensions가 설치 되어 있습니다. 사용 하려는 경우 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] FrontPage Server Extensions와 HTTP를 사용 하는 Windows Server 웹 서버에 게시 하려면 FrontPage Server Extensions를 먼저 설치 해야 합니다. Windows Server에서 사용자 서버 관리 관리 도구를 사용 하 여 설치를 수행할 수 있습니다.  
  
## <a name="windows-server-locked-down-content-types"></a>Windows Server: 잠금에 대 한 콘텐츠 형식  
 IIS에 [!INCLUDE[WinXPSvr](../debugger/includes/winxpsvr_md.md)] 잠겨 알려진된 일부 콘텐츠 형식 (예를 들어.htm,.html,.txt, 및 등)를 제외한 모든 파일 형식입니다. 배포할 수 있도록 하려면 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 형식.application,.manifest 및 응용 프로그램에서 사용 하는 다른 사용자 지정 파일 형식 파일을 다운로드할 수 있도록 IIS 설정을 변경 해야 하는이 서버를 사용 하 여 응용 프로그램입니다.  
  
 IIS 서버를 사용 하 여 배포 하는 경우 inetmgr.exe를 실행 하 고 기본 웹 페이지에 대 한 새 파일 형식을 추가 합니다.  
  
-   .Application 및.manifest 확장에 대 한 MIME 형식을 지정 해야 "/ x ms-응용 프로그램입니다." 다른 파일 형식에 대 한 MIME 형식을 지정 해야 "응용 프로그램/옥텟 스트림."  
  
-   확장명을 가진 MIME 형식을 만드는 경우 "*" 및 MIME 형식이 "응용 프로그램/옥텟 스트림" 파일을 다운로드할 수 파일 형식은 허용 됩니다. 그러나 (차단 된 파일 형식 예:.aspx 및.asmx를 다운로드할 수 없습니다.)  
  
 Windows Server에서 MIME 형식을 구성 하는 방법에 대 한 자세한 내용은 참조 Microsoft 기술 자료 문서 KB326965, "IIS 6.0 않습니다 하지 제공 알 수 없는 MIME 형식"에서 [http://support.microsoft.com/default.aspx?scid=kb;en-us;326965](http://support.microsoft.com/default.aspx?scid=kb;en-us;326965).  
  
## <a name="content-type-mappings"></a>콘텐츠 형식 매핑  
 .Application 파일에 대 한 콘텐츠 형식 (MIME 형식)를 HTTP를 통해 게시 하는 경우 "/ x ms-응용 프로그램입니다." 이어야 합니다. 있는 경우 [!INCLUDE[dnprdnlong](../code-quality/includes/dnprdnlong_md.md)] 서버에 설치,이 대해 설정할 하면 자동으로 합니다. 이 설치 되지 않은 경우에 대 한 MIME 형식 연결을 만들어야 할는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] vroot 응용 프로그램 (또는 전체 서버).  
  
 IIS 서버를 사용 하 여 배포 하는 경우 inetmgr.exe를 실행 하 고 "/ x ms-응용 프로그램".application 확장명에 대 한 새 콘텐츠 형식을 추가 합니다.  
  
## <a name="http-compression-issues"></a>HTTP 압축 문제  
 와 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)], GZIP 알고리즘을 사용 하 여 클라이언트에 보내는 데이터 스트림을 압축 하는 웹 서버 기술, HTTP 압축을 사용 하는 다운로드를 수행할 수 있습니다. 클라이언트-이 경우 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]-파일을 읽기 전에 스트림의 압축을 해제 합니다.  
  
 IIS를 사용 하는 경우에 HTTP 압축을 쉽게 설정할 수 있습니다. 그러나 HTTP 압축을 사용 하도록 설정 하면 것만 사용할 수 특정 파일 형식-즉, HTML 및 텍스트 파일입니다. 어셈블리 (.dll)에 대 한 압축을 사용 하려면 XML (.xml), 배포 매니페스트 (.application) 및 응용 프로그램 매니페스트 (.manifest)을 추가 해야 이러한 파일 형식의를 압축 하도록 IIS에 대 한 형식의 목록. 파일 형식 배포에 추가 하기 전 까지는 텍스트와 HTML 파일은 압축 됩니다.  
  
 IIS에 대 한 자세한 지침을 참조 하십시오. [HTTP 압축에 대 한 추가 문서 유형을 지정 하는 방법을](http://go.microsoft.com/fwlink/?LinkId=178459)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [ClickOnce 배포 문제 해결](../deployment/troubleshooting-clickonce-deployments.md)   
 [ClickOnce 배포 전략 선택](../deployment/choosing-a-clickonce-deployment-strategy.md)   
 [응용 프로그램 배포 필수 조건](../deployment/application-deployment-prerequisites.md)