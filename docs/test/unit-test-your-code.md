---
title: Visual Studio에서 단위 테스트
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
helpviewer_keywords:
- Visual Studio, unit tests
- unit tests, verifying code with
- testing code, automated tests
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: ea1d186f280c41d5330b3860f5b0802fb001bf84
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="unit-test-your-code"></a>코드 단위 테스트

개발자와 테스터는 단위 테스트를 통해 C#, Visual Basic 및 C++ 프로젝트에서 클래스의 메서드에 있는 논리 오류를 빠르게 찾을 수 있습니다.

단위 테스트 도구는 다음과 같습니다.

* **테스트 탐색기**&mdash;단위 테스트를 실행하고 해당 결과를 **테스트 탐색기**에서 확인할 수 있습니다. 타사 프레임워크를 비롯하여 **테스트 탐색기**용 어댑터가 있는 모든 단위 테스트 프레임워크를 사용할 수 있습니다.

* **관리 코드용 Microsoft 단위 테스트 프레임우크**&mdash;관리 코드용 Microsoft 단위 테스트 프레임워크는 Visual Studio와 함께 설치되며 .NET 코드 테스트용 프레임워크를 제공합니다.

* **C++용 Microsoft 단위 테스트 프레임워크**&mdash;C++용 Microsoft 단위 테스트 프레임워크는 **C++을 통한 데스크톱 개발** 워크로드의 일부로 설치됩니다. 네이티브 코드 테스트용 프레임워크를 제공합니다. Google Test, Boost.Test 및 CTest 프레임워크도 포함되며 타사 어댑터를 추가 테스트 프레임 워크에서 사용할 수 있습니다. 자세한 내용은 [C/C++에 대한 단위 테스트 작성](../test/writing-unit-tests-for-c-cpp.md)을 참조하세요.

* **코드 검사 도구**&mdash;단위 테스트가 테스트 탐색기의 명령 하나에서 실행하는 제품 코드의 양을 결정할 수 있습니다.

* **Microsoft Fakes 격리 프레임워크**&mdash;Microsoft Fakes 격리 프레임워크는 테스트 중인 코드에서 종속성을 만드는 프로덕션 및 시스템 코드에 대한 대체 클래스 및 메서드를 만들 수 있습니다. 함수에 대한 모조 위임을 구현하여 종속성 개체의 동작과 출력을 제어할 수 있습니다.

[IntelliTest](../test/generate-unit-tests-for-your-code-with-intellitest.md)를 사용하면 .NET 코드를 탐색하여 테스트 데이터 및 단위 테스트 도구 모음을 생성할 수도 있습니다. 코드의 모든 문에 대해 해당 문을 실행할 테스트 입력이 생성됩니다. 코드의 모든 조건부 분기에 대해 사례 분석이 수행됩니다.

## <a name="key-tasks"></a>주요 작업

다음 항목은 단위 테스트를 이해하고 만드는 데 유용합니다.

|작업|관련 항목|
|-----------|-----------------------|
|**빠른 시작 및 연습:** 다음 항목을 사용하여 코드 예제에서 Visual Studio의 단위 테스트에 대해 알아봅니다.|-   [연습: 관리 코드에 대한 단위 테스트 만들기 및 실행](../test/walkthrough-creating-and-running-unit-tests-for-managed-code.md)<br />-   [빠른 시작: 테스트 탐색기를 사용한 테스트 기반 개발](../test/quick-start-test-driven-development-with-test-explorer.md)<br />-   [기존 C++ 응용 프로그램에 단위 테스트 추가](../test/unit-testing-existing-cpp-applications-with-test-explorer.md)|
|**테스트 탐색기를 사용한 단위 테스트:** 테스트 탐색기를 통해 보다 다 생산적이고 효율적인 단위 테스트를 만드는 방법에 대해 알아봅니다.|-   [단위 테스트 기본 사항](../test/unit-test-basics.md)<br />-   [단위 테스트 프로젝트 만들기](../test/create-a-unit-test-project.md)<br />-   [테스트 탐색기를 사용하여 단위 테스트 실행](../test/run-unit-tests-with-test-explorer.md)<br />-   [타사 단위 테스트 프레임워크 설치](../test/install-third-party-unit-test-frameworks.md)|
|**관리 코드 단위 테스트:**|-   [관리 코드용 Microsoft 단위 테스트 프레임워크를 사용하여 .NET Framework용 단위 테스트 작성](../test/writing-unit-tests-for-the-dotnet-framework-with-the-microsoft-unit-test-framework-for-managed-code.md)|
|**C++ 코드 단위 테스트**|-   [C++용 Microsoft 단위 테스트 프레임워크를 사용하여 C/C++용 단위 테스트 작성](../test/writing-unit-tests-for-c-cpp-with-the-microsoft-unit-testing-framework-for-cpp.md)|
|**단위 테스트 격리**|-   [Microsoft Fakes를 사용하여 테스트 중인 코드 격리](../test/isolating-code-under-test-with-microsoft-fakes.md)|
|**코드 검사를 사용하여 프로젝트의 코드 중 테스트되는 부분 식별:** Visual Studio 테스트 도구의 코드 검사 기능에 대해 알아보세요.|-   [코드 검사를 사용하여 테스트할 코드 범위 결정](../test/using-code-coverage-to-determine-how-much-code-is-being-tested.md)|
|**부하 테스트를 사용하여 스트레스 및 성능 분석 수행:** 응용 프로그램에서 성능 및 스트레스 문제를 격리하기 위해 부하 테스트를 만들고 여기에 단위 테스트를 추가할 수 있습니다.|-   [부하 테스트(VSTS 및 TFS)](/vsts/load-test/)|
|**품질 게이트 설정:** 코드의 품질을 확인하기 위해 코드를 체크 인하기 전에 테스트가 실행되도록 품질 게이트를 만들 수 있습니다.|-   [체크 인 정책(VSTS)](/vsts/tfvc/add-check-policies)|
|**테스트 옵션 설정:** 예를 들면 테스트 결과가 저장되는 위치를 지정할 수 있습니다.|[.runsettings 파일을 사용하여 단위 테스트 구성](../test/configure-unit-tests-by-using-a-dot-runsettings-file.md)|

## <a name="api-reference-documentation"></a>API 참조 설명서

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting>에서는 단위 테스트를 지원하는 특성, 예외, 어설션 및 기타 클래스를 제공하는 UnitTesting 네임스페이스에 대해 설명합니다.
- <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Web>에서는 ASP.NET 및 웹 서비스 단위 테스트를 지원하여 UnitTesting 네임스페이스를 확장하는 UnitTesting.Web 네임스페이스에 대해 설명합니다.

## <a name="see-also"></a>참고 항목

- [코드 품질 향상](/visualstudio/test/improve-code-quality)
