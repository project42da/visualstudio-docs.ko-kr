---
title: "방법: IIS 속성 설정 확인 | Microsoft Docs"
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
- IIS, property settings
- debugging Web applications, troubleshooting
- IIS administration tool
- Web applications, setting properties
- properties [debugger], setting with IIS administration tool
ms.assetid: 9efc50bf-02fb-4750-9b3e-f03c38f10d8b
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c0d58ea851423e9239d8685f89890b5d9e152d53
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-verify-iis-property-settings"></a>방법: IIS 속성 설정 확인
IIS 관리 도구를 사용하여 웹 응용 프로그램의 속성을 설정할 수 있습니다. 이러한 속성이 제대로 설정되어 있어야 응용 프로그램이 실행되므로 일반적으로 문제를 해결하는 데는 이러한 설정을 확인하는 단계가 필요합니다.  
  
> [!NOTE]
>  표시되는 대화 상자와 메뉴 명령은 활성 설정이나 버전에 따라 도움말에서 설명하는 것과 다를 수 있습니다. 설정을 변경하려면 **도구** 메뉴에서 **설정 가져오기 및 내보내기** 를 선택합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](../ide/personalizing-the-visual-studio-ide.md)을 참조하세요.  
  
### <a name="to-check-iis-settings-for-the-web-application"></a>웹 응용 프로그램에 대한 IIS 설정을 확인하려면  
  
1.  열기는 **관리 도구** 창:에 **시작** 메뉴에서 **프로그램**, 클릭 하 고 **관리 도구**합니다. 경우 **관리 도구** 에 표시 되지 않으면는 **프로그램** 메뉴를 클릭에서 찾습니다는 **제어판**합니다.  
  
    -   Windows 2000에서 선택 **인터넷 서비스 관리자**합니다.  
  
    -   Windows XP에서 선택 **인터넷 정보 서비스**합니다.  
  
    -   Windows Server 2003에서 두 번 클릭 **사용자 서버 관리**합니다.  
  
         **사용자 서버 관리** 창이 열립니다. 아래 **응용 프로그램 서버**, 클릭 **이 응용 프로그램 서버를 관리할**합니다.  
  
         **응용 프로그램 서버** 창이 열립니다. 열기는 **인터넷 정보 서비스 (IIS) 관리자** 왼쪽된 창에서 노드.  
  
2.  대화 상자에서 현재 컴퓨터의 트리 컨트롤 노드를 클릭합니다. 클릭는 **웹사이트** 노드를 웹 응용 프로그램의 노드를 선택 합니다. 웹 사이트 노드 및의 형제 수는 **기본 웹 사이트** 노드 또는 기존 웹 사이트 노드 아래에 있는 가상 디렉터리 노드일 합니다.  
  
3.  웹 응용 프로그램을 마우스 오른쪽 단추로 클릭 하 고 바로 가기 메뉴를 클릭 **속성**합니다.  
  
4.  웹 응용 프로그램에 대한 보안 설정을 확인합니다.  
  
    1.  웹 응용 프로그램에서 **속성** 창 클릭는 **디렉터리 보안** 탭을 클릭 **편집**합니다.  
  
    2.  에 **인증 방법을** 대화 상자에서 **익명 액세스 가능** 및 **Windows 통합 인증** 아직 선택 되지 않은 경우.  
  
    3.  클릭 **확인** 를 닫으려면는 **인증 방법을** 대화 상자.  
  
5.  ATL 서버 응용 프로그램의 경우 DEBUG 동사가 ISAPI 확장과 관련이 있는지 여부를 확인합니다. 자세한 내용은 참조 [하는 방법: 확장명을 가진 디버그 동사 연결](http://msdn.microsoft.com/en-us/50d261d3-4bd4-41c0-b44e-3591086f121e)합니다.  
  
6.  에 대 한 프로그램 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 응용 프로그램을 하는지 확인 한 가상 폴더 응용 프로그램에 설정 된 응용 프로그램 이름이 **인터넷 정보 서비스 (IIS) 관리자**, **인터넷 서비스 관리자** 또는  **인터넷 정보 서비스**합니다.  
  
    1.  웹 응용 프로그램에서 **속성** 창에서는 **디렉터리** 응용 프로그램이 가상 디렉터리에 있으면 탭 또는 **홈 디렉터리** 이면 응용 프로그램에서 탭 웹 사이트입니다.  
  
    2.  확인에서 이름을 **로컬 경로** 응용 프로그램이 실제로 배포 된 디렉터리의 이름과 일치 합니다.  
  
    3.  아래 **응용 프로그램 설정**, 응용 프로그램을 포함 하는 루트 디렉터리의 이름을 입력 합니다.  
  
    4.  클릭 **확인** 를 닫으려면는 **속성** 대화 상자.  
  
7.  에 대 한는 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 응용 프로그램을 클릭는 **ASP.NET** 탭 하 고 확인 하는 올바른 버전의 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 지정 합니다.  
  
8.  클릭 **확인** 를 닫으려면는 **속성** 대화 상자.  
  
9. 클릭 **확인** 를 닫으려면는 **인터넷 정보 서비스 (IIS) 관리자**, **인터넷 서비스 관리자**, 또는 **인터넷 정보 서비스**대화 상자.  
  
## <a name="see-also"></a>참고 항목  
 [문제 해결](../debugger/debugging-web-applications-troubleshooting.md)