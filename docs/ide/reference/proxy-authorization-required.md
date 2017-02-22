---
title: "프록시 권한 필요 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c2d24ae1-9902-460e-b72a-0299eed9ee82
caps.latest.revision: 4
caps.handback.revision: 4
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# 프록시 권한 필요
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

이 오류는 대개 사용자가 프록시 서버를 통해 Visual Studio Online에 연결했는데 프록시 서버에서 호출을 차단하는 경우 발생합니다. Visual Studio Online은 사용자의 IDE 로그인 상태를 유지하는 데 사용됩니다.  
  
## 이 오류를 해결하려면  
  
-   Visual Studio를 다시 시작합니다. 프록시 인증 대화 상자가 나타납니다. 대화 상자에서 자격 증명을 입력합니다.  
  
-   위의 단계를 수행해도 문제가 해결되지 않으면 프록시 서버에서 http:\/\/go.microsoft.com 주소가 아닌 \*.visualStudio.com 주소에 대한 자격 증명을 입력하라는 메시지를 표시하기 때문일 수 있습니다. 이러한 서버에 대해 다음을 허용 목록에 포함하여 Visual Studio에서 모든 로그인 시나리오의 차단을 해제해야 합니다.  
  
    -   \*.windows.net  
  
    -   \*.microsoftonline.com  
  
    -   \*.visualstudio.com  
  
    -   \*.microsoft.com  
  
    -   \*.live.com  
  
-   그렇지 않으면 Visual Studio가 다시 시작될 때 http:\/\/go.microsoft.com 주소 및 서버 끝점 모두에 대해 프록시 인증 대화 상자가 표시되도록 허용 목록에서 http:\/\/go.microsoft.com 주소를 제거합니다.  
  
-   또는  
  
-   프록시에 기본 자격 증명을 사용하려는 경우 다음 작업을 수행하면 됩니다.  
  
    1.  **%ProgramFiles%\\Microsoft Visual Studio 14.0\\Common7\\IDE**\(또는 **%ProgramFiles\(x86\)%\\Microsoft Visual Studio 14.0\\Common7\\IDE**\)에서 devenv.exe.config\(devenv.exe 구성 파일\)를 찾습니다.  
  
    2.  구성 파일에서 `<system.net>` 블록을 찾아 다음 코드를 추가합니다.  
  
        ```xml  
        <defaultProxy enabled="true" useDefaultCredentials="true">  
            <proxy bypassonlocal="True" proxyaddress=" HYPERLINK "http://<yourproxy:port#" http://<yourproxy:port#>"/>  
        </defaultProxy>  
  
        ```  
  
         `proxyaddress="<http://<yourproxy:port#>`에는 네트워크의 올바른 프록시 주소를 삽입해야 합니다.  
  
-   또는  
  
-   [이 게시물](http://blogs.msdn.com/b/rido/archive/2010/05/06/how-to-connect-to-tfs-through-authenticated-web-proxy.aspx)의 지침에 따라 프록시를 사용할 수 있는 코드를 추가할 수도 있습니다.