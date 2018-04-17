---
title: '오류: 웹 서버에서 디버깅을 시작할 수 없습니다. | Microsoft Docs'
ms.custom: ''
ms.date: 05/23/2017
ms.technology:
- vs-ide-debug
ms.topic: reference
f1_keywords:
- vs.debug.error.http
- vwd.nonadmin.error.
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- IIS, debugging DLLs
- debugger, Web application errors
- unable to start debugging error
- security [debugger], Web applications
- debugging [Visual Studio], errors
- HTTP servers, debugging error
- security settings, checking for default Web sites
- errors [debugger], unable to start debugging
- debugging ASP.NET Web applications, unable to start debugging error
- remote debugging, errors
author: mikejo5000
ms.author: mikejo
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 459df1ca9ffed246116c71adac8a38039b6602ae
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="error-unable-to-start-debugging-on-the-web-server"></a>오류: 웹 서버에서 디버깅을 시작할 수 없습니다.

웹 서버에서 실행 중인 ASP.NET 응용 프로그램을 디버깅 하려고 할 때이 오류 메시지가 나타날 수 있습니다: `Unable to start debugging on the Web server`합니다.

대개이 오류는 응용 프로그램 풀, IIS 재설정 또는 둘 다에 대 한 업데이트를 필요로 하는 오류 또는 구성 변경이 발생 했기 때문에 발생 합니다. 관리자 권한 명령 프롬프트를 열고 입력 하 여 IIS를 다시 설정할 수 있습니다 `iisreset`합니다. 

## <a name="specificerrors"></a>자세한 오류 메시지는 무엇입니까?

`Unable to start debugging on the Web server` 메시지는 일반 합니다. 일반적으로 더 구체적인 메시지 오류 문자열에 포함 되며 문제 또는 보다 정확 하 게 수정 프로그램에 대 한 검색의 원인을 파악 하는 데 도움이 되. 다음은 몇 주 오류 메시지에 추가 하는 일반적인 오류 메시지:

- [IIS 시작와 일치 하는 웹 사이트를 나열 하지 않습니다 url](#IISlist)
- [웹 서버가 올바르게 구성 되지 않았습니다.](#web_server_config)
- [웹 서버에 연결할 수 없습니다.](#unabletoconnect)
- [웹 서버가 적시에 응답 하지 않습니다.](#webservertimeout)
- [Microsoft visual studio 원격 디버깅 monitor(msvsmon.exe) 원격 컴퓨터에서 실행 되 고 표시 되지 않습니다.](#msvsmon)
- [원격 서버 오류를 반환합니다.](#server_error)
- [ASP.NET 디버깅을 시작할 수 없습니다.](#aspnet)
- [디버거는 원격 컴퓨터에 연결할 수 없습니다.](#cannot_connect)
- [참조 일반적인 구성 오류에 대 한 도움말입니다. 디버거 외부에서 웹 페이지를 실행 합니다. 추가 정보가 제공 될 수 있습니다.](#see_help)

## <a name="IISlist"></a> IIS 시작와 일치 하는 웹 사이트를 나열 하지 않습니다 url

- 관리자 권한으로 Visual Studio를 다시 시작 하 고 디버깅을 다시 시도 하십시오. (일부 ASP.NET 디버깅 시나리오에는 상승 된 권한이 필요 합니다.)

    Visual Studio 바로 가기 아이콘을 마우스 오른쪽 단추로 클릭 하 여 항상 관리자 권한으로 실행 하려면 Visual Studio를 구성할 수 있습니다 선택 **속성 > 고급**를 선택한 다음 항상 관리자 권한으로 실행 합니다.

## <a name="web_server_config"></a> 웹 서버가 올바르게 구성 되지 않았습니다.

- 참조 [오류: 웹 서버가 올바르게 구성 되지 않았습니다.](../debugger/error-the-web-server-is-not-configured-correctly.md)합니다.

## <a name="unabletoconnect"></a> 웹 서버에 연결할 수 없습니다.

- 동일한 컴퓨터에서 Visual Studio와 웹 서버를 실행 및 사용 하 여 디버깅 **F5** (대신 **프로세스에 연결**)? 프로젝트 속성을 열고 프로젝트가 올바른 웹 서버에 연결 하 고 URL을 시작 하도록 구성 되어 있는지 확인 합니다. (열기 **속성 > 웹 > 서버** 또는 **속성 > 디버그** 프로젝트 형식에 따라 합니다. Web Forms 프로젝트를 열고 **속성 페이지 > 시작 옵션 > 서버**.)

- 그렇지 않은 경우 응용 프로그램 풀을 다시 시작 하 고 IIS 다시 설정 합니다. 자세한 내용은 참조 [IIS 구성을 확인](#vxtbshttpservererrorsthingstocheck)합니다.

## <a name="webservertimeout"></a> 웹 서버가 적시에 응답 하지 않습니다.

- IIS를 다시 설정 하 고 디버깅을 다시 시도 하십시오. 여러 디버거 인스턴스는 IIS 프로세스;에 연결 기본 설정으로 종료합니다. 자세한 내용은 참조 [IIS 구성을 확인](#vxtbshttpservererrorsthingstocheck)합니다.

## <a name="msvsmon"></a> Microsoft visual studio 원격 디버깅 monitor(msvsmon.exe) 원격 컴퓨터에서 실행 되 고 표시 되지 않습니다.

- 원격 컴퓨터에서 디버깅 하는 경우 했는지 확인 [설치 하 고 원격 디버거를 실행 하는](../debugger/remote-debugging.md)합니다. 메시지에 언급 방화벽, 있는지 확인는 [방화벽에서 포트를 수정](../debugger/remote-debugger-port-assignments.md) 특히 타사 방화벽을 사용 하는 경우에 열려 있습니다.
- 호스트 파일을 사용 하는 경우 올바르게 구성 되어 있는지 확인 합니다. 예를 들어, 사용 하 여 디버깅 하는 경우 **F5** (대신 **프로세스에 연결**), 호스트 파일, 프로젝트 속성에서와 같이 동일한 프로젝트 URL을 포함 해야 **속성 > 웹 > 서버**  또는 **속성 > 디버그**프로젝트 형식에 따라 합니다.

## <a name="server_error"></a> 원격 서버 오류를 반환합니다.

확인 프로그램 [IIS 로그 파일](https://support.microsoft.com/help/943891/the-http-status-code-in-iis-7-0--iis-7-5--and-iis-8-0) 오류 하위 코드 및 추가 정보와이 IIS 7 [블로그 게시물](https://blogs.iis.net/tomkmvp/troubleshoot-a-403)합니다.

또한 다음은 일반적인 오류 코드 중 일부는 몇 가지 제안 사항입니다.
- (403) 사용할 수 없음입니다. 이 오류에 대 한 다양 한 원인은, 로그 파일 및 웹 사이트에 대 한 IIS 보안 설정을 확인 합니다. 서버의 web.config 포함 되어 있는지 확인 `debug=true` 컴파일 요소에 있습니다. 웹 응용 프로그램 폴더에 적절 한 권한이 있는지, 그리고 응용 프로그램 풀 구성이 올바른지 (암호 변경 수 있습니다)에 있는지 확인 합니다. 참조 [IIS 구성을 확인](#vxtbshttpservererrorsthingstocheck)합니다. 이러한 설정이 올바른지 이미 로컬로 디버깅 하는 경우의 올바른 서버 종류 및 URL에 연결 하 고 있는지 확인할 수도 (에서 **속성 > 웹 > 서버** 또는 **속성 > 디버그**, 사용자 프로젝트 형식에 따라).
- (503) 서버를 사용할 수 없습니다. 응용 프로그램 풀 오류 또는 구성 변경으로 인해 중지 있을 수 있습니다. 응용 프로그램 풀을 다시 시작 합니다.
- (404) 찾을 수 없습니다. 올바른 버전의 ASP.NET에 대 한 응용 프로그램 풀 구성 되어 있는지 확인 합니다.

## <a name="aspnet"></a> ASP.NET 디버깅을 시작할 수 없습니다.

- 응용 프로그램 풀을 다시 시작 하 고 IIS를 다시 설정 합니다. 자세한 내용은 참조 [IIS 구성을 확인](#vxtbshttpservererrorsthingstocheck)합니다.
- URL을 다시 작성 하는 경우 없는 URL 다시 작성 된 기본 web.config를 테스트 합니다. 참조는 **참고** URL에 대 한 모듈에서 다시 작성 [IIS 구성을 확인](#vxtbshttpservererrorsthingstocheck)합니다.

## <a name="cannot_connect"></a> 디버거는 원격 컴퓨터에 연결할 수 없습니다.

로컬로 디버깅 하는 경우 64 비트 버전의 원격 디버거를 사용 하 여 64 비트 응용 프로그램을 디버깅할 수 있도록 Visual Studio는 32 비트 응용 프로그램을이 오류가 발생할 수 있습니다. 프로젝트 속성을 열고 프로젝트에 연결 하는 올바른 웹 서버 URL 구성 되어 있는지 확인 합니다. (열기 **속성 > 웹 > 서버** 또는 **속성 > 디버그** 프로젝트 형식에 따라.)

또한 호스트 파일을 사용 하는 경우 올바르게 구성 되어 있는지 확인 합니다. 예를 들어 호스트 파일, 프로젝트 속성에서와 같이 동일한 프로젝트 URL을 포함 해야 **속성 > 웹 > 서버** 또는 **속성 > 디버그**프로젝트 형식에 따라 합니다.

## <a name="see_help"></a> 참조 일반적인 구성 오류에 대 한 도움말입니다. 디버거 외부에서 웹 페이지를 실행 합니다. 추가 정보가 제공 될 수 있습니다.

- Visual Studio와 웹 서버는 동일한 컴퓨터에서 실행 중인 있습니다? 프로젝트 속성을 열고 프로젝트가 올바른 웹 서버에 연결 하 고 URL을 시작 하도록 구성 되어 있는지 확인 합니다. (열기 **속성 > 웹 > 서버** 또는 **속성 > 디버그** 프로젝트 형식에 따라.)

- 단계를 수행 되지 않으면 원격 디버깅 하는, [IIS 구성을 확인](#vxtbshttpservererrorsthingstocheck)합니다.

##  <a name="vxtbshttpservererrorsthingstocheck"></a> IIS 구성을 확인 하십시오.

문제를 해결 하려면 여기에서 자세히 설명 하는 단계를 수행한 후 및 디버깅을 다시 시도 하기 전에 IIS를 다시 설정 할 수도 있습니다. 관리자 권한 명령 프롬프트를 열고 입력 하 여 할 수 있습니다 `iisreset`합니다. 

* 중지 하 고 IIS 응용 프로그램 풀을 다시 시작 후 다시 시도 하세요. 

    응용 프로그램 풀 오류의 결과로 중지 있을 수 있습니다. 또는 적용 하는 다른 구성 변경을 중지 하 고 응용 프로그램 풀을 다시 시작 해야 할 수 있습니다.
    
    > [!NOTE]
    > 응용 프로그램 풀 중지를 유지 하는 경우 제어판에서 URL 재작성 모듈을 제거 해야 합니다. 웹 플랫폼 설치 관리자 (WebPI)를 사용 하 여 제거할 수 있습니다. 이 문제는 중요 한 시스템을 업그레이드 한 후 발생할 수 있습니다.

* 응용 프로그램 풀 구성을 확인 하 고, 필요한 경우 해결 한 후 다시 시도 하십시오.

    버전의 Visual Studio 프로젝트와 일치 하지 않는 ASP.NET에 대 한 응용 프로그램 풀을 구성할 수 있습니다. 응용 프로그램 풀에서 ASP.NET 버전을 업데이트 하 고 다시 시작 합니다. 자세한 내용은 참조 [IIS 8.0를 사용 하 여 ASP.NET 3.5 및 ASP.NET 4.5](/iis/get-started/whats-new-in-iis-8/iis-80-using-aspnet-35-and-aspnet-45)합니다.

    또한 암호 자격 증명 변경 되 면 응용 프로그램 풀 또는 웹 사이트에서이 정보도 업데이트 해야 합니다.  응용 프로그램 풀에서에서 자격 증명을 업데이트 **고급 설정 > 프로세스 모델 > Identity**합니다. 웹 사이트에서 자격 증명을 업데이트 **기본 설정 >로 연결 중...** . 응용 프로그램 풀을 다시 시작 합니다.
    
* 웹 응용 프로그램 폴더에 적절 한 권한이 있는지 확인 합니다.

    IIS_IUSRS, IUSR, 제공 하거나 특정 사용자와 연결 된는 [응용 프로그램 풀](/iis/manage/configuring-security/application-pool-identities) 읽기 및 웹 응용 프로그램 폴더에 대 한 권한을 실행 합니다. 문제를 해결 하 고 응용 프로그램 풀을 다시 시작 합니다.

* 올바른 버전의 ASP.NET IIS에 설치 되어 있는지 확인 합니다.

    일치 하지 않는 버전의 Visual Studio 프로젝트와 IIS에 ASP.NET이이 문제가 발생할 수 있습니다. Web.config의 프레임 워크 버전을 설정 해야 합니다. IIS에서 ASP.NET을 설치 하려면 사용 된 [웹 플랫폼 설치 관리자 (WebPI)](https://www.microsoft.com/web/downloads/platform.aspx)합니다. 참고: [IIS 8.0를 사용 하 여 ASP.NET 3.5 및 ASP.NET 4.5](/iis/get-started/whats-new-in-iis-8/iis-80-using-aspnet-35-and-aspnet-45) 또는 ASP.NET Core [Windows iis에서 호스트](https://docs.asp.net/en/latest/publishing/iis.html)합니다.
  
* IP 주소만 사용하는 경우의 인증 오류 해결

     기본적으로 IP 주소는 인터넷의 일부로 인식되는데 인터넷에서는 NTLM 인증을 수행할 수 없습니다. 웹 사이트를 IIS에서 인증을 요구 하도록 구성 된 경우이 인증이 실패 합니다. 이 문제를 해결 하려면 원격 컴퓨터의 IP 주소 대신의 이름을 지정할 수 있습니다.
     
## <a name="other-causes"></a>다른 원인

IIS 구성 문제를 유발 하지 않는지, 다음이 단계를 시도 합니다.

- 관리자 권한으로 Visual Studio를 다시 시작 하 고 다시 시도 하십시오.

    웹 배포를 사용 하는 등 몇 가지 ASP.NET 디버깅 시나리오는 Visual Studio에 대 한 상승 된 권한이 필요 합니다.
    
- Visual Studio의 여러 인스턴스를 실행 하는 경우 (관리자 권한)으로 Visual Studio의 한 인스턴스에 프로젝트를 다시 열고 다시 시도 하십시오.

- 로컬 주소를 가진 호스트 파일을 사용할 경우 컴퓨터의 IP 주소 대신 루프백 주소를 사용해 보세요.

    로컬 주소를 사용 하지 않는 경우 호스트 파일에 포함 되어 있는지 확인, 프로젝트 속성에서와 같이 동일한 프로젝트 URL **속성 > 웹 > 서버** 또는 **속성 > 디버그**에 따라 프로그램 프로젝트 유형입니다.

## <a name="more-troubleshooting-steps"></a>자세한 문제 해결 단계

* 서버에서 브라우저에서 localhost 페이지 표시.

     IIS가 올바르게 설치되어 있지 않은 경우 브라우저에 `http://localhost` 를 입력하면 오류가 발생합니다.
     
     IIS에 배포 하는 방법에 대 한 자세한 내용은 참조 하십시오. [IIS 8.0를 사용 하 여 ASP.NET 3.5 및 ASP.NET 4.5](/iis/get-started/whats-new-in-iis-8/iis-80-using-aspnet-35-and-aspnet-45) 및 ASP.NET Core [Windows iis에서 호스트](https://docs.asp.net/en/latest/publishing/iis.html)합니다.

* 서버에서 기본 ASP.NET 응용 프로그램을 만듭니다 (또는 기본 web.config 파일을 사용 하 여).

    디버거는 실행 되도록 앱을 가져올 수 없습니다, 서버에서 로컬로 기본 ASP.NET 응용 프로그램을 만들어 보세요 및 기본적인 응용 프로그램을 디버깅 하려고 합니다. (기본 ASP.NET MVC 템플릿에서 사용 하 여 삭제할 수 있습니다.) 기본 응용 프로그램을 디버그할 수, 하는 경우 두 가지 구성의 차이점을 확인할 수 있습니다 하 합니다. URL 재작성 규칙 같은 web.config 파일에서 설정 차이 찾습니다.

## <a name="see-also"></a>참고 항목  
 [웹 응용 프로그램 디버그: 오류 및 문제 해결](../debugger/debugging-web-applications-errors-and-troubleshooting.md)