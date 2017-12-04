---
title: "Visual Studio에서 사용자 지정 시작 페이지 설치 또는 시작 항목 변경 | Microsoft Docs"
ms.custom: 
ms.date: 02/01/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.startpage
- VS.StartPage.HowDoI
- vs.ToolsOptionsPages.Startup
helpviewer_keywords:
- Start Page [Visual Studio]
- customizing Start Page [Visual Studio]
- Visual Studio Start page
caps.latest.revision: "45"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 45cfb501103c762f7af6fc130a981028c262540b
ms.sourcegitcommit: eb954434c34b4df6fd2264266381b23ce9e6204a
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/22/2017
---
# <a name="customize-the-start-page-for-visual-studio"></a>Visual Studio 시작 페이지 사용자 지정

**프로젝트 열기** 대화 상자 표시 또는 가장 최근에 로드한 솔루션 열기 등 Visual Studio의 시작 환경을 다양한 방법으로 사용자 지정할 수 있습니다. 도구 창에서 실행되는 WPF(Windows Presentation Foundation) XAML 페이지인 사용자 지정 시작 페이지를 표시하고 Visual Studio 내부에 있는 명령을 실행할 수도 있습니다.

## <a name="to-change-the-startup-item"></a>시작 항목을 변경하려면

1. 메뉴 모음에서 **도구**, **옵션**을 선택합니다.

1. **환경**을 확장한 다음 **시작**을 선택합니다.

1. **시작 시** 목록에서 Visual Studio가 시작된 후 표시할 항목을 선택합니다.

## <a name="to-show-a-custom-start-page"></a>사용자 지정 시작 페이지를 표시하려면

Visual Studio SDK를 사용하여 [사용자 지정 시작 페이지를 만들거나](../extensibility/creating-a-custom-start-page.md), 다른 사용자가 이미 만든 시작 페이지를 사용할 수 있습니다. 예를 들어 [Visual Studio Marketplace](https://marketplace.visualstudio.com/search?target=VS&category=Tools&vsVersion=&subCategory=Start%20Pages&sortBy=Downloads)에서 사용자 지정 시작 페이지를 찾을 수 있습니다.

사용자 지정 시작 페이지를 설치하려면 .vsix 파일을 열거나 시작 페이지 파일을 복사하여 컴퓨터의 **%USERPROFILE%\Documents\Visual Studio 2017\StartPages** 폴더에 붙여넣습니다.

### <a name="to-select-which-custom-start-page-to-display"></a>표시할 사용자 지정 시작 페이지를 선택하려면

1. 메뉴 모음에서 **도구**, **옵션**을 선택합니다.

1. **환경**을 확장한 다음 **시작**을 선택합니다.

1. **시작 페이지 사용자 지정** 목록에서 원하는 페이지를 선택합니다.

> [!NOTE]
> 사용자 지정 시작 페이지에 오류가 있어 Visual Studio에 충돌이 발생하면 안전 모드에서 Visual Studio를 시작한 다음 기본 시작 페이지를 사용하도록 설정할 수 있습니다. [/SafeMode(devenv.exe)](../ide/reference/safemode-devenv-exe.md)를 참조하세요.

## <a name="see-also"></a>참고 항목

[Visual Studio IDE 개인 설정](../ide/personalizing-the-visual-studio-ide.md)
