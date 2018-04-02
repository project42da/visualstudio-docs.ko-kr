---
title: Visual Studio에서 단위 테스트 시작 | Microsoft Docs
ms.date: 05/02/2017
ms.technology: vs-ide-test
ms.topic: article
helpviewer_keywords:
- unit testing, create unit test plans
ms.author: gewarren
manager: ghogen
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: a95891afa4a5b05dcaa238bb06fcc57268542187
ms.sourcegitcommit: 900ed1e299cd5bba56249cef8f5cf3981b10cb1c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/19/2018
---
# <a name="get-started-with-unit-testing"></a>유닛 테스트 시작

Visual Studio를 사용하여 코드 상태를 유지 관리하고, 코드 검사를 적용하고, 고객이 찾기 전에 오류와 결함을 찾기 위한 단위 테스트를 정의하고 실행합니다.

## <a name="create-unit-tests"></a>단위 테스트 만들기

단위 테스트를 만들고 수시로 실행하여 코드가 올바르게 작동하는지 확인할 수 있습니다.

1. 단위 테스트 프로젝트를 만듭니다.

   ![솔루션에 단위 테스트 프로젝트 추가](media/createunittest1.png)

1. 프로젝트 이름을 지정합니다.

   ![단위 테스트 프로젝트 템플릿](media/createunittest2.png)

   프로젝트가 솔루션에 추가됩니다.

   ![솔루션 탐색기의 단위 테스트 프로젝트](media/createunittest5.png)

1. 단위 테스트 프로젝트에서 테스트하려는 프로젝트에 대한 참조를 추가합니다.

   ![단위 테스트 프로젝트에 참조 추가](media/createunittest6.png)

1. 테스트할 코드가 포함된 프로젝트를 선택합니다.

   ![추가할 패키지 참조 선택](media/createunittest7.png)

1. 단위 테스트를 코딩합니다.

   ![단위 테스트에 코드 추가](media/createunittest8.png)

**단위 테스트 만들기** [명령](create-unit-tests-menu.md)을 사용하여 단위 테스트 메서드 스텁을 만들 수도 있습니다.

![단위 테스트 만들기 명령 사용](media/createunittestcommand2.png)

## <a name="run-unit-tests"></a>단위 테스트 실행

1. 테스트 탐색기를 엽니다.

   ![[테스트] 메뉴에서 테스트 탐색기 열기](media/rununittest1.png)

1. 단위 테스트를 실행합니다.

   ![테스트 탐색기에서 단위 테스트 실행](media/rununittest2.png)

   테스트 탐색기에서 통과 또는 실패한 단위 테스트를 볼 수 있습니다.

   ![테스트 탐색기에서 단위 테스트 결과 검토](media/rununittest3.png)

## <a name="view-live-unit-test-results"></a>라이브 단위 테스트 결과 보기

Visual Studio 2017 이상에서 MSTest, xUnit 또는 NUnit 테스트 프레임워크를 사용하고 있다면 단위 테스트의 라이브 결과를 볼 수 있습니다.

1. **테스트** 메뉴에서 Live Unit Testing을 설정합니다.

   ![Live Unit Testing 설정](media/live-test-results-start.png)

1. 코드를 작성하고 편집할 때 코드 편집기 창에 테스트 결과가 표시됩니다.

   ![테스트 결과 보기](media/live-test-results-ui.png)

1. 테스트 결과 표시기를 선택하면 추가 정보가 표시됩니다.

   ![테스트 결과 표시기 선택](media/live-test-results-details.png)

자세한 내용은 [Live Unit Testing](../test/live-unit-testing-intro.md)을 참조하세요.

## <a name="generate-unit-tests-with-intellitest"></a>IntelliTest를 사용하여 단위 테스트 생성

IntelliTest를 실행하면 오류가 발생하는 테스트를 쉽게 확인하고 필요한 코드를 추가하여 수정할 수 있습니다. 생성된 테스트 중에서 재발 테스트 모음을 제공하기 위해 테스트 프로젝트에 저장할 테스트를 선택할 수 있습니다. 코드를 변경하면 IntelliTest를 다시 실행하여 생성된 테스트를 코드 변경 내용과 동기화합니다. 방법을 알아보려면 [IntelliTest를 사용하여 코드에 대한 단위 테스트 생성](../test/generate-unit-tests-for-your-code-with-intellitest.md)을 참조하세요.

![IntelliTest를 사용하여 단위 테스트 생성](media/intellitest.png)

## <a name="run-unit-tests-with-test-explorer"></a>테스트 탐색기를 사용하여 단위 테스트 실행

테스트 탐색기를 사용하여 Visual Studio 또는 타사 단위 테스트 프로젝트에서 단위 테스트를 실행하고, 테스트를 범주로 그룹화하며, 테스트 목록을 필터링하고, 테스트 PLAYLIST를 만들어 저장하고 실행할 수 있습니다. 테스트를 디버그하고 테스트 성능 및 코드 검사를 분석할 수도 있습니다. 방법을 알아보려면 [테스트 탐색기를 사용하여 단위 테스트 실행](../test/run-unit-tests-with-test-explorer.md)을 참조하세요.

![테스트 탐색기를 사용하여 단위 테스트 실행](media/testexplorer.png)

## <a name="use-code-coverage-to-determine-how-much-code-is-being-tested"></a>코드 검사를 사용하여 테스트할 코드 범위 결정

프로젝트의 코드 중 유닛 테스트와 같은 코딩된 테스트를 사용하여 실제로 테스트할 부분을 결정하려면 Visual Studio의 코드 검사 기능을 사용합니다. 버그로부터 효과적으로 보호하려면 코드의 상당한 부분을 실행 또는 '검사'해야 합니다. 방법을 알아보려면 [코드 검사를 사용하여 테스트할 코드 범위 결정](../test/using-code-coverage-to-determine-how-much-code-is-being-tested.md)을 참조하세요.

![코드 검사를 사용하여 테스트할 코드 범위 결정](media/codecoverage.png)

## <a name="use-a-different-unit-test-framework"></a>다른 단위 테스트 프레임워크 사용

Boost, Google, nUnit 등의 타사 테스트 프레임워크를 사용하여 Visual Studio에서 단위 테스트를 실행할 수 있습니다. Visual Studio의 Test Runner가 프레임워크와 함께 작동할 수 있도록 해당 프레임워크용 플러그인을 사용하십시오.

다음은 타사 테스트 프레임 워크를 사용할 수 있게 설정하는 단계입니다.

1. 메뉴 모음에서 **도구** > **확장 및 업데이트...**를 선택합니다.

1. **확장명 및 업데이트** 대화 상자에서 **온라인** 범주 및 **Visual Studio Marketplace**를 차례로 확장합니다. 그런 다음, **도구** > **테스트**를 선택합니다.

   ![Visual Studio Marketplace](media/extensions-and-updates-testing.png)

1. 설치하려는 프레임워크 또는 어댑터를 선택한 다음, **다운로드**를 선택합니다.

1. 클래스 라이브러리 프로젝트를 만들고 솔루션에 추가합니다.

   ![클래스 라이브러리 프로젝트 이름 지정 및 추가](media/create3rdpartyunittest3.png)

1. 플러그 인을 설치합니다. **솔루션 탐색기**에서 클래스 라이브러리 프로젝트를 선택한 다음, 마우스 오른쪽 단추로 클릭하거나 컨텍스트 메뉴에서 **NuGet 패키지 관리...** 를 선택합니다.

   ![NuGet 패키지를 관리하여 플러그 인 설치](media/create3rdpartyunittest3a.png)

   [NuGet](https://www.nuget.org/)은 Visual Studio의 확장 프로그램으로, 프로젝트의 라이브러리 및 도구를 추가하고 업데이트하는 데 사용할 수 있습니다.

1. **NuGet 패키지 관리자** 창에서 플러그 인을 검색하고 선택한 다음, **설치**를 선택합니다.

   ![타사 프레임워크 설치](media/create3rdpartyunittest4.png)

   프레임워크가 프로젝트에서 참조됩니다.

   ![타사 단위 테스트 프레임워크에 대한 참조가 솔루션에 추가됨](media/create3rdpartyunittest6.png)

1. 클래스 라이브러리 프로젝트의 **참조** 노드에서 **참조 추가...**를 선택합니다.

   ![프로젝트에 참조 추가](media/createunittest6.png)

1. **참조 관리자** 대화 상자에서 테스트할 코드를 포함하는 프로젝트를 선택합니다.

   ![테스트할 코드 프로젝트 선택](media/createunittest7.png)

1. 단위 테스트를 코딩합니다.

   ![단위 테스트에 코드 추가](media/create3rdpartyunittest7.png)

## <a name="see-also"></a>참고 항목

* [단위 테스트 만들기 명령](create-unit-tests-menu.md)
* [IntelliTest를 사용하여 테스트 생성](generate-unit-tests-for-your-code-with-intellitest.md)
* [테스트 탐색기를 사용하여 테스트 실행](run-unit-tests-with-test-explorer.md)
* [코드 검사 결정](using-code-coverage-to-determine-how-much-code-is-being-tested.md)
* [코드 품질 향상](improve-code-quality.md)