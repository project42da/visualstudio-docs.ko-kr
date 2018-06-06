---
title: 프로젝트와 파일에 대한 Visual Studio 템플릿
ms.date: 01/02/2018
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.topic: conceptual
helpviewer_keywords:
- templates [Visual Studio], project
- templates [Visual Studio], item
- item templates [Visual Studio]
- project templates [Visual Studio]
author: gewarren
ms.author: gewarren
manager: douge
ms.openlocfilehash: 62e51a5a03011874acc723eaf159e3f7130d1340
ms.sourcegitcommit: 0aafcfa08ef74f162af2e5079be77061d7885cac
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/01/2018
ms.locfileid: "34573260"
---
# <a name="project-and-item-templates"></a>프로젝트 및 항목 템플릿

프로젝트 및 항목 템플릿은 사용자 용도에 맞게 사용자 지정할 수 있는 구조체와 일부 기본 코드를 제공하는 재사용 가능한 스텁을 제공합니다.

## <a name="visual-studio-templates"></a>Visual Studio 템플릿

미리 정의된 많은 프로젝트 템플릿과 항목 템플릿이 Visual Studio와 함께 설치됩니다. 예를 들어 **새 프로젝트** 대화 상자에 표시되는 Visual Basic 및 C# **Windows Forms 앱** 및 **클래스 라이브러리** 템플릿은 프로젝트 템플릿입니다. 항목 템플릿은 **새 항목 추가** 대화 상자에 표시되며 코드 파일, XML 파일, HTML 페이지 및 스타일 시트와 같은 항목을 포함합니다.

이러한 템플릿은 사용자에게 프로젝트를 만들거나 기존 프로젝트를 확장하기 위한 시작 지점을 제공합니다. 프로젝트 템플릿은 특정 프로젝트 형식에 필요한 파일을 제공하고 표준 어셈블리 참조를 포함하며 기본 프로젝트 속성과 컴파일러 옵션을 설정합니다. 정확한 파일 확장명이 있는 하나의 빈 파일에서부터 스텁 코드가 있는 여러 소스 코드 파일, 디자이너 정보 파일 및 포함 리소스에 이르기까지 항목 템플릿의 범위는 다양합니다.

**새 프로젝트** 및 **새 항목 추가** 대화 상자에 있는 설치된 템플릿 외에도 직접 템플릿을 작성하거나 커뮤니티에서 만든 템플릿을 다운로드하여 사용할 수 있습니다. 자세한 내용은 [방법: 프로젝트 템플릿 만들기](../ide/how-to-create-project-templates.md) 및 [방법: 항목 템플릿 만들기](../ide/how-to-create-item-templates.md)를 참조하세요.

## <a name="contents-of-a-template"></a>템플릿의 내용

모든 프로젝트 템플릿과 항목 템플릿은 Visual Studio와 함께 설치되었는지 직접 만들었는지에 상관없이 동일한 원칙으로 작동하며 비슷한 내용으로 구성됩니다. 모든 템플릿에는 다음과 같은 항목이 포함됩니다.

- 템플릿이 사용될 때 만들어지는 파일입니다. 이러한 파일에는 소스 코드 파일, 포함 리소스, 프로젝트 파일 등이 있습니다.

- 메타데이터를 포함한 하나의 *.vstemplate* 파일은 **새 프로젝트** 및 **새 항목 추가** 대화 상자에 템플릿을 표시하고 템플릿에서 프로젝트 또는 항목을 만들 필요가 있습니다. *.vstemplate* 파일에 대한 자세한 내용은 [템플릿 매개 변수](../ide/template-parameters.md)를 참조하세요.

이러한 파일이 *.zip* 파일로 압축되어 올바른 폴더에 배치되면 Visual Studio에서는 다음 위치에 이를 자동으로 표시합니다.

- 프로젝트 템플릿은 **새 프로젝트** 대화 상자에 표시됩니다.

- 항목 템플릿은 **새 항목 추가** 대화 상자에 표시됩니다.

템플릿 폴더에 대한 자세한 내용은 [방법: 템플릿 찾기 및 구성](../ide/how-to-locate-and-organize-project-and-item-templates.md)을 참조하세요.

## <a name="see-also"></a>참고 항목

- [방법: 프로젝트 템플릿 만들기](../ide/how-to-create-project-templates.md)
- [방법: 항목 템플릿 만들기](../ide/how-to-create-item-templates.md)
- [템플릿 매개 변수](../ide/template-parameters.md)
- [템플릿 사용자 지정](../ide/customizing-project-and-item-templates.md)
- [Visual Studio 템플릿의 NuGet 패키지](/nuget/visual-studio-extensibility/visual-studio-templates)