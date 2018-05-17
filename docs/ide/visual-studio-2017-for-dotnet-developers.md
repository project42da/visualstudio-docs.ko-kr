---
title: .NET 개발자용 Visual Studio 2017
description: 더 나은.NET 코드를 더 빠르게 작성할 수 있도록 Visual Studio 2017 기능의 개요를 제공합니다.
author: kuhlenh
ms.author: kaseyu
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-ide-general
ms.date: 01/16/2018
ms.topic: conceptual
helpviewer_keywords:
- editor
ms.workload:
- dotnet
ms.openlocfilehash: bd517cd859f47f9b4cb41884bd116005aa31fa29
ms.sourcegitcommit: a8e01952be5a539104e2c599e9b8945322118055
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="visual-studio-2017-productivity-guide-for-net-developers"></a>.NET 개발자용 Visual Studio 2017 생산성 가이드

[Visual Studio 2017](https://www.visualstudio.com/downloads/)은 개발자를 어느 때 보다 더 생산적이게 합니다! 솔루션 시작 및 로드, 테스트 검색 및 입력 대기 시간을 위해 성능과 안정성을 개선했습니다. 또한 더 나은 코드를 더 빠르게 쓸 수 있도록 기능을 향상시키고 추가했습니다. 이러한 기능 중 일부는 디컴파일된 어셈블리에 대한 탐색, 입력 시 변수 이름 제안, **테스트 탐색기**에서 계층 구조 보기, 파일/유형/멤버/기호 선언 탐색하려면 전체로 이동(**Ctrl**+**T**), 지능형 **예외 도우미**, 코드 스타일 구성 및 적용, 많은 리팩터링 및 코드 수정을 포함합니다.

이 가이드를 따라 생산성을 최적화합니다.

##  <a name="im-used-to-my-keyboard-shortcuts-from-a-different-extensioneditoride"></a>다른 확장/편집기/IDE에서 내 바로 가기 키에 익숙합니다.

다른 IDE 또는 코딩 환경에서 왔다면 다음 확장 중 하나를 설치하면 유용할 수 있습니다.

- [Emacs 에뮬레이션](https://marketplace.visualstudio.com/items?itemName=JustinClareburtMSFT.EmacsEmulation)
- [Visual Studio용 바로 가기 키(ReSharper/IntelliJ)](https://marketplace.visualstudio.com/items?itemName=JustinClareburtMSFT.HotKeys)
- [VSVim](https://marketplace.visualstudio.com/items?itemName=JaredParMSFT.VsVim)

다음은 많이 사용되는 Visual Studio 바로 가기입니다.

| 바로 가기(모든 프로필) | 명령 | 설명 |
|-|-|-|
| **Ctrl**+**T** | 전체로 이동 | 모든 파일/유형/멤버/기호 선언으로 이동 |
| **F12**(또는 **Ctrl**+**클릭**) | 정의로 이동 | 기호가 정의된 위치로 이동 |
| **Ctrl**+**F12** | 구현으로 이동 | 모든 베이스 형식 또는 멤버에서 다양한 구현으로 이동 |
| **Shift**+**F12** | 모든 참조 찾기 | 모든 기호 또는 리터럴 참조 보기 |
| **Ctrl**+**.** (또는 C# 프로필에서 **Alt**+**Enter**) | 빠른 작업 및 리팩터링 | 커서 위치 또는 코드 선택에서 사용 가능한 코드 해결, 코드 생성 작업, 리팩터링, 또는 기타 빠른 작업 확인 |
| **Ctrl**+**D** | 중복된 줄 | 커서가 있는 코드 줄 복제(**Visual Studio 2017 버전 15.6** 이상에서 사용 가능) |
| **Shift**+**Alt**+**+**/**-** | 선택 영역을 확대/축소 | 편집기(**Visual Studio 2017 버전 15.5** 이상에서 사용 가능)에서 현재 선택 영역을 확장하거나 축소 |
| **Ctrl**+**Q** | 빠른 실행 | 모든 Visual Studio 설정 검색 |
| **F5** | 디버깅 시작 | 응용 프로그램 디버깅 시작 |
| **Ctrl**+**F5** | 디버깅하지 않고 실행 | 디버깅하지 않고 응용 프로그램을 로컬에서 실행 |
| **Ctrl**+**K**,**D**(기본 프로필) 또는 **Ctrl**+**E**,**D**(C# 프로필) | 문서 서식 | 줄 바꿈, 간격 및 들여쓰기 설정에 따라 파일에서 서식 위반 정리 |
| **Ctrl**+**\\**,**E**(기본 프로필) 또는 **Ctrl**+**W**,**E**(C# 프로필) | 오류 목록 보기 | 문서, 프로젝트 또는 솔루션의 모든 오류 보기 |

> [!NOTE]
> 기본 Visual Studio keybindings의 바인딩을 해제한 일부 확장 다음과 같은 명령을 사용하려면 **도구** > **설정 가져오기 및 내보내기** > **모든 설정 다시 설정** 또는 **도구** > **옵션** > **키보드** > **다시 설정**으로 이동하여 Visual Studio의 기본값으로 키 바인딩을 복원합니다.

## <a name="i-need-a-way-to-quickly-navigate-to-files-or-types"></a>파일 또는 형식을 빠르게 탐색하는 방법이 있어야 합니다.
Visual Studio 2017에 **전체로 이동**(**Ctrl**+**T**)이라는 기능이 있습니다. 전체로 이동은 사용자를 모든 파일, 형식, 멤버 또는 기호 선언으로 빠르게 이동하게 할 수 있습니다.
- 이 검색 표시줄의 위치를 변경하거나 **기어** 아이콘을 사용하여 '라이브 탐색 미리 보기'를 꺼둠
- 쿼리 구문(예: "t mytype")을 사용하여 결과를 필터링합니다. 또한 현재 문서만으로 검색 범위를 지정할 수 있습니다.
- camelCase 일치가 지원됩니다!

![Visual Studio에서 전체로 이동](../ide/media/VS2017Guide-go-to-all.png)

## <a name="my-team-enforces-code-style-rules-on-our-codebase"></a>팀은 코드 스타일 규칙을 코드베이스에 적용합니다.
*.editorconfig* 파일을 사용하여 코딩 규칙을 체계화하고 소스에서 이동하도록 할 수 있습니다.
- Visual Studio에서 *.editorconfig* 파일을 추가하고 편집하려면 [EditorConfig 언어 서비스 확장](https://aka.ms/editorconfig)을 설치하는 것이 좋습니다.
- 모든 .NET 코딩 규칙 옵션에 대해서는 [설명서](https://aka.ms/editorconfigDocs)를 확인하세요.
- 예제 *.editorconfig*에 대해서는 [이 요점](https://gist.github.com/kuhlenh/5471666a7a2c57fea427e81cf0a41da8)을 참조하세요.

![Visual Studio에서 코드 스타일 적용](../ide/media/VSGuide_CodeStyle.png)

## <a name="i-need-more-refactorings-and-code-fixes"></a>더 많은 리팩터링 및 코드 수정이 있어야 합니다.
Visual Studio 2017에는 많은 리팩터링, 코드 생성 작업 및 코드 수정이 제공됩니다. 빨간색 오류 표시선은 오류를 나타내며, 녹색 오류 표시선은 경고를 나타내고, 세 개의 회색 점은 코드 제안 사항을 나타냅니다. 전구/스크루드라이버 아이콘을 클릭하거나 **Ctrl**+**.** 또는 **Alt**+**Enter**를 눌러 코드 수정에 액세스할 수 있습니다. 각 수정 사항은 수정 작업 방식의 라이브 코드 diff를 보여주는 미리 보기 창이 함께 제공됩니다.

- 인기 있는 빠른 수정 및 리팩터링은 다음과 같습니다.
  - *이름 바꾸기*
  - *메서드 추출*
  - *메서드 시그니처 변경*
  - *생성자 생성*
  - *Generate 메서드*
  - *Move Type to File*(파일로 형식 이동)
  - *Add Null-Check*(Null 검사 추가)
  - 매개 변수 추가
  - 불필요한 Using 제거
  - 더 많은 내용은 [설명서](https://aka.ms/refactorings) 참조
- [Roslyn 분석기](https://github.com/dotnet/roslyn/wiki/Getting-Started-Writing-a-Custom-Analyzer-&-Code-Fix)를 사용하여 고유한 리팩터링 또는 코드 수정을 작성하세요.
- 여러 커뮤니티 회원이 다음과 같은 추가적인 코드 검사를 추가하는 ‘무료’ 확장을 작성했습니다.
  - [Roslynator](https://marketplace.visualstudio.com/items?itemName=josefpihrt.Roslynator2017)
  - [SonarLint for Visual Studio](https://marketplace.visualstudio.com/items?itemName=SonarSource.SonarLintforVisualStudio2017)
  - [StyleCopAnalyzers](https://www.nuget.org/packages/stylecop.analyzers/)

![Visual Studio에서 리팩터링](../ide/media/VSGuide_CodeAnalysis.png "VSGuide_CodeAnalysis")

## <a name="i-need-find-usages-go-to-implementation-navigate-to-decompiled-assemblies"></a>사용량 찾기, 구현으로 이동, 디컴파일된 어셈블리 탐색이 필요
Visual Studio 2017에는 코드베이스를 검색하고 탐색하는 데 도움이 되는 여러 가지 기능이 있습니다. [코드 탐색 기능](../ide/navigating-code.md)에 대해 자세히 알아보기

| 기능 | 바로 가기 | 세부 정보/개선 사항 |
|- | - | -|
| 모든 참조 찾기 | **Shift**+**F12**| 결과에는 색이 지정되며, 프로젝트, 정의 등으로 결과를 그룹화할 수 있습니다. 결과를 ‘잠글’ 수도 있습니다. |
| 구현으로 이동 | **Ctrl**+**F12** | `override` 키워드에서 [정의로 이동]을 사용하여 재정의된 멤버로 이동할 수 있습니다. |
| 정의로 이동 | **F12** 또는 **Ctrl**+**클릭**| 정의로 이동하려면 클릭하면서 **Ctrl**을 계속 누르고 있습니다. |
| 정의 피킹(Peeking) | **Alt**+**F12** | 정의의 인라인 보기 |
| 구조체 시각화 도우미 | 괄호 사이의 회색 점선 | 코드 구조를 보려면 가리키기 |
| 디컴파일된 어셈블리 탐색 | **F12** 또는 **Ctrl**+**클릭** | **도구** > **옵션** > **텍스트 편집기** > **C#** > **고급** > **Enable navigation to decompiled sources(디컴파일된 소스에 탐색을 사용하도록 설정)** 를 통해 기능을 사용하도록 설정하여 외부 소스(ILSpy로 디컴파일됨)를 탐색합니다. |

![전체로 이동 및 모든 참조 찾기](../ide/media/VSIDE_Productivity_Navigation.png)

## <a name="i-want-to-run-and-see-my-unit-tests"></a>단위 테스트를 실행하고 참조하려 합니다.
Visual Studio 2017의 테스트 환경이 많이 개선되었습니다. MSTest v1, MSTest v2, NUnit 또는 XUnit 테스트 프레임워크로 유닛 테스트 환경을 사용하세요.
- **‘테스트 탐색기’** 테스트 검색은 버전 15.6에서 빠릅니다(최상의 결과를 위해 테스트 어댑터를 최신 버전으로 업그레이드).
- 버전 15.6의 새 ‘계층 구조 정렬’을 사용하여 테스트 탐색기에서 테스트를 구성합니다.
- [Live Unit Testing](../test/live-unit-testing.md)은 계속 코드 변경으로 영향을 받는 테스트를 실행하며 테스트 상태를 알려주는 인라인 편집기 아이콘을 업데이트합니다. *Live Test Set*(라이브 테스트 집합)에서 특정 테스트 또는 테스트 프로젝트를 포함하거나 제외합니다.

![Visual Studio에서 텍스트 탐색기의 계층 구조 뷰](../ide/media/VSGuide_Testing.png)

## <a name="i-want-to-debug-my-code"></a>내 코드를 디버그하고 싶습니다.
Visual Studio 2017에는 새로운 디버깅 기능이 추가되었습니다.
- *Run to click*(실행하려면 클릭)을 사용하면 코드 줄 옆을 가리키고, 나타나는 녹색 ‘재생’ 아이콘을 누르고, 해당 줄에 도달할 때까지 프로그램을 실행할 수 있습니다.
- 새 **‘예외 도우미’** 는 어떤 변수가 NullReferenceException에서 ‘null’인지와 같은 가장 중요한 정보를 대화 상자의 최상위 수준에 놓습니다.
- [뒤로 이동](../debugger/how-to-use-intellitrace-step-back.md) 디버깅을 사용하면 이전 중단점 또는 단계로 돌아가서 과거의 응용 프로그램 상태를 볼 수 있습니다.
- [스냅숏 디버깅](/azure/application-insights/app-insights-snapshot-debugger)을 사용하면 예외가 throw되는 때에 라이브 웹 응용 프로그램의 상태를 확인할 수 있습니다(Azure에 있어야 함).

![VS2017의 새 예외 도우미](../ide/media/VSGuide_Debugging.png "VSGuide_Debugging")

## <a name="i-want-to-use-version-control-with-my-projects"></a>내 프로젝트에서 버전 제어를 사용하고 싶습니다.
git 또는 TFVC를 사용하여 Visual Studio에서 코드를 저장하고 업데이트할 수 있습니다.
- **‘팀 탐색기’** 로 로컬 변경 사항을 정리하고 상태 표시줄로 보류 중인 커밋과 변경 사항을 추적합니다.
- [Visual Studio용 지속적인 업데이트 도구](https://marketplace.visualstudio.com/items?itemName=VSIDEDevOpsMSFT.ContinuousDeliveryToolsforVisualStudio) 확장으로 Visual Studio 내부에 프로젝트에 대한 지속적인 통합 및 업데이트를 설정하고 민첩한 개발자 워크플로를 채택합니다.

![Visual Studio에서 소스 제어](../ide/media/VSIDE_Productivity_SourceControl.png)

## <a name="what-other-features-do-i-need-to-know-about"></a>알아야 할 다른 기능은 무엇인가요?
코드 작성을 보다 효율적으로 하기 위한 편집기 및 생산성 기능 목록입니다. 일부 기능은 기본적으로 활성화되어 있지 않으므로(이 기능은 컴퓨터에서 인덱싱할 수 있고 논쟁적이거나 실험적입니다) 사용하도록 설정해야 합니다.

| 기능 | 설명 | 사용 방법 |
|-|-|-|
| 솔루션 탐색기에서 파일 찾기 | 솔루션 탐색기에서 활성 파일 강조 표시 | **솔루션 탐색기의 도구** > **옵션** > **프로젝트 및 솔루션** > **활성 항목 추적** |
| 참조 어셈블리 및 NuGet 패키지의 형식에 대한 using 추가 | 참조되지 않은 형식의 NuGet 패키지를 설치하기 위해 코드 수정이 있는 전구 표시 | **도구** > **옵션** > **텍스트 편집기** > **C#** > **고급** > **참조 어셈블리의 형식에 대한 using 제안** 및 **NuGet 패키지의 형식에 대한 using 제안** |
| 전체 솔루션 분석 사용 | **오류 목록**에서 솔루션의 모든 오류 보기 | **도구** > **옵션** > **텍스트 편집기** > **C#** > **고급** > **전체 솔루션 분석 사용** |
| 디컴파일된 소스에 탐색을 사용하도록 설정 | 외부 소스에서 형식/멤버에 대한 정의로 이동하고, 메서드 본문을 표시하기 위해 ILSpy 디컴파일러를 사용할 수 있습니다. | **도구** > **옵션** > **텍스트 편집기** > **C#** > **고급** > **Enable navigation to decompiled sources(디컴파일된 소스에 탐색을 사용하도록 설정)** |
| 완료/제안 모드 | IntelliSense의 완료 동작 변경 -- IntelliJ 배경 개발자는 기본값에서 설정을 변경하는 경향이 있습니다. | **메뉴** > **편집** > **IntelliSense** > **완료 모드 설정/해제** |
| [CodeLens](../ide/find-code-changes-and-other-history-with-codelens.md) | 편집기에서 코드 참조 정보 및 변경 내용 표시 | **도구** > **옵션** > **텍스트 편집기** > **모든 언어** > **CodeLens** |
| [코드 조각](../ide/visual-csharp-code-snippets.md) | 일반 상용구를 없애는 도움말 |  코드 조각 이름을 입력하고 **탭** 키를 두 번 누릅니다. |

![Visual Studio의 코드 조각](../ide/media/VSGuide_SmartEditor.png)

## <a name="missing-a-feature-that-makes-you-productive-or-experiencing-poor-performance"></a>생산적으로 만드는 기능이 누락되거나 성능 저하를 경험합니까?
여러 가지 방법으로 피드백을 남길 수 있습니다.
- .NET 기능 요청은 [GitHub 리포지토리](https://github.com/dotnet/roslyn/issues)에 제출될 수 있습니다.
- Visual Studio 기능 요청, 버그 및 성능 문제는 Visual Studio 창의 오른쪽 상단에 있는 **사용자 의견 보내기** 아이콘을 사용하여 제출될 수 있습니다.