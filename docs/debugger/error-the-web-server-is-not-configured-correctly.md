---
title: "오류: 웹 서버가 올바르게 구성 되지 않았습니다 | Microsoft Docs"
ms.custom: 
ms.date: 09/20/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: vs.debug.remote.projnotconfigured
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords: debugger, Web application errors
caps.latest.revision: "22"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 6f1e206cc9327ef933f52f35960f628170e02c38
ms.sourcegitcommit: 9357209350167e1eb7e50b483e44893735d90589
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/05/2018
---
# <a name="error-the-web-server-is-not-configured-correctly"></a>오류: 웹 서버가 제대로 구성되어 있지 않습니다.

문제를 해결 하려면 여기에서 자세히 설명 하는 단계를 수행한 후 및 디버깅을 다시 시도 하기 전에 IIS를 다시 설정 할 수도 있습니다. 관리자 명령 프롬프트를 열고 입력 하 여 할 수 있습니다 `iisreset`합니다.

이 문제를 해결 하려면 다음이 단계를 수행 합니다.

1. 서버에서 호스팅되는 웹 응용 프로그램으로 구성 된 경우 릴리스 빌드를 디버그 빌드를 다시 게시 하 고 web.config 파일에 포함 되어 있는지 확인 `debug=true` 컴파일 요소에 있습니다. IIS 및 다시 시도 다시 설정 합니다.

    예를 들어 게시 프로필에 대 한 릴리스 빌드를 사용 하는 경우 디버그로 변경 하 고 다시 게시 합니다. Debug 특성으로 설정 됩니다는 그렇지 않은 경우 `false` 게시 하는 경우.

2. (IIS) 실제 경로가 정확한 지 확인 합니다. Iis에서에서이 설정을 알게 **기본 설정 > 실제 경로** (또는 **고급 설정** 이전 버전의 IIS에).

    실제 경로 올바르지 않을 수 웹 응용 프로그램이 다른 컴퓨터에 복사, 수동으로 이름을 변경 되었거나 이동 합니다. IIS 및 다시 시도 다시 설정 합니다.

3. Visual Studio에서 올바른 서버 속성에서 선택 되어 있는지 확인 합니다. (열기 **속성 > 웹 > 서버** 또는 **속성 > 디버그** 프로젝트 형식에 따라 합니다. Web Forms 프로젝트를 열고 **속성 페이지 > 시작 옵션 > 서버**).

    IIS와 같은 외부 (사용자 지정) 서버를 사용 하는 URL은 올바른 이어야 합니다. 그렇지 않은 경우 IIS Express 및 다시 시도 선택 합니다.

4. (IIS) 올바른 버전의 ASP.NET 서버에 설치 되어 있는지 확인 합니다.

    일치 하지 않는 버전의 Visual Studio 프로젝트와 IIS에 ASP.NET이이 문제가 발생할 수 있습니다. Web.config의 프레임 워크 버전을 설정 해야 합니다. IIS에서 ASP.NET을 설치 하려면 사용 된 [웹 플랫폼 설치 관리자 (WebPI)](https://www.microsoft.com/web/downloads/platform.aspx)합니다. 참고: [IIS 8.0를 사용 하 여 ASP.NET 3.5 및 ASP.NET 4.5](/iis/get-started/whats-new-in-iis-8/iis-80-using-aspnet-35-and-aspnet-45) 또는 ASP.NET Core [Windows iis에서 호스트](https://docs.asp.net/en/latest/publishing/iis.html)합니다.
  
4. 경우는 `maxConnection` 있고 IIS에서의 제한은 너무 낮기를 너무 많은 연결이 있는 경우 해야 할 수 있습니다 [연결 제한을 늘리려면](/iis/configuration/system.applicationhost/sites/sitedefaults/limits)합니다.
  
## <a name="see-also"></a>참고 항목  
 [원격 IIS 컴퓨터의 원격 디버깅 ASP.NET](../debugger/remote-debugging-aspnet-on-a-remote-iis-7-5-computer.md)   
 [웹 응용 프로그램 디버그: 오류 및 문제 해결](../debugger/debugging-web-applications-errors-and-troubleshooting.md)