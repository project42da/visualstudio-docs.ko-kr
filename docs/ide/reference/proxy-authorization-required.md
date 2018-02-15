---
title: "프록시 권한 부여가 필요한 오류 수정 | Microsoft Docs"
ms.custom: 
ms.date: 09/22/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c2d24ae1-9902-460e-b72a-0299eed9ee82
caps.latest.revision: "4"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: e33e0e2896ccb3a5f7fe6d6da57f509af30d77fe
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="proxy-authorization-required"></a>프록시 권한 필요

일반적으로 사용자가 프록시 서버를 통해 인터넷에 연결할 때 프록시 서버가 Visual Studio에서 네트워크 리소스에 대한 호출을 차단하는 경우 이 오류가 발생합니다.

## <a name="to-correct-this-error"></a>이 오류를 해결하려면

- Visual Studio를 다시 시작합니다. 프록시 인증 대화 상자가 나타납니다. 대화 상자에서 자격 증명을 입력합니다.

- 위의 단계를 수행해도 문제가 해결되지 않으면 프록시 서버에서 http://go.microsoft.com 주소가 아닌 *.visualStudio.com 주소에 대한 자격 증명을 입력하라는 메시지를 표시하기 때문일 수 있습니다. 이러한 서버에 대해 다음 URL 목록을 허용 목록에 포함하여 Visual Studio에서 모든 로그인 시나리오의 차단을 해제해야 합니다.

    - *.windows.net

    - *.microsoftonline.com

    - *.visualstudio.com

    - *.microsoft.com

    - *.live.com

- 그렇지 않으면 Visual Studio가 다시 시작될 때 http://go.microsoft.com 주소 및 서버 끝점 모두에 대해 프록시 인증 대화 상자가 표시되도록 허용 목록에서 http://go.microsoft.com 주소를 제거합니다.

    또는

- 프록시에 기본 자격 증명을 사용하려는 경우 다음 작업을 수행하면 됩니다.

    1. **devenv.exe.config** (the devenv.exe configuration file) in: **%ProgramFiles%\Microsoft Visual Studio\2017\Enterprise\Common7\IDE** 또는 **%ProgramFiles(x86)%\Microsoft Visual Studio\2017\Enterprise\Common7\IDE**를 찾습니다.

    1. 구성 파일에서 `<system.net>` 블록을 찾아 다음 코드를 추가합니다.

        ```xml
        <defaultProxy enabled="true" useDefaultCredentials="true">
            <proxy bypassonlocal="True" proxyaddress=" HYPERLINK "http://<yourproxy:port#" http://<yourproxy:port#>"/>
        </defaultProxy>
        ```

        `proxyaddress="<http://<yourproxy:port#>`에는 네트워크의 올바른 프록시 주소를 삽입해야 합니다.

    또는

- [이 게시물](http://blogs.msdn.com/b/rido/archive/2010/05/06/how-to-connect-to-tfs-through-authenticated-web-proxy.aspx) 의 지침에 따라 프록시를 사용할 수 있는 코드를 추가할 수도 있습니다.
