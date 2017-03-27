---
title: "사용자 권한 및 Visual Studio | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Visual Studio, user permissions
- user permissions
- administrative privileges
- permissions
ms.assetid: 70485ed7-6342-41bf-8250-7a6826e21b98
caps.latest.revision: 14
author: kempb
ms.author: kempb
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Human Translation
ms.sourcegitcommit: a42f5a30375192c89c9984e40ba0104da98d7253
ms.openlocfilehash: dc32236dad42ec169fc1c7a243b7c67fd5a8dbf3
ms.lasthandoff: 03/07/2017

---
# <a name="user-permissions-and-visual-studio"></a>사용자 권한 및 Visual Studio
보안을 위해 가급적 일반 사용자로 Visual Studio를 실행해야 합니다.  

> [!WARNING]
>  신뢰할 수 있는 사람이나 신뢰할 수 있는 위치에서 제공되지 않는 Visual Studio 솔루션은 컴파일하거나 실행하거나 디버깅하지 마십시오.  

 Visual Studio IDE에서는 일반 사용자로 거의 모든 작업을 할 수 있지만 다음 작업을 완료하려면 관리자 권한이 필요합니다.  

|영역|작업|추가 정보|  
|----------|----------|--------------------------|  
|설치|Visual Studio를 설치합니다.|[Visual Studio 설치](../install/install-visual-studio.md)|  
||로컬 도움말 콘텐츠 설치, 업데이트 또는 제거|[로컬 콘텐츠 설치 및 관리](../ide/install-and-manage-local-content.md)|  
|응용 프로그램 종류|SharePoint용 솔루션 개발|[SharePoint 솔루션 개발 요구 사항](/office-dev/office-dev/requirements-for-developing-sharepoint-solutions)|  
||[!INCLUDE[win8_appstore_long](../debugger/includes/win8_appstore_long_md.md)]의 개발자 라이선스 취득|[개발자 라이선스 얻기(Windows 스토어 앱)](http://go.microsoft.com/fwlink/?LinkID=241313)|  
|도구 상자|**도구 상자**에 클래식 COM 컨트롤 추가.|[도구 상자 사용](../ide/using-the-toolbox.md)|  
|추가 기능|IDE에서 기본 COM을 사용하여 작성한 추가 기능 설치 및 사용|[추가 기능 및 마법사 만들기](http://msdn.microsoft.com/Library/c5a47c21-6668-4de3-898d-afa969317e73)|  
|빌드|구성 요소를 등록하는 빌드 후 이벤트 사용|[사용자 지정 빌드 단계 및 빌드 이벤트 이해](/visual-cpp/ide/understanding-custom-build-steps-and-build-events)|  
||C++ 프로젝트를 빌드할 때 등록 단계 포함|[사용자 지정 빌드 단계 및 빌드 이벤트 이해](/visual-cpp/ide/understanding-custom-build-steps-and-build-events)|  
|디버깅|높은 권한으로 실행되는 응용 프로그램 디버깅|[디버거 설정 및 준비](../debugger/debugger-settings-and-preparation.md)|  
||ASP.NET 웹 사이트와 같이 다른 사용자 계정으로 실행되는 응용 프로그램 디버깅|[ASP.NET 및 AJAX 응용 프로그램 디버그](../debugger/debugging-aspnet-and-ajax-applications.md)|  
||XBAP(XAML 브라우저 응용 프로그램) 영역에서 디버깅|[WPF 호스트(PresentationHost.exe)](http://msdn.microsoft.com/Library/3215bfa1-722c-4ac8-a7c5-bdd02d30afbd)|  
||에뮬레이터를 사용하여 Microsoft Azure용 클라우드 서비스 프로젝트 디버깅|[Visual Studio에서 Azure 클라우드 서비스 또는 가상 컴퓨터 디버깅](http://go.microsoft.com/fwlink/?LinkId=266725)|  
||원격 디버깅을 위한 방화벽 구성|[원격 디버깅](../debugger/remote-debugging.md)|  
|성능 도구|응용 프로그램 프로파일링|[초보자를 위한 성능 프로파일링 지침](../profiling/beginners-guide-to-performance-profiling.md)|  
|배포|로컬 컴퓨터에서 IIS(인터넷 정보 서비스)에 웹 응용 프로그램 배포|[Deploying an ASP.NET Web Application to a Hosting Provider using Visual Studio or Visual Web Developer: Deploying to IIS as a Test Environment](http://go.microsoft.com/fwlink/?LinkId=266478)(Visual Studio 또는 Visual Web Developer를 사용하여 호스팅 제공업체에 ASP.NET 웹 응용 프로그램 배포: IIS에 테스트 환경으로 배포)|

## <a name="running-visual-studio-as-an-administrator"></a>관리자로 Visual Studio 실행  
 IDE를 시작할 때마다 관리자 권한으로 Visual Studio를 실행하거나 응용 프로그램 바로 가기를 수정하여 항상 관리자 권한으로 실행할 수 있습니다. 자세한 내용은 Windows 도움말을 참조하십시오.  

#### <a name="to-run-visual-studio-with-administrative-permissions-on-includewin8debuggerincludeswin8mdmd-includewin81debuggerincludeswin81mdmd-includewinserver8debuggerincludeswinserver8mdmd-or-includewinblueserver2ideincludeswinblueserver2mdmd"></a>[!INCLUDE[win8](../debugger/includes/win8_md.md)], [!INCLUDE[win81](../debugger/includes/win81_md.md)], [!INCLUDE[winserver8](../debugger/includes/winserver8_md.md)] 또는 [!INCLUDE[winblue_server_2](../ide/includes/winblue_server_2_md.md)]에서 관리자 권한으로 Visual Studio를 실행하려면  

1.  **시작** 화면에서 **Visual Studio**를 입력합니다. 설치된 Visual Studio의 버전이 표시되어야 합니다.  

2.  시작할 Visual Studio의 버전을 선택한 후 바로 가기 메뉴를 표시합니다(화면 맨 아래에 표시). **관리자 권한으로 실행**을 선택합니다.  

     Visual Studio가 시작되면 제목 표시줄의 제품 이름 뒤에 **(관리자)**가 나타납니다.  

#### <a name="to-run-visual-studio-with-administrative-permissions-on-includewin7debuggerincludeswin7mdmd-or-includewinsvr08r2debuggerincludeswinsvr08r2mdmd"></a>[!INCLUDE[win7](../debugger/includes/win7_md.md)] 또는 [!INCLUDE[winsvr08_r2](../debugger/includes/winsvr08_r2_md.md)]에서 관리자 권한으로 Visual Studio를 실행하려면  

1.  **시작** 메뉴에서 **모든 프로그램**을 선택합니다.  

2.  **Microsoft Visual Studio** *버전* 폴더에서 **Visual Studio** *버전*을 선택하고 바로 가기 메뉴를 연 다음 **관리자 권한으로 실행**을 선택합니다.  

     Visual Studio가 시작되면 제목 표시줄의 제품 이름 뒤에 **(관리자)**가 나타납니다.  

## <a name="see-also"></a>참고 항목  
 [Visual Studio 프로젝트 포팅, 마이그레이션, 업그레이드](../porting/port-migrate-and-upgrade-visual-studio-projects.md)   
 [Visual Studio 설치](../install/install-visual-studio.md)

