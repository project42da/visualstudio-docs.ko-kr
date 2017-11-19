---
title: "기능 &#39; Visual Studio 2015 SDK의 새로운 s | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: c64aac80-a411-463f-b7bd-8b7607a52ece
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: b8b1fa4647cd5b145d19e2264381b186394be814
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="what39s-new-in-the-visual-studio-2015-sdk"></a>기능 &#39;의 새로운 Visual Studio 2015 SDK
Visual Studio SDK는 Visual Studio 2015, Visual Studio 2015 업데이트 및 Visual Studio 2017에 대 한 다음과 같은 새로운 기능과 업데이트 된 기능에 있습니다.  
  
## <a name="vs-2015-sdk-update-1"></a>VS 2015 SDK 업데이트 1  
 업데이트 1 확장 색 테마 및 Visual Studio 이미지 서비스를 함께 사용할 수 있는 도구를 포함 합니다.  
  
 이러한 항목은 아래의 [VSSDK 유틸리티](../extensibility/internals/vssdk-utilities.md) 섹션:  
  
-   [색 테마 설정 도구](../extensibility/internals/color-theming-tools.md) 만들고 Visual Studio에 대 한 사용자 지정 색을 편집할 수 있습니다.  
  
-   [이미지 서비스 도구](../extensibility/internals/image-service-tools.md) Visual Studio 이미지 매니페스트 파일을 사용 하 여 작업할 수 있도록 합니다.  
  
## <a name="new-way-to-add-the-visual-studio-sdk-to-visual-studio"></a>Visual Studio에 Visual Studio SDK를 추가 하는 새로운 방법  
 Visual Studio 2015부터 Visual Studio SDK를 별도로 다운로드할 필요가 없습니다. 대신, 일반 설치 프로세스의 일부로 설치할 수 있습니다 또는 나중에 설치 하도록 선택할 수 있습니다. 열거나 VSIX 솔루션을 만들 때 Visual Studio Visual Studio 확장성 도구 설치를 요청 합니다. 자세한 내용은 참조 [Visual Studio SDK 설치](../extensibility/installing-the-visual-studio-sdk.md)합니다.  
  
## <a name="new-ways-of-creating-extensions"></a>새로운 확장을 만드는 방법  
 Visual Studio 2015 SDK 부터는 사용 중인 프로그래밍 언어에 따라 확장을 만들기 위한 다른 옵션 해야 합니다.  
  
### <a name="visual-c-and-visual-basic"></a>Visual C# 및 Visual Basic  
 C# 및 Visual Basic의 경우에 Vspackage, 메뉴 명령, 도구 창, 편집기 분류자, 편집기 장식 및 편집기 여백 확장을 만들 수 있도록 하는 프로젝트 항목 템플릿의 전체 범위. 표준 VSIX 프로젝트에 이러한 중 일부 또는 모두를 추가할 수 있습니다. 자세한 내용은 다음을 참조하세요.  
  
-   [메뉴 명령을 사용하여 확장 만들기](../extensibility/creating-an-extension-with-a-menu-command.md)  
  
-   [도구 창으로 확장 만들기](../extensibility/creating-an-extension-with-a-tool-window.md)  
  
-   [편집기 항목 템플릿을 사용하여 확장 만들기](../extensibility/creating-an-extension-with-an-editor-item-template.md)  
  
-   [로 확장 만들기](../extensibility/creating-an-extension-with-a-vspackage.md)  
  
     VSPackage 마법사는 더 이상 C# 또는 Visual Basic에서 확장을 만듭니다.  
  
### <a name="c"></a>C++  
 C + +에서 VSPackage 마법사 메뉴 명령, 도구 창 및 사용자 지정 편집기를 지원 합니다. 찾도록는 **새 프로젝트** 대화 상자에 **Visual c + + / 확장성**합니다.  
  
## <a name="vs-sdk-reference-assemblies-via-nuget"></a>NuGet 통해 VS SDK 참조 어셈블리  
 향상 된 이식성 및 확장성 프로젝트의 공유에 대 한 NuGet 버전의 VS SDK 참조 어셈블리를 사용할 수 있습니다.  다운로드할 수 [nuget.org](http://www.nuget.org) 공개한 [VisualStudioExtensibility](http://www.nuget.org/profiles/VisualStudioExtensibility) 프로젝트 또는 Visual Studio를 통해 솔루션에 쉽게 추가할 수 있습니다 및 **참조 / 관리 NuGet 패키지** 대화 상자. 특정 확장 어셈블리에 대 한 개별 참조를 추가 하거나 한 번에 VS SDK를 사용 하 여 어셈블리를 참조 하는 모든 VS SDK를 추가할 수 있습니다 [메타 패키지](http://www.nuget.org/packages/VSSDK_Reference_Assemblies)합니다. NuGet에 대 한 자세한 내용은 참조는 [NuGet 설명서](http://docs.microsoft.com/NuGet) 및 [패키지 관리자 UI](http://docs.microsoft.com/NuGet/Tools/Package-Manager-UI) 항목입니다.  
  
 NuGet 버전의 VS SDK 참조 어셈블리를 사용 하면 다른 사용자를 열고 프로젝트를 빌드해야 VS SDK를 설치할 필요가 없습니다.  NuGet 참조 어셈블리 및 VS SDK 빌드 도구는 해당 프로젝트에 대 한 컴퓨터에 자동으로 설치 됩니다.  
  
 VS SDK 항목 템플릿 NuGet을 사용 하 여 해당 참조에 대해 및 기본적으로 NuGet의 이점을 얻을 수 있도록 빌드 도구를 사용 합니다.  
  
> [!NOTE]
>  계속 프로젝트와 함께 설치 하는 VS SDK 참조 어셈블리를 사용할 수 있습니다 (아래에 있는 \<Visual Studio 설치 위치 > \ \ VSSDK\VisualStudioIntegration\Common\Assemblies) 되도록 기존 확장성 프로젝트 필요가 없습니다 NuGet 패키지를 사용 하도록 업그레이드 됩니다.  프로젝트 **참조 / 참조 추가** 대화가 계속 VS SDK가 설치 되어 참조 어셈블리를 사용 합니다.  
>   
>  NuGet을 사용 하 여 참조 하십시오. 기존 프로젝트를 수정 하려는 경우 [하는 방법: Visual Studio 2015로 마이그레이션 Vspackage](../extensibility/how-to-migrate-extensibility-projects-to-visual-studio-2015.md) NuGet 패키지에 확장성 프로젝트를 업데이트 하는 방법에 대 한 섹션에 있는 합니다.  
  
## <a name="light-bulbs"></a>전구  
 확장 코드 작성의 가장 흥미로운 새로운 방법 중 하나는 Roslyn 프로젝트에서 제공 됩니다. 자세한 내용은 참조 [Roslyn](https://github.com/dotnet/Roslyn)합니다.  
  
 전구는 VSSDK와 함께 제공 하는 새로운 기능입니다. 이들은 기본 제공 코드 분석기에서 발견 된 문제에 대 한 수정 또는 리팩터링 코드 동작의 집합을 표시 하도록 확장 되는 Visual Studio 편집기에서 사용 되는 아이콘입니다. 자세한 내용은 참조 [연습: 전구 제안을 표시](../extensibility/walkthrough-displaying-light-bulb-suggestions.md)합니다.  
  
## <a name="updated-user-experience-guidelines"></a>업데이트 된 사용자 환경 지침  
 Visual Studio에 대 한 새로운 확장 또는 기능을 디자인? 업데이트 및 확장 체크 아웃 [Visual Studio 사용자 환경 지침](../extensibility/ux-guidelines/visual-studio-user-experience-guidelines.md)합니다.  찾을 수 있습니다는 [토큰 색](../extensibility/ux-guidelines/shared-colors-for-visual-studio.md), [글꼴 크기](../extensibility/ux-guidelines/fonts-and-formatting-for-visual-studio.md), [대화 상자 레이아웃 사양](../extensibility/ux-guidelines/layout-for-visual-studio.md), 및 Visual Studio와 완벽 하 게 새 UI를 통합 하는 데 필요한 다른 지침.