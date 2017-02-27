---
title: "Visual Studio 확장 프로그램을 개발 하기 시작 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "시작, 시작된 Visual Studio 통합"
  - "Visual Studio 통합"
ms.assetid: 8fe5e2ab-a424-4173-9d39-dd082c4d58d0
caps.latest.revision: 29
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 29
---
# Visual Studio 확장 프로그램을 개발 하기 시작
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

하기 전에 Visual Studio 확장을 작성해 본 경험이 하는 경우 몇 가지 질문이 있을 수 있습니다. 일부 가장 자주 여기 나열 된 것입니다. 원하는 정보를 표시 되지 않으면, 피드백 단추를 사용 \(**이 페이지를 도움이 되었습니까?** 화면 맨 아래에\) 대상에 게 요청 합니다.  
  
## 소프트웨어 Visual Studio 확장 개발 수 있나요?  
 Visual Studio 확장 프로그램을 개발 하기 위해 Visual Studio 2015 외에도 Visual Studio 2015 SDK를 설치 해야 합니다.   일반 설치의 일부로 Visual Studio 2015 SDK를 설치할 수 또는 나중에 설치할 수 있습니다. Visual Studio SDK를 설치 하는 방법에 대 한 자세한 내용은 참조 [Visual Studio SDK](../extensibility/visual-studio-sdk.md)합니다.  
  
## Visual Studio 확장으로 수행할 수 있는 항목의 유형은 있습니까?  
 하늘 다른 Visual Studio 확장을 생각해 보십시오에 있어 제한의입니다. 물론, 대부분의 확장 코드를 작성 하기 있지만 이것이 없는 합니다. 빌드할 수 확장의 종류의 몇 가지 예는 다음과 같습니다.  
  
-   구문 색 지정, IntelliSense, 컴파일러 및 디버그 지원와 Visual Studio에 포함 되지 않은 언어에 대 한 지원  
  
-   추가 서식 파일, 코드 리팩터링, 새 대화 상자 또는 도구 창에 대 한 핵심 확장 생산성 도구 IDE 경험  
  
-   데이터 디자인 또는 클라우드 지원 같은 시나리오를 위해 도메인 관련 디자이너  
  
 체크 아웃 확장의 예는 [Visual Studio 갤러리](https://visualstudiogallery.msdn.microsoft.com/)합니다. 살펴보기 지나야 [Visual Studio 오픈 소스 확장](https://github.com/Microsoft/extendvs/blob/master/CommunityExtensions.md)합니다.  
  
## Visual Studio 기능을 확장할 수 있습니까?  
 이론적으로 Visual Studio의 거의 모든 부분을 확장할 수 있습니다: 메뉴, 도구 모음, 명령, windows, 솔루션, 프로젝트, 편집자 및 등입니다.  
  
 실제로 대부분의 사람들이 확장 기능 명령, 메뉴 및 도구 모음, windows, IntelliSense 및 프로젝트는 발견 했습니다. 관련 섹션에 대 한 링크는 다음과 같습니다.  
  
-   [확장 메뉴 및 명령](../extensibility/extending-menus-and-commands.md): Visual Studio 메뉴 및 도구 모음에 직접 항목을 추가 합니다. 새로운 Visual Studio 기능 나 외부 도우미 응용 프로그램을 시작 하려면 사용할 수 있습니다. 메뉴 항목에 대 한 사용자 지정 바로 가기 키를 제공할 수도 있습니다.  
  
-   [확장 및 도구 창을 사용자 지정](../extensibility/extending-and-customizing-tool-windows.md): 기존의 도구 창을 확장 하거나 사용자 고유의 도구 창을 만들 수 있습니다. 예를 들어, 새 속성을 추가할 수 있습니다는 **속성**, 추가 기능을 추가 하는 새 도구 창을 만들 수 있습니다.  
  
-   [편집기와 언어 서비스 확장](../extensibility/editor-and-language-service-extensions.md): Visual Studio 언어에 대해 제공 되는 IntelliSense 고유의 사용자 지정을 추가 하거나 새 프로그래밍 언어에 대 한 지원을 만듭니다. 새 문 완성, 제안 및 새 나타나도록을 만들 수 있습니다. 전구를 리팩터링 추천 단어를 추가할 수와 새 프로그래밍 언어를 지원 하기 위해 코드를 수정 합니다.  
  
-   [프로젝트 확장](../extensibility/extending-projects.md)  
  
-   [확장 사용자 설정 및 옵션](../extensibility/extending-user-settings-and-options.md)  
  
-   [속성 및 속성 창 확장](../extensibility/extending-properties-and-the-property-window.md)  
  
-   [Visual Studio의 다른 부분을 확장합니다.](../extensibility/extending-other-parts-of-visual-studio.md)  
  
-   [Visual Studio Shell 격리](../extensibility/visual-studio-isolated-shell.md)  
  
##  <a name="BKMK_ProjectTemplate"></a> 프로젝트 템플릿 되는 VSSDK에서 제공 합니다.  
 확장의 두 가지 주요 유형은 VSPackages 및 MEF 확장입니다. 일반적으로 VSPackage 확장은 사용 하거나 명령, 도구 창 및 프로젝트를 확장 하는 확장에 사용 됩니다. MEF 확장은 확장 하거나 Visual Studio 편집기 사용자 지정 하는 데 사용 됩니다.  
  
 Visual C\# 및 Visual Basic 확장에 대 한는 VSSDK 메뉴 명령, 도구 창 및 편집기 확장을 만드는 새 항목 템플릿 함께 사용할 수 있는 빈 VSIX 프로젝트 템플릿을 제공 합니다. 자세한 내용은 [Visual Studio 2015 SDK의 새로운 기능](../extensibility/what-s-new-in-the-visual-studio-2015-sdk.md)을 참조하세요. 또한 다른 사용자에 게 배포에 대 한이 서식 파일을 패키지 프로젝트 템플릿, 코드 조각 및 기타 아티팩트를 사용할 수 있습니다.  
  
 C \+ \+에서 VSPackage 마법사는 메뉴 명령, 도구 창 및 사용자 지정 편집기를 추가 하는 코드를 제공 합니다.  
  
 격리 된 셸 템플릿 브랜드 및 사용자 고유의으로 배포할 수 있는 Visual Studio shell의 버전의 확장 프로그램을 패키지 하는 데 사용 됩니다. 다음 항목은 각 종류의 확장을 시작 하는 방법을 보여 줍니다.  
  
-   메뉴 명령: [메뉴 명령을 사용 하 여 확장 만들기](../extensibility/creating-an-extension-with-a-menu-command.md)  
  
-   도구 창: [확장 도구 창 만들기](../extensibility/creating-an-extension-with-a-tool-window.md)  
  
-   편집기 확장 합니다. [편집기 항목 템플릿을 사용 하 여 확장 만들기](../extensibility/creating-an-extension-with-an-editor-item-template.md)  
  
-   Vspackage 기본: [VSPackage를 사용 하 여 확장 만들기](../extensibility/creating-an-extension-with-a-vspackage.md)  
  
-   VSIX 프로젝트 템플릿: [VSIX 프로젝트 템플릿을 사용 하 여 시작 하기](../extensibility/getting-started-with-the-vsix-project-template.md)  
  
-   Visual Studio shell을 격리 합니다. [연습: 기본 격리 된 셸 응용 프로그램 만들기](../extensibility/walkthrough-creating-a-basic-isolated-shell-application.md)  
  
## Visual Studio 처럼 my 확장 가져오기  
 확장에 대 한 UI를 디자인 하기 위한 유용한 팁을 확인 [Visual Studio 사용자 환경 지침](../extensibility/ux-guidelines/visual-studio-user-experience-guidelines.md)합니다.  
  
## VSSDK 코드 예제는 어디서 찾을 수 있습니까?  
 이전 섹션에 나열 된 링크는 특정 기능을 구현 하는 방법을 보여 주는 단계별 연습을 모두 있습니다. 찾을 수도 있습니다 오픈 소스에서 GitHub의 VSSDK 샘플 [Visual Studio 샘플](https://aka.ms/vs2015sdksamples)합니다.  
  
## My 확장을 배포할 수는 방법  
 다른 컴퓨터에 확장을 설치 하거나.vsix 파일을 두 번 클릭 하 여 설치 파일로 친구에 보낼 수 있습니다. VSIX 패키지에 대 한 자세한 내용을 확인할 수 [배송 Visual Studio 확장](../extensibility/shipping-visual-studio-extensions.md)합니다.  
  
 또한 많은 수의 Visual Studio 고객에 게 표시 하는 Visual Studio 갤러리에서 확장 프로그램을 게시할 수 있습니다. 갤러리에 대 한 확장 패키지의 예제를 참조 하십시오. [연습: Visual Studio 확장 게시](../extensibility/walkthrough-publishing-a-visual-studio-extension.md)합니다. 갤러리에 게시 하기 위해 수행 해야 하는 방법에 대 한 자세한 내용은 참조 [제품 및 Visual Studio 확장](https://visualstudiogallery.msdn.microsoft.com/)합니다.