---
title: "Visual Studio의 솔루션 및 프로젝트 | Microsoft 문서"
ms.custom: 
ms.date: 10/5/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-general
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.addnewsolutionitem
- vs.environment.projects
- vs.openproject
- vs.addnewitem
- vs.addexistingitem
- VS.SolutionExplorer
- vs.newproject
- vs.addexistingsolutionitem
- vs.environment.solutions
- VS.SolutionExplorer.Solutions
helpviewer_keywords:
- solution items, folder in Solution Explorer
- solution items, shared
- solutions [Visual Studio]
- project items [Visual Studio], about project items
- solutions [Visual Studio], designing
- projects [Visual Studio]
- solutions [Visual Studio], projects and
- projects [Visual Studio], setting up
ms.assetid: aeaf56cb-c2dd-47f6-b012-23b84b7a7254
caps.latest.revision: "35"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: ca3094b3bfe35381236798164fa18e58304bae3f
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="solutions-and-projects-in-visual-studio"></a>Visual Studio의 솔루션 및 프로젝트
Visual Studio에서 앱, 웹 사이트, 플러그인 등을 만들 때 *프로젝트*를 시작합니다. 논리적인 측면에서 프로젝트에는 모든 소스 코드 파일, 아이콘, 이미지, 데이터 파일 및 실행 가능한 프로그램 또는 웹 사이트로 컴파일되는 기타 모든 항목이 포함되어 있거나 컴파일을 수행하는 데 필요한 기타 항목이 포함되어 있습니다. 프로젝트에도 프로그램이 통신하는 여러 서비스 또는 구성 요소에 필요할 수 있는 모든 컴파일러 설정 및 기타 구성 파일이 포함되어 있습니다.  

> [!NOTE]
>  원하지 않는 경우 솔루션이나 프로젝트를 사용하지 않아도 됩니다. Visual Studio에서 파일을 열고 코드 편집을 시작하면 됩니다. 자세한 내용은 [프로젝트 또는 솔루션 없이 Visual Studio에서 코드 개발](../ide/develop-code-in-visual-studio-without-projects-or-solutions.md)을 참조하세요.  

프로젝트 파일(.vbproj, .csproj, .vcxproj)은 프로젝트의 모든 항목에 대한 경로와 함께 가상 폴더 계층을 정의하는 XML 파일이며 빌드 설정을 포함합니다. 프로젝트 파일의 콘텐츠를 보려면 솔루션 탐색기에서 프로젝트 이름을 선택한 다음 상황에 맞는 메뉴에서 **프로젝트 언로드** 단추를 선택할 수 있습니다. 그런 다음 상황에 맞는 메뉴를 다시 열고 **\<projectname\> 편집**을 선택합니다.  

Visual Studio에서 프로젝트 파일은 솔루션 탐색기에서 프로젝트 내용 및 설정을 표시하는 데 사용됩니다. 프로젝트를 컴파일할 때 MSBuild 엔진은 프로젝트 파일을 사용하여 실행 파일을 만듭니다. 또한 다른 종류의 출력을 생성하는 프로젝트를 사용자 지정할 수 있습니다.  

프로젝트는 논리적인 의미와 파일 시스템에서 *솔루션* 내에 포함되어 있습니다. 이 솔루션에는 빌드 정보, Visual Studio 창 설정 및 특정 프로젝트와 관련이 없는 기타 파일과 함께 하나 이상의 관련된 프로젝트가 있을 수 있습니다. 솔루션은 고유한 형식을 가진 텍스트 파일(.sln)으로 설명되고 일반적으로 직접 편집할 수 없습니다.  

솔루션에는 프로젝트에 참여한 각 사용자에 대한 설정, 기본 설정 및 구성 정보를 저장하는 연결된 *.suo* 파일이 있습니다.  

 다음 다이어그램은 프로젝트와 솔루션 및 프로젝트와 솔루션에 논리적으로 포함된 항목 간의 관계를 보여줍니다.  

 ![Visual Studio 프로젝트 및 솔루션](../ide/media/vside-project-diagram.png)  

## <a name="creating-new-projects"></a>새 프로젝트 만들기  
 새 프로젝트를 만드는 가장 쉬운 방법은 프로젝트 템플릿으로 시작하는 것입니다. 이 템플릿은 특정 프로그래밍 언어로 특정 유형의 응용 프로그램이나 웹 사이트를 만들기 시작하는 미리 생성된 코드 파일, 구성 파일, 자산 및 설정이라는 기본 집합으로 구성되어 있습니다. 이러한 템플릿은 **파일**, **새로 만들기**, **프로젝트** 또는 **파일**, **새로 만들기**, **웹 사이트**를 선택하면 표시되는 **새 프로젝트** 또는 **새 웹 사이트** 대화 상자에서 확인할 수 있습니다. 자세한 내용은 [솔루션 및 프로젝트 만들기](../ide/creating-solutions-and-projects.md)를 참조하세요.  

사용자 지정 프로젝트 및 항목 템플릿을 만들 수도 있습니다. 자세한 내용은 [프로젝트 템플릿 및 항목 템플릿 만들기](../ide/creating-project-and-item-templates.md)를 참조하세요.  

## <a name="managing-projects-in-solution-explorer"></a>솔루션 탐색기에서 프로젝트 관리  
 새 프로젝트를 만든 후에 **솔루션 탐색기** 를 사용하여 프로젝트와 솔루션 및 연결된 항목을 보고 관리합니다. 다음 그림은 두 프로젝트가 포함되어 있으며, C# 솔루션을 사용하는 솔루션 탐색기를 보여 줍니다.  

 ![솔루션 탐색기](../ide/media/vs2015_solution_explorer.png "vs2015_solution_explorer")  

## <a name="in-this-section"></a>단원 내용  

-   [솔루션 및 프로젝트 만들기](../ide/creating-solutions-and-projects.md)  

-   [프로젝트 항목 추가 및 제거](../ide/adding-and-removing-project-items.md)  

-   [프로젝트 및 솔루션 속성 관리](../ide/managing-project-and-solution-properties.md)  

-   [프로젝트의 참조 관리](../ide/managing-references-in-a-project.md)  

-   [응용 프로그램 속성](../ide/application-properties.md)  

-   [어셈블리 및 매니페스트 서명 관리](../ide/managing-assembly-and-manifest-signing.md)  

-   [방법: 응용 프로그램 아이콘 지정(Visual Basic, C#)](../ide/how-to-specify-an-application-icon-visual-basic-csharp.md)  

-   [특정 .NET Framework 버전 대상 지정](../ide/targeting-a-specific-dotnet-framework-version.md)  

-   [프로젝트 및 항목 템플릿 만들기](../ide/creating-project-and-item-templates.md)  

## <a name="see-also"></a>참고 항목  
 [Visual Studio IDE](../ide/visual-studio-ide.md)
