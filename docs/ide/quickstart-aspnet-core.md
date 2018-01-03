---
title: "Visual Studio를 사용하여 C#으로 ASP.NET Core 웹앱 만들기 | Microsoft Docs"
ms.custom: 
ms.date: 10/10/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-acquisition
ms.tgt_pltfrm: 
ms.topic: quickstart
author: gewarren
ms.author: gewarren
manager: ghogen
dev_langs: CSharp
ms.workload:
- aspnet
- dotnetcore
ms.openlocfilehash: 66c1b3ca7a877c001bc3aeb69c5331fdc828aad8
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="quickstart-use-visual-studio-to-create-your-first-aspnet-core-web-app"></a>빠른 시작: Visual Studio를 사용하여 첫 번째 ASP.NET Core 웹앱 만들기

Visual Studio IDE(통합 개발 환경)에 대한 이 5 ~ 10분 분량의 소개에서는 간단한 C # ASP.NET Core 웹 응용 프로그램을 만듭니다. 아직 Visual Studio를 설치하지 않은 경우 [여기](http://www.visualstudio.com)에서 평가판을 설치합니다.

## <a name="create-a-project"></a>프로젝트 만들기

먼저, ASP.NET Core 웹 응용 프로그램 프로젝트를 만듭니다. 프로젝트 형식에는 무엇인가 추가하기 전에 기능 웹 응용 프로그램을 구성하는 템플릿 파일이 포함되어 있습니다.

1. Visual Studio 2017을 엽니다.

1. 메뉴 모음에서 **파일**, **새로 만들기**, **프로젝트...**를 차례로 선택합니다.

1. **새 프로젝트** 대화 상자의 왼쪽 차에서 **Visual C#**을 확장한 후 **.NET Core**를 선택합니다. 가운데 창에서 **ASP.NET Core 웹 응용 프로그램**을 선택한 후 **확인**을 선택합니다.

     **.NET Core** 프로젝트 템플릿이 표시되지 않으면 **새 프로젝트** 대화 상자를 취소하고 나가 메뉴 모음에서 **도구**, **도구 및 기능 가져오기...**를 선택합니다. Visual Studio 설치 관리자가 시작됩니다. **ASP.NET 및 웹 개발** 워크로드를 선택한 후 **수정**을 선택합니다.

     ![VS 설치 관리자에서 ASP.NET 워크로드](../ide/media/quickstart-aspnet-workload.png)

1. **새 ASP.NET Core 웹 응용 프로그램** 대화 상자의 상단 드롭다운 메뉴에서 **ASP.NET Core 2.0**을 선택합니다. (목록에 **ASP.NET Core 2.0**이 표시되지 않으면 대화 상자 맨 위에 있는 노란색 표시줄에 나타나는 **다운로드** 링크에 따라 설치합니다.) **확인**을 선택합니다.

   ![새 ASP.NET Core 웹 응용 프로그램 대화 상자](../ide/media/quickstart-aspnet-core20.png)

## <a name="explore-the-ide"></a>IDE 탐색

1. **솔루션 탐색기** 도구 모음에서 **페이지** 폴더를 확장한 후 **About.cshtml**을 선택하고 편집기에서 엽니다. 이 파일은 웹 응용 프로그램의 **정보** 페이지에 해당합니다.

1. 편집기에서 `AboutModel`을 선택한 후 **F12** 키를 누르거나 바로 가기(마우스 오른쪽 단추 클릭) 메뉴에서 **정의로 이동**을 선택합니다. 이 명령으로 `AboutModel` C# 클래스 정의가 표시됩니다.

   ![[정의로 이동] 바로 가기 메뉴](../ide/media/quickstart-aspnet-gotodefinition.png)

1. 다음으로, 간단한 바로 가기를 사용하여 파일 맨 위에서 `using` 지시문을 정리합니다. 회색으로 표시된 using 지시문을 선택하면 [빠른 작업](../ide/quick-actions.md) 전구 메뉴가 캐럿 바로 아래 또는 왼쪽 여백에 나타납니다. 전구 메뉴를 선택한 후 **불필요한 Using 제거**를 선택합니다.

     파일에서 불필요한 using이 삭제됩니다.

1. `OnGet()` 메서드에서 본문을 다음 코드로 변경합니다.

 ```csharp
 public void OnGet()
 {
     string directory = Environment.CurrentDirectory;
     Message = String.Format("Your directory is {0}.", directory);
 }
 ```

1. 이러한 형식은 범위에 없으므로 두 개의 물결선이 **환경** 및 **문자열** 아래에 나타납니다. **오류 목록** 도구 모음을 열고 같은 오류가 나열되는지 확인합니다. (**오류 목록** 도구 모음이 표시되지 않으면 메뉴 모음에서 **보기**, **오류 목록**을 선택합니다.)

   ![오류 목록](../ide/media/quickstart-aspnet-errorlist.png)

1. 편집기 창에서 오류가 있는 줄에 커서를 놓고 왼쪽 여백에서 빠른 작업 전구 메뉴를 선택합니다. 드롭다운 메뉴에서 **using System;**을 선택하여 이 지시문을 파일 맨 위에 추가하고 오류를 해결합니다.

## <a name="run-the-application"></a>응용 프로그램 실행

1. **Ctrl+F5** 키를 눌러 응용 프로그램을 실행하고 웹 브라우저에서 엽니다.

1. 웹 사이트의 맨 위에서 **정보**를 선택하여 **정보** 페이지에 대한 `OnGet()` 메서드에 추가한 디렉터리 메시지를 표시합니다.

1. 웹 브라우저를 닫습니다.

> [!NOTE]
> **'IIS Express' 웹 서버에 연결할 수 없습니다**라는 오류 메시지가 발생하면 Visual Studio를 닫은 후 마우스 오른쪽 단추 클릭 또는 상황에 맞는 메뉴에서 **관리자 권한으로 실행** 옵션을 사용하여 엽니다. 그런 다음 응용 프로그램을 다시 실행합니다.

이 빠른 시작을 완료한 것을 축하 드립니다! Visual Studio IDE를 이해하는 데 도움이 되었기를 바랍니다. 해당 기능을 보다 자세히 알아보려면 목차에서 **자습서** 섹션에 있는 자습서를 읽어보세요.

## <a name="see-also"></a>참고 항목

[Visual Studio를 사용하여 C# 및 Visual Basic 시작](getting-started-with-visual-csharp-and-visual-basic.md)  
[ASP.NET Core에서 Razor 페이지 시작](/aspnet/core/tutorials/razor-pages/razor-pages-start)