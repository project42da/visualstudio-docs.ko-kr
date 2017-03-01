---
title: "Visual Studio 2015 SDK의 새로운 기능 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c64aac80-a411-463f-b7bd-8b7607a52ece
caps.latest.revision: 13
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
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
translationtype: Machine Translation
ms.sourcegitcommit: 512014c5070e4314ad2b7d0e8c5c404c43f32cd9
ms.openlocfilehash: 8d77fce54b12b90f6a2632fd1c1741990be42a08
ms.lasthandoff: 02/22/2017

---
# <a name="what39s-new-in-the-visual-studio-2015-sdk"></a>Visual Studio 2015 SDK의 새로운 기능
Visual Studio SDK는 다음 기능이 새로 추가 되거나 업데이트 된 Visual Studio 2015, Visual Studio 2015 업데이트 및 Visual Studio 2017 합니다.  
  
## <a name="vs-2015-sdk-update-1"></a>VS 2015 SDK 업데이트 1  
 업데이트 1에는 색 테마 및 Visual Studio 이미지 서비스와 잘 작동 하는 확장 프로그램 유용한 도구를 포함 합니다.  
  
 이러한 항목은 아래에서 [VSSDK 유틸리티](../extensibility/internals/vssdk-utilities.md) 섹션:  
  
-   [색 테마 도구](../extensibility/internals/color-theming-tools.md) 만들고 Visual Studio에 대 한 사용자 지정 색을 편집 하는 데 도움이 됩니다.  
  
-   [이미지 서비스 도구](../extensibility/internals/image-service-tools.md) Visual Studio 이미지의 매니페스트 파일을 사용 하 여 작업할 수 있도록 합니다.  
  
## <a name="new-way-to-add-the-visual-studio-sdk-to-visual-studio"></a>Visual Studio에 Visual Studio SDK를 추가 하는 새로운 방법  
 Visual Studio 2015 년부터 Visual Studio SDK를 별도로 다운로드할 필요가 없습니다. 대신 일반 설치 프로세스의 일부로 설치할 수 있습니다 하거나 나중에 설치할 수 있습니다. VSIX 솔루션을 만들거나 열 때 Visual Studio를 묻습니다 Visual Studio 확장성 도구를 설치할 수 있습니다. 자세한 내용은 참조 [Visual Studio SDK 설치](../extensibility/installing-the-visual-studio-sdk.md)합니다.  
  
## <a name="new-ways-of-creating-extensions"></a>새로운 확장을 만드는 방법  
 사용 중인 프로그래밍 언어에 따라 확장을 만들기 위한 다른 옵션 Visual Studio 2015 SDK를 시작 해야 합니다.  
  
### <a name="visual-c-and-visual-basic"></a>Visual C# 및 Visual Basic  
 C# 및 Visual Basic의 경우 Vspackage, 메뉴 명령, 도구 창, 편집기 분류자, 편집기 장식 및 편집기 여백 확장을 만들 수 있도록 하는 프로젝트 항목 템플릿의 전체 범위의 있습니다. 일부 또는 모든 표준 VSIX 프로젝트에 추가할 수 있습니다. 자세한 내용은 다음을 참조하세요.  
  
-   [메뉴 명령을 사용 하 여 확장 만들기](../extensibility/creating-an-extension-with-a-menu-command.md)  
  
-   [확장 도구 창 만들기](../extensibility/creating-an-extension-with-a-tool-window.md)  
  
-   [편집기 항목 템플릿을 사용 하 여 확장 만들기](../extensibility/creating-an-extension-with-an-editor-item-template.md)  
  
-   [VSPackage를 사용 하 여 확장 만들기](../extensibility/creating-an-extension-with-a-vspackage.md)  
  
     VSPackage 마법사는 더 이상 C# 또는 Visual Basic에서 확장을 만듭니다.  
  
### <a name="c"></a>C++  
 C + +에서 VSPackage 마법사 메뉴 명령, 도구 창 및 사용자 지정 편집기를 지원 합니다. 찾으려는 **새 프로젝트** 대화 상자에서 **Visual c + + / 확장성**합니다.  
  
## <a name="vs-sdk-reference-assemblies-via-nuget"></a>NuGet 통해 VS SDK 참조 어셈블리  
 향상 된 휴대성과 확장 프로젝트 공유에 대 한 VS SDK 참조 어셈블리의 NuGet 버전을 사용할 수 있습니다.  다운로드할 수 [nuget.org](http://www.nuget.org) 공개한 [VisualStudioExtensibility](http://www.nuget.org/profiles/VisualStudioExtensibility) 프로젝트 또는 Visual Studio를 통해 솔루션에 쉽게 추가할 수 있습니다 **참조 / 관리 NuGet 패키지** 대화 합니다. 특정 확장 어셈블리에 대 한 개별 참조를 추가 하거나 한 번에 VS SDK를 사용 하 여 어셈블리를 참조 하는 모든 VS SDK를 추가할 수 [메타 패키지](http://www.nuget.org/packages/VSSDK_Reference_Assemblies)합니다. NuGet에 대 한 자세한 참조 [NuGet 개요](http://docs.nuget.org/) 및 [관리 NuGet 패키지를 사용 하 여 대화 상자](http://docs.nuget.org/Consume/Package-Manager-Dialog)합니다.  
  
 VS SDK 참조 어셈블리의 NuGet 버전을 사용 하면 다른 사용자를 열고 프로젝트를 빌드할 VS SDK를 설치할 필요가 없습니다.  NuGet 참조 어셈블리 및 VS SDK 빌드 도구는 해당 프로젝트에 대 한 컴퓨터에 자동으로 설치 됩니다.  
  
 VS SDK 항목 템플릿 NuGet을 사용 하 여 해당 참조에 대해 및 빌드 도구 기본적으로 NuGet의 이점을 활용할 수 있도록 합니다.  
  
> [!NOTE]
>  프로젝트와 함께 설치 되는 VS SDK 참조 어셈블리를 사용 하 여 계속할 수 있습니다 (아래에 있는 \<Visual Studio 설치 위치 > \ VSSDK\VisualStudioIntegration\Common\Assemblies) 기존 확장성 프로젝트 NuGet 패키지를 사용 하 여 업그레이드할 필요가 없습니다.  프로젝트 **참조 / 참조 추가** 대화 상자가 VS SDK가 설치 되어 참조 어셈블리를 사용 하 여 계속 합니다.  
>   
>  NuGet을 사용 하 여 참조를 기존 프로젝트를 수정 하려는 경우 [하는 방법: Visual Studio 2015를 마이그레이션 Vspackage](../extensibility/how-to-migrate-extensibility-projects-to-visual-studio-2015.md) 확장성 프로젝트에 NuGet 패키지 업데이트에 대 한 섹션이 있는 합니다.  
  
## <a name="light-bulbs"></a>전구  
 확장 코드를 작성 하는 가장 흥미로운 새로운 방법 중 하나는 Roslyn 프로젝트에 의해 제공 됩니다. 자세한 내용은 참조 [Roslyn](https://github.com/dotnet/Roslyn)합니다.  
  
 전구는는 VSSDK와 함께 제공 되는 새로운 기능입니다. 기본 제공 코드 분석기에 의해 식별 된 문제에 대 한 수정 또는 코드 리팩터링 작업 집합을 표시 하도록 확장 하는 Visual Studio 편집기에서 사용 되는 아이콘입니다. 자세한 내용은 참조 [연습: 전구 제안 표시](../extensibility/walkthrough-displaying-light-bulb-suggestions.md)합니다.  
  
## <a name="updated-user-experience-guidelines"></a>업데이트 된 사용자 환경 지침  
 Visual Studio에 대 한 새로운 확장 기능 또는 기능을 디자인? 업데이트 된와 확장 된 체크아웃 [Visual Studio 사용자 환경 지침](../extensibility/ux-guidelines/visual-studio-user-experience-guidelines.md)합니다.  찾을 수는 [토큰 색상](../extensibility/ux-guidelines/shared-colors-for-visual-studio.md), [글꼴 크기](../extensibility/ux-guidelines/fonts-and-formatting-for-visual-studio.md), [대화 상자 레이아웃 사양](../extensibility/ux-guidelines/layout-for-visual-studio.md), 및 Visual Studio와 새 UI를 원활 하 게 통합 하는 데 필요한 기타 지침입니다.
