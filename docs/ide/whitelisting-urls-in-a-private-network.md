---
title: "개인 네트워크의 허용 목록 URL | Microsoft Docs"
ms.custom: 
ms.date: 09/19/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 3bc7db7b6a1d3e1d39b5fb3b128c28da37a9538b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="whitelisting-urls-in-a-private-network"></a>개인 네트워크의 허용 목록 URL    
방화벽과 같은 보안 어플라이언스를 사용하는 개인 네트워크에서 Visual Studio를 사용하는 경우 Visual Studio는 일부 네트워크 리소스에 연결할 수 없습니다. 이러한 리소스에는 로그인 및 라이선스용 VSTS(Visual Studio Team Services), NuGet 및 Azure 서비스가 포함됩니다. Visual Studio가 이러한 리소스 중 하나에 연결되지 않는 경우 다음과 같은 오류 메시지가 표시됩니다.  

  **기본 연결이 닫혔습니다. 전송 중에 예상치 못한 오류가 발생했습니다.**  

Visual Studio는 TLS(전송 계층 보안) 1.2 프로토콜을 사용하여 네트워크 리소스에 연결합니다. Visual Studio에서 TLS 1.2를 사용하는 경우 일부 개인 네트워크의 보안 어플라이언스는 특정 서버 연결을 차단합니다. 오류를 해결하려면 다음 URL에 대한 연결을 사용합니다.

- https://management.core.windows.net  

- https://app.vssps.visualstudio.com  

- https://login.microsoftonline.com  

- https://login.live.com  

- https://go.microsoft.com  

- https://graph.windows.net  

- https://app.vsspsext.visualstudio.com  

- *.azurewebsites.net(Azure 연결의 경우)  

- *.nuget.org(NuGet 연결의 경우)  

- *.visualstudio.com  

- cdn.vsassets.io(콘텐츠 배달 네트워크 또는 CDN, 콘텐츠 호스트)  

- *.gallerycdn.vsassets.io(VSTS 확장 호스트)  

- static2.sharepointonline.com(Visual Studio가 Office Fabric UI 키트에서 사용하는 리소스(예: 글꼴) 호스트)

> [!NOTE]
>  개인이 소유한 NuGet 서버 URL은 위 목록에 포함되어 있지 않을 수 있습니다. %APPData%\Nuget\NuGet.Config를 열면 사용 중인 NuGet 서버를 확인할 수 있습니다.  

## <a name="see-also"></a>참고 항목  
[프록시 권한 필요 오류](../ide/reference/proxy-authorization-required.md)  
[연결된 환경](../ide/connected-environment.md)  
[방화벽 또는 프록시 서버 뒤에 Visual Studio 설치](../install/install-visual-studio-behind-a-firewall-or-proxy-server.md)  
