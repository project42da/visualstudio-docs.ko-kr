---
title: ".NET 개발자용 Visual Studio 2017 | Microsoft Docs"
description: "더 나은.NET 코드를 더 빠르게 작성할 수 있도록 Visual Studio 2017 기능의 개요를 제공합니다."
author: kuhlenh
ms.author: kaseyu
manager: ghogen
ms.technology: vs-ide-general
ms.date: 01/16/2018
ms.topic: article
helpviewer_keywords:
- editor
ms.workload:
- dotnet
ms.openlocfilehash: f15239ed045185449735ec3b5e0bcdc514fa786d
ms.sourcegitcommit: 8cbe6b38b810529a6c364d0f1918e5c71dee2c68
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 02/28/2018
---
# <a name="visual-studio-2017-for-net-developers"></a>.NET 개발자용 Visual Studio 2017

## <a name="smart-code-editor"></a>스마트 코드 편집기

- [설명서: IntelliSense 사용](using-intellisense.md)
- [설명서: 스마트 편집기 기능](writing-code-in-the-code-and-text-editor.md)

Visual Studio는 .NET("Roslyn") 컴파일러를 통해 코드를 심층적으로 이해하여 구문 색 지정, 기능 코드 완성, 잘못 입력된 변수의 맞춤법 검사, 가져오지 않은 형식 확인, 개요, 구조 시각화 도우미 [CodeLens](find-code-changes-and-other-history-with-codelens.md), 호출 계층 구조, 마우스를 올려 놓을 수 있는 빠른 정보, 매개변수 도움말은 물론, 리팩터링, 빠른 작업 적용 및 코드 생성 도구 등의 스마트 편집 기능을 제공합니다.

![Visual Studio 스마트 코드 편집기](../ide/media/VSIDE_Productivity_SmartCodeEditor.png "VSIDE_Productivity_SmartCodeEditor")

## <a name="navigate-and-search-your-codebase"></a>코드베이스 탐색 및 검색

[설명서: 코드 탐색](navigating-code.md)

*전체로 이동* 바로 가기로 파일, 형식, 멤버 또는 기호 선언으로 이동하여 .NET 코드를 빠르게 탐색합니다(**Ctrl + T**). .NET 언어 전체에서 참조를 포함하여 코드에 기호 또는 리터럴에 대한 모든 참조를 찾습니다(**Shift+F12**). 기호 정의(**F12**) 또는 구현(**Ctrl + F12**)으로 바로 이동할 수 있도록 대상 탐색 명령을 사용합니다.

![전체로 이동 및 모든 참조 찾기](../ide/media/VSIDE_Productivity_Navigation.png "VSIDE_Productivity_Navigation")

## <a name="live-code-analysis-for-code-quality"></a>코드 품질에 대한 라이브 코드 분석

[설명서: 리팩터링 및 빠른 작업](refactoring-code-generation-quick-actions.md)

Visual Studio에는 라이브 코드 진단 기능이 있어 오류와 잠재적인 문제 코드를 감지하여 코드 품질을 개선하는 데 도움이 됩니다. 빠른 작업(**Ctrl**+**.**)을 제공하여 문서, 프로젝트 또는 솔루션 전반에서 감지된 문제를 해결할 수 있습니다. *전체 솔루션 분석*을 활성화하여 편집기에서 해당 파일이 열려 있지 않은 경우에도 솔루션 전체에서 문제를 찾을 수 있습니다.

또한 코드 제안을 사용하여 모범 사례를 배우고 코드를 스텁 또는 생성하고 코드를 리팩터링하며 **Ctrl**+**.** 바로 가기로 새로운 언어 기능을 제공합니다. 스타일 문제를 해결하기 위한 빠른 해결을 제공합니다.

![전구 메뉴를 사용하여 빠른 해결 및 리팩터링 적용](../ide/media/VSIDE_Productivity_CodeAnalysis.png "VSIDE_Productivity_CodeAnalysis")

## <a name="unit-testing"></a>유닛 테스트

[설명서: Visual Studio에서 유닛 테스트](../test/improve-code-quality.md)

.NET Framework, .NET Standard 또는 .NET Core를 타게팅하는 응용 프로그램에 대해 MSTest, NUnit 또는 XUnit 테스팅 프레임워크에 기반하여 단위 테스트를 실행하고 디버깅합니다. *테스트 탐색기*에서 테스트를 탐색하고 검토하거나 *실시간 유닛 테스트*(Enterprise SKU만 해당)으로 편집기 내부에서 코드 변화가 단위 테스트에 어떻게 영향을 미치는지 즉시 확인합니다.

![Visual Studio의 실시간 유닛 테스트](../ide/media/VSIDE_Productivity_LiveUnitTesting.png "VSIDE_Productivity_LiveUnitTesting")

## <a name="code-consistency-and-style"></a>코드 일관성 및 스타일

- [설명서: 휴대용 사용자 지정 편집기 옵션](create-portable-custom-editor-options.md)
- [설명서: .NET에 대한 EditorConfig 코드 스타일 설정](editorconfig-code-style-settings-reference.md)

Visual Studio에서는 코딩 규칙 구성을 지원하고 코딩 스타일 위반을 감지하며 **Ctrl**+**.** 바로 가기를 사용하여 스타일 문제를 해결하기 위한 빠른 해결을 제공합니다. *EditorConfig*를 사용하여 프로젝트 및 파일 수준에서 값 재지정을 허용하여 리포지토리 전반에서 팀의 서식 지정, 명명 및 코드 스타일 규칙을 구성하고 강제 적용합니다.

![EditorConfig를 사용하여 코딩 규칙 구성 및 강제 적용](../ide/media/VSIDE_Productivity_CodeStyle.png "VSIDE_Productivity_CodeStyle")

## <a name="debugging"></a>디버깅

[설명서: Visual Studio의 디버깅](../debugger/index.md)

Visual Studio에는 .NET Framework, .NET Standard 및 .NET Core를 대상으로 하는 .NET 애플리케이션을 디버깅할 수 있는 최고의 디버거입니다. *편집 및 계속*으로 디버깅하면서 조건부 중단점을 전환 및 설정(**F9**)하고 메서드 호출을 실행하며 LINQ 및 람다 식을 평가하고 가변 워치를 설정하고 프로세스에 다시 연결하며 콜 스택을 조사하거나 실시간 코드 편집을 수행합니다.

Azure에서 서비스를 실행하는 경우 *스냅숏 디버깅*을 사용하여 Visual Studio 2017 Enterprise에서 배포된 라이브 클라우드 응용 프로그램에 대한 문제를 진단할 수 있습니다.

![Visual Studio의 디버깅](../ide/media/VSIDE_Productivity_Debugging.png "VSIDE_Productivity_Debugging")

## <a name="version-control"></a>버전 제어

[설명서: Visual Studio의 버전 제어](/vsts/index)

git 또는 TFVC를 사용하여 Visual Studio에서 코드를 저장하고 업데이트합니다. 편집기 내부에서 팀 탐색기로 로컬 변경 사항을 정리하고 상태 표시줄로 보류 중인 커밋과 변경 사항을 추적합니다. [Visual Studio용 지속적인 업데이트 도구](https://marketplace.visualstudio.com/items?itemName=VSIDEDevOpsMSFT.ContinuousDeliveryToolsforVisualStudio) 확장으로 Visual Studio 내부에 지속적인 통합 및 전달을 설정하여 민첩한 개발자 워크플로를 채택합니다.

![Visual Studio에서 소스 제어](../ide/media/VSIDE_Productivity_SourceControl.png "VSIDE_Productivity_SourceControl")

## <a name="extensibility"></a>확장성

[설명서: Visual Studio 확장](../extensibility/index.md)

Visual Studio에는 필요에 따라 설치하거나 만들 수 있는 확장의 풍부한 에코시스템이 있습니다. *확장 갤러리* 또는 *Visual Studio Marketplace*에서 확장을 설치하고 *VS SDK*로 자체 편집기 플러그인을 빌드하거나 *.NET 컴파일러 플랫폼 SDK*를 사용하여 자체 라이브 코드 분석기 또는 리팩터링을 만듭니다. [Microsoft 코드 분석](https://marketplace.visualstudio.com/items?itemName=VisualStudioPlatformTeam.MicrosoftCodeAnalysis2017) 확장을 다운로드하여 추가 코드 수정 및 제안 사항을 찾을 수 있습니다.

![Visual Studio 확장 갤러리](../ide/media/VSIDE_Productivity_Extensibility.png "VSIDE_Productivity_Extensibility")

## <a name="popular-extensions--shortcuts"></a>자주 사용되는 확장 기능 및 바로 가기

다른 IDE 또는 코딩 환경에서 왔다면 다음 확장 중 하나를 설치하면 유용할 수 있습니다.

- [Emacs 에뮬레이션](https://marketplace.visualstudio.com/items?itemName=JustinClareburtMSFT.EmacsEmulation )
- [Visual Studio용 바로 가기 키(ReSharper/IntelliJ)](https://marketplace.visualstudio.com/items?itemName=JustinClareburtMSFT.HotKeys)
- [VSVim](https://marketplace.visualstudio.com/items?itemName=JaredParMSFT.VsVim)

다음은 많이 사용되는 Visual Studio 바로 가기입니다. 일부 확장은 기본 Visual Studio 키 바인딩을 해제하며 아래 명령을 사용하려면 키 바인딩을 복원해야 합니다. Visual Studio의 기본값으로 키 바인딩을 복원하려면 **도구 > 설정 가져오기 및 내보내기... > 모든 설정 다시 설정**으로 이동합니다.

| 바로 가기(모든 프로필) | 명령 | 설명 |
|-|-|-|
| **Ctrl+T** | 전체로 이동 | 모든 파일/유형/멤버/기호 선언으로 이동 |
| **F12**(또느ㅡㄴ **Ctrl + 클릭**) | 정의로 이동 | 기호가 정의된 위치로 이동 |
| **Ctrl+F12** | 구현으로 이동 | 모든 베이스 형식 또는 멤버에서 다양한 구현으로 이동 |
| **Shift+F12** | 모든 참조 찾기 | 모든 기호 또는 리터럴 참조 보기 |
| **Ctrl**+**.** (또는 C# 프로필에서 **Alt+Enter**) | 빠른 작업 및 리팩터링 | 커서 위치 또는 코드 선택에서 사용 가능한 코드 해결, 코드 생성 작업, 리팩터링, 또는 기타 빠른 작업 확인 |
| **Ctrl**+**E**,**V** | 중복된 줄 | 커서가 있는 코드 줄 복제(**Visual Studio 2017 버전 15.6 미리 보기 2** 이상에서 사용 가능) |
| **Ctrl+Q** | 빠른 실행 | 모든 Visual Studio 설정 검색 |
| **F5** | 디버깅 시작 | 응용 프로그램 디버깅 시작 |
| **Ctrl+F5** | 디버깅하지 않고 실행 | 디버깅하지 않고 응용 프로그램을 로컬에서 실행 |
| **Ctrl + K,D**(기본 프로필) 또는 **Ctrl + E,D**(C# 프로필) | 문서 서식 | 줄 바꿈, 간격 및 들여쓰기 설정에 따라 파일에서 서식 위반 정리 |
| **Ctrl+\\,E**(기본 프로필) 또는 **Ctrl+W,E**(C# 프로필) | 오류 목록 보기 | 문서, 프로젝트 또는 솔루션의 모든 오류 보기 |