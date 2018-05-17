---
title: 사용자 권한 및 Visual Studio
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- Visual Studio, user permissions
- user permissions
- administrative privileges
- permissions
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 08b12e09348a28276d0c5d2f375b26e75c1ac3c5
ms.sourcegitcommit: 56018fb1f52f17bf35ae2ce71c50c763486e6173
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/04/2018
---
# <a name="user-permissions-and-visual-studio"></a>사용자 권한 및 Visual Studio

보안을 위해 가급적 일반 사용자로 Visual Studio를 실행해야 합니다.

> [!WARNING]
> 신뢰할 수 있는 사람이나 신뢰할 수 있는 위치에서 제공되지 않는 Visual Studio 솔루션은 컴파일하거나 실행하거나 디버깅하지 마십시오.

Visual Studio IDE에서는 일반 사용자로 거의 모든 작업을 할 수 있지만 다음 작업을 완료하려면 관리자 권한이 필요합니다.

|영역|작업|추가 정보|
|----------|----------|--------------------------|
|설치|Visual Studio를 설치합니다.|[Visual Studio 설치](../install/install-visual-studio.md)|
||로컬 도움말 콘텐츠 설치, 업데이트 또는 제거|[로컬 콘텐츠 설치 및 관리](../ide/install-and-manage-local-content.md)|
|응용 프로그램 종류|SharePoint용 솔루션 개발|[SharePoint 솔루션 개발 요구 사항](../sharepoint/requirements-for-developing-sharepoint-solutions.md)|  
||[!INCLUDE[win8_appstore_long](../debugger/includes/win8_appstore_long_md.md)]의 개발자 라이선스 취득|[개발자 라이선스 얻기](http://go.microsoft.com/fwlink/?LinkID=241313)|
|도구 상자|**도구 상자**에 클래식 COM 컨트롤 추가.|[도구 상자](../ide/reference/toolbox.md)|
|추가 기능|IDE에서 기본 COM을 사용하여 작성한 추가 기능 설치 및 사용|[추가 기능 및 마법사 만들기](http://msdn.microsoft.com/Library/c5a47c21-6668-4de3-898d-afa969317e73)|
|빌드|구성 요소를 등록하는 빌드 후 이벤트 사용|[사용자 지정 빌드 단계 및 빌드 이벤트 이해](/cpp/ide/understanding-custom-build-steps-and-build-events)|
||C++ 프로젝트를 빌드할 때 등록 단계 포함|[사용자 지정 빌드 단계 및 빌드 이벤트 이해](/cpp/ide/understanding-custom-build-steps-and-build-events)|
|디버깅|높은 권한으로 실행되는 응용 프로그램 디버깅|[디버거 설정 및 준비](../debugger/debugger-settings-and-preparation.md)|
||ASP.NET 웹 사이트와 같이 다른 사용자 계정으로 실행되는 응용 프로그램 디버깅|[ASP.NET 및 AJAX 응용 프로그램 디버그](../debugger/debugging-aspnet-and-ajax-applications.md)|
||XBAP(XAML 브라우저 응용 프로그램) 영역에서 디버깅|[WPF 호스트(PresentationHost.exe)](/dotnet/framework/wpf/app-development/wpf-host-presentationhost-exe)|
||에뮬레이터를 사용하여 Microsoft Azure용 클라우드 서비스 프로젝트 디버깅|[Visual Studio에서 클라우드 서비스 디버깅](http://go.microsoft.com/fwlink/?LinkId=266725)|
||원격 디버깅을 위한 방화벽 구성|[원격 디버깅](../debugger/remote-debugging.md)|
|성능 도구|응용 프로그램 프로파일링|[초보자를 위한 성능 프로파일링 지침](../profiling/beginners-guide-to-performance-profiling.md)|
|배포|로컬 컴퓨터에서 IIS(인터넷 정보 서비스)에 웹 응용 프로그램 배포|[isual Studio 또는 Visual Web Developer를 사용하여 호스팅 제공업체에 ASP.NET 웹 응용 프로그램 배포: IIS에 테스트 환경으로 배포](http://go.microsoft.com/fwlink/?LinkId=266478)|
>>>>>>> 346075117af3d2bd1fddd9c3aca24516a39fa6a3

## <a name="run-visual-studio-as-an-administrator"></a>관리자 권한으로 Visual Studio 실행

IDE를 시작할 때마다 관리자 권한으로 Visual Studio를 실행하거나 응용 프로그램 바로 가기를 수정하여 항상 관리자 권한으로 실행할 수 있습니다. 자세한 내용은 Windows 도움말을 참조하십시오.

### <a name="run-visual-studio-with-administrative-permissions"></a>관리자 권한으로 Visual Studio 실행

이러한 지침은 Windows 10에 대한 것입니다. 다른 버전의 Windows와 유사합니다.

1. **시작** 메뉴를 열고 Visual Studio 2017로 스크롤합니다.

1. **Visual Studio 2017**의 마우스 오른쪽 단추 클릭 또는 상황에 맞는 메뉴에서 **추가** > **관리자 권한으로 실행**을 선택합니다.

     Visual Studio가 시작되면 제목 표시줄의 제품 이름 뒤에 **(관리자)** 가 나타납니다.

## <a name="see-also"></a>참고 항목

- [Visual Studio 프로젝트 포팅, 마이그레이션, 업그레이드](../porting/port-migrate-and-upgrade-visual-studio-projects.md)
- [Visual Studio 설치](../install/install-visual-studio.md)