---
title: "테스트 탐색기 FAQ | Microsoft Docs"
ms.date: 1/15/2018
ms.reviewer: 
ms.suite: 
ms.technology: vs-devops-test
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Test Explorer
- Test window
- Visual Studio Test Explorer
- summary line
- unit tests
- Test Explorer FAQ
ms.author: kehavens
ms.workload:
- multiple
author: kendrahavens
manager: ghogen
ms.openlocfilehash: d06c02e651dd4acdcaebf05448282f26c20e3a75
ms.sourcegitcommit: 37c87118f6f41e832da96f21f6b4cc0cf8fee046
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/12/2018
---
# <a name="visual-studio-test-explorer-faq"></a>Visual Studio 테스트 탐색기 FAQ

## <a name="test-discovery"></a>테스트 검색

### <a name="1-the-test-explorer-is-not-discovering-my-tests-that-are-dynamically-defined-for-example-theories-custom-adapters-custom-traits-ifdefs-etc-how-can-i-discover-these-tests"></a>1. 텍스트 탐색기가 동적으로 정의된 나의 테스트를 검색하지 않습니다. (예: 이론, 사용자 지정 어댑터, 사용자 지정 특성, #ifdefs 등) 이러한 테스트를 검색하려면 어떻게 할까요?

  프로젝트를 빌드하고 **도구 > 옵션 > 테스트**에서 어셈블리 기반 검색이 켜져 있는지 확인합니다.

  [실시간 테스트 검색](https://go.microsoft.com/fwlink/?linkid=862824)은 소스 기반 테스트 검색입니다. 이론, 사용자 지정 어댑터, 사용자 지정 특성, `#ifdef` 문 등을 사용하는 테스트는 런타임에 정의되기 때문에 검색할 수 없습니다. 해당 테스트를 정확하게 검색하려면 빌드가 필요합니다. 15.6 미리 보기에서 어셈블리 기반 검색(기존 Discoverer)은 빌드 후에만 실행됩니다. 이 설정은 실시간 테스트 검색은 편집 중에 검색할 수 있는 만큼 테스트를 검색하고 어셈블리 기반 검색을 사용하면 동적으로 정의된 테스트가 빌드 후에 표시될 수 있음을 의미합니다. 실시간 테스트 검색은 응답성을 개선하지만 빌드 후에 완전하고 정확한 결과를 얻을 수 있습니다.

### <a name="2-what-does-the--plus-symbol-that-appears-in-the-top-line-of-test-explorer-mean"></a>2. 테스트 탐색기의 맨 위 줄에 표시되는 ‘+’(더하기) 기호는 무엇인가요?

  ‘+’(더하기) 기호는 어셈블리 기반 검색이 켜져 있는 한, 빌드 후에 추가 테스트가 검색될 수 있음을 나타냅니다. 이 기호는 동적으로 정의된 테스트가 프로젝트에서 검색되는 경우 표시됩니다.

  ![더하기 기호 요약 줄](media/testex-plussymbol.png)

### <a name="3-assembly-based-discovery-is-no-longer-working-for-my-project-how-do-i-turn-it-back-on"></a>3. 어셈블리 기반 검색이 프로젝트에서 더 이상 작동하지 않습니다. 다시 켜려면 어떻게 할까요?

  **도구 > 옵션 > 테스트**로 이동하여 **빌드 후 빌드된 어셈블리에서 테스트를 추가로 검색** 상자를 선택합니다.

  ![어셈블리 기반 옵션](media/testex-toolsoptions.png)

### <a name="4-tests-now-appear-in-test-explorer-while-i-type-without-having-to-build-my-project-what-changed"></a>4. 이제 프로젝트를 빌드할 필요 없이 입력하는 동안 테스트 탐색기에 테스트가 나타납니다. 변경된 내용은 무엇인가요?

  이 기능을 [실시간 테스트 검색](https://go.microsoft.com/fwlink/?linkid=862824)이라고 합니다. 프로젝트를 빌드하지 않아도 Roslyn 분석기를 사용하여 실시간으로 테스트를 검색하고 테스트 탐색기를 채웁니다. 이론 또는 사용자 지정 특성과 같은 동적으로 정의된 테스트의 테스트 검색 동작에 대한 자세한 정보는 FAQ #1을 참조하세요.

### <a name="5-what-languages-and-test-frameworks-can-use-real-time-test-discovery"></a>5. 실시간 테스트 검색을 사용할 수 있는 언어 및 테스트 프레임워크는 무엇인가요?

  [실시간 테스트 검색](https://go.microsoft.com/fwlink/?linkid=862824)은 Roslyn 컴파일러를 사용하여 빌드되므로 관리 언어(C# 및 Visual Basic)에서만 작동합니다. 현재 실시간 테스트 검색은 xUnit, NUnit 및 MSTest 프레임워크에서만 작동합니다.

### <a name="6-how-can-i-turn-on-logs-for-the-test-explorer"></a>6. 테스트 탐색기에 대해 로그를 어떻게 켤 수 있습니까?

  **도구 > 옵션 > 테스트**로 이동하고 거기서 로깅 섹션을 찾습니다.

### <a name="7-why-are-my-tests-in-uwp-projects-not-discovered-until-i-deploy-my-app"></a>7. UWP 프로젝트의 내 테스트가 내 앱을 배포할 때까지 검색되지 않는 이유는 무엇입니까?

  UWP 테스트는 앱이 배포될 때 서로 다른 런타임을 대상으로 합니다. 따라서 UWP 프로젝트에 대해 정확히 테스트를 검색하려면 프로젝트를 빌드할 뿐만 아니라 배포도 해야 합니다.

### <a name="8-how-does-sorting-test-results-work-in-the-hierarchy-view"></a>8. 계층 보기에서 테스트 결과 정렬이 어떻게 작동합니까?

  계층 보기는 테스트를 결과에 의해서가 아니라 알파벳순으로 정렬합니다. 설정에 의한 다른 그룹은 일반적으로 테스트 결과를 결과순으로 정렬한 다음, 알파벳순으로 정렬합니다. 비교를 위해 다음 이미지의 다양한 그룹화 방법 옵션을 참조하세요. [이 GitHub 문제](https://github.com/Microsoft/vstest/issues/1425)의 디자인에 관한 피드백을 제공할 수 있습니다.

  ![정렬 예제](media/testex-sortingex.png)

### <a name="9-in-the-hierarchy-view-there-are-passed-failed-skipped-and-not-run-icons-next-to-the-project-namespace-and-class-groupings-what-do-these-icons-mean"></a>9. 계층 구조 보기에서 프로젝트, 네임스페이스, 클래스 그룹 옆에 통과, 실패, 건너뜀 및 실행 안 됨 아이콘이 있습니다. 이러한 아이콘은 무엇을 의미하나요?

  프로젝트, 네임스페이스, 클래스 그룹 옆의 아이콘은 해당 그룹 내의 테스트 상태를 나타냅니다. 다음 표를 참조하고

  ![테스트 탐색기 계층 구조 아이콘](media/testex-hierarchyicons.png)

## <a name="features"></a>기능

### <a name="how-can-i-turn-on-feature-flags-to-try-out-new-testing-features"></a>새로운 테스트 기능을 사용하기 위해 기능 플래그를 켜려면 어떻게 할까요?

기능 플래그는 기능이 일반 공급되기 전에 피드백을 제공하고 싶어하는 사용자에게 제품의 실험적 또는 완료되지 않은 부분을 제공하는 데 사용됩니다. IDE 환경이 불안정해질 수 있습니다. 가상 머신과 같은 안전한 개발 환경에서만 사용하십시오. 기능 플래그는 항상 전적으로 사용자의 책임 하에 사용하는 설정입니다. [기능 플래그 확장](https://marketplace.visualstudio.com/items?itemName=PaulHarrington.FeatureFlagsExtension) 또는 개발자 명령 프롬프트를 통해 실험적 기능을 켤 수 있습니다.

![기능 플래그 확장](media/testex-featureflag.png)

Visual Studio 개발자 명령 프롬프트를 통해 기능 플래그를 켜려면 다음 명령을 사용합니다. 컴퓨터에 Visual Studio가 설치된 경로를 변경하고 레지스트리 키를 원하는 기능 플래그로 변경합니다.

```shell
vsregedit set “C:\Program Files (x86)\Microsoft Visual Studio\Preview\Enterprise” HKLM FeatureFlags\TestingTools\UnitTesting\HierarchyView Value dword 1
```

> [!NOTE]
> dword 뒤에 1 대신 0을 사용하면 동일한 명령으로 플래그를 끌 수 있습니다.
  
## <a name="see-also"></a>참고 항목

<xref:Microsoft.VisualStudio.TestTools.UnitTesting?displayProperty=fullName>  
[기존 코드에 대한 단위 테스트 만들기 및 실행](http://msdn.microsoft.com/e8370b93-085b-41c9-8dec-655bd886f173)
[코드 단위 테스트](unit-test-your-code.md)
[Live Unit Testing FAQ](live-unit-testing-faq.md)
