---
title: "방법: ASP.NET 프로세스의 이름 찾기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- ASP.NET debugging, ASP.NET process
- ASP.NET process
ms.assetid: 931a7597-b0f0-4a28-931d-46e63344435f
caps.latest.revision: "29"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 03ae4956f0e16a4fb9267266ebc6b6c335c95eac
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-find-the-name-of-the-aspnet-process"></a>방법: ASP.NET 프로세스의 이름 찾기
실행 중인 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 응용 프로그램에 연결하려면 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 프로세스의 이름을 알고 있어야 합니다.  

-   IIS 또는 IISExpress에서 ASP.NET Core를 실행 하는 경우 프로세스 이름은 dotnet.exe입니다.

-   나중에 IIS 6.0에 ASP.NET를 실행 하는 경우 이름은 w3wp.exe입니다.  
  
-   이전 버전의 IIS에서 ASP.NET을 실행 하는 경우 이름은 aspnet_wp.exe입니다.

-   IISExpress에 ASP.NET을 실행 하는 경우 이름은 iisexpress.exe입니다.
  
버전의 Visual Studio 2012 이전의 Visual Studio를 사용 하 여 빌드한 응용 프로그램의 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 코드 파일 시스템에 상주 하 고 WebDev.WebServer.exe 테스트 서버 또는 WebDev.WebServer40.exe에서 실행할 수 있습니다. 대신 WebDev.WebServer40.exe WebDev.WebServer.exe에 연결 해야 하는 경우에 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 프로세스입니다. 이 시나리오는 로컬 디버깅에만 적용됩니다.
  
이전 버전의 ASP 응용 프로그램은 in-process로 실행되는 경우 IIS 프로세스 inetinfo.exe 내에서 실행됩니다.  

### <a name="to-determine-the-iis-version-under-which-the-application-is-running"></a>응용 프로그램이 실행되는 IIS 버전을 확인하려면  

1.  응용 프로그램이 실행 되 고 있는지 확인 한 다음, Visual Studio에서 사용 하 여는 [프로세스에 연결](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md) 명령입니다.

2.  프로세스를 빠르게 찾기 위해 w3wp.exe 같은 프로세스 이름에 첫 번째 문자를 입력의 **사용 가능한 프로세스** 목록입니다.

    이 항목의 목록에서 사용 가능한 프로세스는 어떤 버전의 IIS 사용할 수 있고 프로세스 응용 프로그램을 실행 표시 됩니다.

    > [!NOTE]
    > Visual Studio 2017 년부터 프로세스 이름을 검색 하려면 검색 상자를 사용할 수 있습니다.
  
## <a name="see-also"></a>참고 항목  
 [실행 중인 프로세스에 연결](../debugger/attach-to-running-processes-with-the-visual-studio-debugger.md)  
 [원격 웹 응용 프로그램 디버깅의 필수 구성 요소](../debugger/prerequistes-for-remote-debugging-web-applications.md)   
 [시스템 요구 사항](../debugger/aspnet-debugging-system-requirements.md)   
 [ASP.NET 응용 프로그램 디버그](../debugger/how-to-enable-debugging-for-aspnet-applications.md)