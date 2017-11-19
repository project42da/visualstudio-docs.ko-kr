---
title: "Visual Studio 확장 개발 하기 시작 | Microsoft Docs"
ms.custom: 
ms.date: 09/18/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- getting started, Visual Studio integration
- Visual Studio, integration
ms.assetid: 8fe5e2ab-a424-4173-9d39-dd082c4d58d0
caps.latest.revision: "29"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 2d788121e81af48cb972631d0845ad7b4317818b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="starting-to-develop-visual-studio-extensions"></a>Visual Studio 확장 개발 하기 시작
하기 전에 Visual Studio 확장을 작성해 본 경험이 있는 경우 몇 가지 질문 있을 수도 있습니다. 여기에 가장 일반적인 것 중 일부 나열한 했습니다. 피드백 단추를 사용 하 여 원하는 정보 보이지 않으면 (**이 페이지가 도움이 되었나요?** 화면 맨 아래에) 대상에 게 요청 합니다.  
  
## <a name="what-software-do-i-need-to-develop-visual-studio-extensions"></a>Visual Studio 확장을 개발 하는 소프트웨어 필요 합니까?  
 Visual Studio 확장을 개발 하기 위해 Visual Studio 외에도 Visual Studio SDK를 설치 해야 합니다. 일반 설치의 일부로 Visual Studio SDK를 설치할 수 있습니다 또는 나중에 설치할 수 있습니다. Visual Studio SDK를 설치 하는 방법에 대 한 자세한 내용은 참조 [Visual Studio SDK](../extensibility/visual-studio-sdk.md)합니다.  
  
## <a name="what-kinds-of-things-can-i-do-with-visual-studio-extensions"></a>Visual Studio 확장을 할 수 있는 항목의 유형은 있습니까?  
 sky 상상해 다른 Visual Studio 확장에 관한 제한의입니다. 대부분의 확장을 사용 하면 코드를 작성 하는 관련이 사항이 있지만 이것이 없는 합니다. 확장을 빌드할 수의 종류의 몇 가지 예는 다음과 같습니다.  
  
-   구문 색 지정, IntelliSense, 컴파일러 및 디버그 지원와 Visual Studio에 포함 되지 않은 언어에 대 한 지원  
  
-   추가 템플릿, 코드 리팩터링, 새 대화 상자 또는 도구 창을 여 핵심을 확장 하는 생산성 도구 IDE 효과  
  
-   데이터 디자인 또는 클라우드 지원 같은 시나리오에 대 한 도메인 별로 디자이너  
  
 체크 아웃 확장의 예는 [Visual Studio 마켓플레이스](https://marketplace.visualstudio.com/vs)합니다. 다양 한 확장 프로그램을 기반으로 열려 있는 및 마켓플레이스에 링크 해당 GitHub 리포지토리를 포함 합니다. 
  
## <a name="which-visual-studio-features-can-i-extend"></a>Visual Studio 기능을 확장할 수 있습니까?  
 이론적으로, Visual Studio의 거의 모든 부분을 확장할 수 있습니다: 메뉴, 도구 모음, 명령, windows, 솔루션, 프로젝트, 편집기, 및 등입니다.  
  
 실제로 대부분의 사용자가을 확장 하려면 기능은 명령, 메뉴 및 도구 모음, windows, IntelliSense, 및 프로젝트를 발견 했습니다. 관련 섹션에 대 한 링크는 다음과 같습니다.  
  
-   [메뉴 및 명령을 확장](../extensibility/extending-menus-and-commands.md): Visual Studio 메뉴 및 도구 모음에 직접 항목을 추가 합니다. 새 Visual Studio 기능 또는 자신의 외부 도우미 응용 프로그램을 시작 하려면 사용할 수 있습니다. 메뉴 항목에 대 한 사용자 지정 바로 가기 키를 제공할 수도 있습니다.  
  
-   [확장 및 사용자 지정 도구 창의](../extensibility/extending-and-customizing-tool-windows.md): 기존 도구 창 확장 또는 사용자 고유의 도구 창을 만들 수 있습니다. 예를 들어, 새 속성을 추가할 수 있습니다는 **속성**, 또는 추가 기능을 추가 하는 새 도구 창을 만들 수 있습니다.  
  
-   [편집기와 언어 서비스 확장](../extensibility/editor-and-language-service-extensions.md): 고유의 사용자 지정의 Visual Studio 언어에 대해 제공 된 IntelliSense를 추가 하거나 새 프로그래밍 언어에 대 한 지원을 생성 합니다. 새 문 완성, 제안 및 새 나타나도록을 만들 수 있습니다. 전구를 사용 리팩터링 제안을 추가할 수 있으며, 새 프로그래밍 언어를 지원 하기 위해 코드를 수정 합니다.  
  
-   [프로젝트 확장](../extensibility/extending-projects.md)  
  
-   [사용자 설정 및 옵션 확장](../extensibility/extending-user-settings-and-options.md)  
  
-   [속성 및 속성 창 확장](../extensibility/extending-properties-and-the-property-window.md)  
  
-   [Visual Studio의 다른 부분 확장](../extensibility/extending-other-parts-of-visual-studio.md)  
  
-   [Visual Studio Shell(격리)](../extensibility/visual-studio-isolated-shell.md)  
  
##  <a name="BKMK_ProjectTemplate"></a>VSSDK 여 어떤 프로젝트 템플릿이 제공 됩니다.  
 확장의 두 가지 주요 유형은 Vspackage 및 MEF 확장입니다. 일반적으로 VSPackage 확장 사용 하거나 명령, 도구 창 및 프로젝트를 확장 하는 확장에 사용 됩니다. MEF 확장을 확장 하거나 Visual Studio 편집기를 사용자 지정 하는 데 사용 됩니다.  
  
 Visual C# 및 Visual Basic 확장에 대 한 VSSDK를 메뉴 명령과 도구 창, 편집기 확장을 만드는 새 항목 템플릿은 함께 사용할 수 있는 빈 VSIX 프로젝트 템플릿을 제공 합니다. 또한 다른 사용자에 게 배포에 대 한이 서식 파일을 패키지 프로젝트 템플릿, 코드 조각 및 기타 아티팩트를 사용할 수 있습니다.  
  
 C + +에서 VSPackage 마법사 메뉴 명령, 도구 창 및 사용자 지정 편집기를 추가 하는 코드를 제공 합니다.  
  
 격리 셸 템플릿이 브랜딩 및 사용자 고유의로 배포할 수 있는 Visual Studio shell의 버전에서는 확장 패키지에 사용 됩니다. 다음 항목은 각 종류의 확장을 시작 하는 방법을 보여 줍니다.  
  
-   메뉴 명령을: [메뉴 명령을 사용 하 여 확장 만들기](../extensibility/creating-an-extension-with-a-menu-command.md)  
  
-   도구 창을: [도구 창 확장 만들기](../extensibility/creating-an-extension-with-a-tool-window.md)  
  
-   편집기 확장: [확장 편집기 항목 템플릿 만들기](../extensibility/creating-an-extension-with-an-editor-item-template.md)  
  
-   기본 Vspackage: [VSPackage를 사용 하 여 확장 만들기](../extensibility/creating-an-extension-with-a-vspackage.md)  
  
-   VSIX 프로젝트 템플릿은: [VSIX 프로젝트 템플릿을 사용 하 여 시작](../extensibility/getting-started-with-the-vsix-project-template.md)  
  
-   Visual Studio 격리 셸: [연습: 기본 격리 셸 응용 프로그램 만들기](../extensibility/walkthrough-creating-a-basic-isolated-shell-application.md)  
  
## <a name="how-do-i-get-my-extension-to-look-like-visual-studio"></a>Visual Studio 모양 my 확장 가져오기  
 확장에 대 한 UI를 디자인 하기 위한 팁 가져오기 [Visual Studio 사용자 환경 지침](../extensibility/ux-guidelines/visual-studio-user-experience-guidelines.md)합니다.  
  
## <a name="where-can-i-find-examples-of-vssdk-code"></a>VSSDK 코드 예는 어디서 찾을 수 있습니까?  
 이전 섹션에 나열 된 링크의 각 특정 기능을 구현 하는 방법을 보여 주는 단계별 연습이 포함. 찾을 수 있습니다 오픈 소스 github에서 VSSDK 샘플 [Visual Studio 샘플](https://github.com/Microsoft/VSSDK-Extensibility-Samples)합니다.  
  
## <a name="how-can-i-distribute-my-extension"></a>My 확장을 배포할 수는 방법  
 다른 컴퓨터에 확장을 설치 하거나 두 번 클릭 하 여 설치 하는.vsix 파일로 친구 들에 게 보낼 수 있습니다. VSIX 패키지에 대 한 자세한 내용을 확인할 수 [Visual Studio 확장명 전달](../extensibility/shipping-visual-studio-extensions.md)합니다.  
  
 Visual Studio 고객의 많은 정보를 볼 수 있도록 Visual Studio 마켓플레이스에 확장 프로그램을 게시할 수도 있습니다. 마켓플레이스 확장 패키지의 예제를 보려면 [연습: Visual Studio Extension 게시](../extensibility/walkthrough-publishing-a-visual-studio-extension.md)합니다. 마켓플레이스에서 게시 하기 위해 수행 해야 하는 방법에 대 한 자세한 내용은 참조 [제품 및 Visual Studio 용 확장명](https://docs.microsoft.com/en-us/vsts/integrate/ide/extensions/overview)합니다.
