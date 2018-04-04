---
title: Visual Studio 설치 또는 사용 시의 네트워크 관련 오류 문제 해결 | Microsoft Docs
description: ''
ms.custom: ''
ms.date: 02/12/2018
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-acquisition
ms.tgt_pltfrm: ''
ms.topic: conceptual
helpviewer_keywords:
- network installation, Visual Studio
- administrator guide, Visual Studio
- installing Visual Studio, administrator guide
- list of domains, locations, URLs, Visual Studio
- proxy errors, Visual Studio
ms.assetid: ''
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: fc5f1c07f709c1cdb8e20704dbea9cb5550b14b3
ms.sourcegitcommit: efd8c8e0a9ba515d47efcc7bd370eaaf4771b5bb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/03/2018
---
# <a name="troubleshooting-network-related-errors-when-you-install-or-use-visual-studio"></a>Visual Studio 설치 또는 사용 시의 네트워크 관련 오류 문제 해결
방화벽 또는 프록시 서버 배후에서 Visual Studio를 설치하거나 사용할 때 발생할 수 있는 가장 일반적인 네트워크 또는 프록시 관련 오류에 대한 솔루션이 있습니다.

## <a name="error-proxy-authorization-required"></a>오류: “프록시 권한 필요”

일반적으로 사용자가 프록시 서버를 통해 인터넷에 연결할 때 프록시 서버가 Visual Studio에서 네트워크 리소스에 대한 호출을 차단하는 경우 이 오류가 발생합니다.

### <a name="to-fix-this-error"></a>이 오류를 해결하려면

- Visual Studio를 다시 시작합니다. 프록시 인증 대화 상자가 나타납니다. 대화 상자에 메시지가 표시되면 자격 증명을 입력합니다.

- Visual Studio를 다시 시작해도 문제가 해결되지 않으면 프록시 서버에서 http:&#47;&#47;go.microsoft.com 주소가 아닌 &#42;.visualStudio.com 주소에 대한 자격 증명을 입력하라는 메시지를 표시하기 때문일 수 있습니다. 이러한 서버에 대해 다음 URL을 허용 목록에 포함하여 Visual Studio에서 모든 로그인 시나리오의 차단을 해제하는 것이 좋습니다.

    - &#42;.windows.net

    - &#42;.microsoftonline.com

    - &#42;.visualstudio.com

    - &#42;.microsoft.com

    - &#42;.live.com

- 또는 Visual Studio를 다시 시작할 때 http:&#47;&#47;go.microsoft.com 주소 및 서버 끝점 둘 다에 대해 프록시 인증 대화 상자가 표시되도록 허용 목록에서 http:&#47;&#47;go.microsoft.com 주소를 제거할 수 있습니다.

    또는

- 프록시에 기본 자격 증명을 사용하려는 경우 다음 작업을 수행할 수 있습니다.

    1. **devenv.exe.config** (the devenv.exe configuration file) in: **%ProgramFiles%\Microsoft Visual Studio\2017\Enterprise\Common7\IDE** 또는 **%ProgramFiles(x86)%\Microsoft Visual Studio\2017\Enterprise\Common7\IDE**를 찾습니다.

    1. 구성 파일에서 `<system.net>` 블록을 찾아 다음 코드를 추가합니다.

        ```xml
        <defaultProxy enabled="true" useDefaultCredentials="true">
            <proxy bypassonlocal="True" proxyaddress=" HYPERLINK "http://<yourproxy:port#" http://<yourproxy:port#>"/>
        </defaultProxy>
        ```

        `proxyaddress="<http://<yourproxy:port#>`에는 네트워크의 올바른 프록시 주소를 삽입해야 합니다.

    또는

- 또한 [How to connect through an authenticated Web Proxy](http://blogs.msdn.com/b/rido/archive/2010/05/06/how-to-connect-to-tfs-through-authenticated-web-proxy.aspx)(인증된 웹 프록시를 통해 연결하는 방법) 블로그 게시물의 지침에 따라 프록시 사용을 허용하는 코드를 추가할 수도 있습니다.

## <a name="error-the-underlying-connection-was-closed"></a>오류: “기본 연결이 닫혔습니다.”

방화벽이 있는 개인 네트워크에서 Visual Studio를 사용하는 경우 Visual Studio가 일부 네트워크 리소스에 연결하지 못할 수 있습니다. 이러한 리소스는 로그인 및 라이선스용 VSTS(Visual Studio Team Services), NuGet 및 Azure 서비스를 포함할 수 있습니다. Visual Studio가 이러한 리소스 중 하나에 연결하지 못할 경우 다음과 같은 오류 메시지가 표시될 수 있습니다.

  **기본 연결이 닫혔습니다. 전송 중에 예상치 못한 오류가 발생했습니다.**

Visual Studio는 TLS(전송 계층 보안) 1.2 프로토콜을 사용하여 네트워크 리소스에 연결합니다. Visual Studio에서 TLS 1.2를 사용하는 경우 일부 개인 네트워크의 보안 어플라이언스는 특정 서버 연결을 차단합니다.

### <a name="to-fix-this-error"></a>이 오류를 해결하려면

다음 URL에 대한 연결을 사용하도록 설정합니다.

- https:&#47;&#47;management.core.windows.net

- https:&#47;&#47;app.vssps.visualstudio.com

- https:&#47;&#47;login.microsoftonline.com

- https:&#47;&#47;login.live.com

- https:&#47;&#47;go.microsoft.com

- https:&#47;&#47;graph.windows.net

- https:&#47;&#47;app.vsspsext.visualstudio.com

- &#42;.azurewebsites.net(Azure 연결의 경우)

- &#42;.visualstudio.com

- cdn.vsassets.io(콘텐츠 배달 네트워크 또는 CDN, 콘텐츠 호스트)

- &#42;.gallerycdn.vsassets.io(VSTS 확장 호스트)

- static2.sharepointonline.com(Visual Studio가 Office UI Fabric 키트에서 사용하는 리소스(예: 글꼴) 호스트)

- &#42;.nuget.org(NuGet 연결의 경우)

 > [!NOTE]
 > 개인이 소유한 NuGet 서버 URL은 이 목록에 포함되어 있지 않을 수 있습니다. %APPData%\Nuget\NuGet.Config에서 사용 중인 NuGet 서버를 확인할 수 있습니다.


## <a name="get-support"></a>지원 받기
Visual Studio 설치에 실패하는 경우에는 [Visual Studio 2017 설치 및 업그레이드 문제 해결](troubleshooting-installation-issues.md) 페이지를 참조하세요. 설치 문제 해결 단계가 도움이 되지 않는 경우 라이브 채팅을 통해 Microsoft에 설치 지원을 문의할 수 있습니다(영어만 가능). 자세한 내용은 [Visual Studio 지원 페이지](https://www.visualstudio.com/vs/support/#talktous)를 참조하세요.

몇 가지 추가 지원 옵션은 다음과 같습니다.
* Visual Studio 설치 관리자와 Visual Studio IDE에 모두 표시되는 [문제 보고](../ide/how-to-report-a-problem-with-visual-studio-2017.md) 도구를 통해 Microsoft에 제품 문제를 보고할 수 있습니다.
* [UserVoice](https://visualstudio.uservoice.com/forums/121579)에서 Microsoft와 제품 제안을 공유할 수 있습니다.
* [Visual Studio 개발자 커뮤니티](https://developercommunity.visualstudio.com/)에서 제품 문제를 추적하고 질문을 하고 답을 찾을 수 있습니다.
* [Gitter 커뮤니티의 Visual Studio 관련 대화](https://gitter.im/Microsoft/VisualStudio)를 통해 Microsoft 및 다른 Visual Studio 개발자와 소통할 수도 있습니다.  (이 옵션을 사용하려면 [GitHub](https://github.com/) 계정이 필요합니다.)

## <a name="see-also"></a>참고 항목
* [방화벽 또는 프록시 서버 뒤에 Visual Studio 설치 및 사용](install-and-use-visual-studio-behind-a-firewall-or-proxy-server.md)
* [Visual Studio 관리자 가이드](visual-studio-administrator-guide.md)
* [Visual Studio 2017 설치](install-visual-studio.md)
