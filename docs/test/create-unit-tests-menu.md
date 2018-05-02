---
title: Visual Studio에서 단위 테스트 메서드 스텁 만들기
ms.date: 05/02/2017
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
helpviewer_keywords:
- unit testing, create unit tests
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 39c59d76d10c2028214b2a1ea15ff139000e3080
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="create-unit-test-method-stubs-with-the-create-unit-tests-command"></a>단위 테스트 만들기 명령을 사용하여 단위 테스트 메서드 스텁 만들기

Visual Studio **단위 테스트 만들기** 명령은 단위 테스트 메서드 스텁을 만드는 기능을 제공합니다. 이 기능을 사용하여 테스트 프로젝트, 테스트 클래스 및 클래스 내 테스트 메서드 스텁을 쉽게 구성할 수 있습니다.

## <a name="availability-and-extensions"></a>가용성 및 확장

**단위 테스트 만들기** 메뉴 명령:

* Visual Studio 2015 이상의 Community, Professional 및 Enterprise Edition에서 사용할 수 있습니다.

* .NET Framework를 대상으로 하는 C# 코드만 지원합니다.

* 확장 가능하고 MSTest, MSTest V2, NUnit, xUnit 형식으로 테스트 내보내기를 지원합니다.

## <a name="get-started"></a>시작

시작하려면 테스트할 프로젝트의 코드 편집기에서 메서드, 형식 또는 네임스페이스를 선택하고, 바로 가기 메뉴를 열고, **단위 테스트 만들기**를 선택합니다. 이렇게 하면 새 단위 테스트에 대한 만들기 옵션을 선택할 수 있는 **단위 테스트 만들기** 대화 상자가 열립니다.

![단위 테스트 만들기 명령 사용](media/createunittestcommand.png)

## <a name="setting-unit-test-traits"></a>단위 테스트 특성 설정

이러한 테스트를 테스트 자동화 프로세스의 일부로 실행하려면 다른 테스트 프로젝트에서 만들어진 테스트를 사용하고(위 대화 상자의 두 번째 옵션) 단위 테스트에 대한 단위 테스트 특성을 설정하는 방법을 고려할 수 있습니다. 이 방법으로 이러한 특정 테스트를 지속적인 통합 또는 지속적인 배포 파이프라인의 일부로 더 쉽게 포함하거나 제외할 수 있습니다. 다음과 같이 단위 테스트에 직접 메타데이터를 추가하여 특성을 설정합니다.

![단위 테스트 특성 설정](media/createunittest.png)

## <a name="using-third-party-unit-test-frameworks"></a>타사 단위 테스트 프레임워크 사용

Visual Studio에서는 모든 테스트 프레임워크를 사용하여 필요에 맞는 단위 테스트를 쉽게 만들 수 있습니다. 기타 프레임워크를 설치하려면.

1. **도구** > **확장 및 업데이트**를 선택합니다.
2. **온라인** > **Visual Studio Marketplace** > **도구**를 확장한 다음, **테스트**를 선택합니다.

![타사 테스트 프레임워크 사용](media/createunittestfx.png)

테스트 프레임워크 확장은 Visual Studio Marketplace에서 사용할 수 있습니다.

* [NUnit Extension for the Test Generators](https://marketplace.visualstudio.com/items?itemName=NUnitDevelopers.TestGeneratorNUnitextension)(테스트 생성기에 대한 NUnit 확장)
* [xUnit.net Extension for the Test Generators](https://marketplace.visualstudio.com/items?itemName=BradWilson.xUnitnetTestExtensions)(테스트 생성기에 대한 xUnit.net 확장)

## <a name="when-should-i-use-this-feature"></a>이 기능은 언제 사용해야 하나요?

이 기능은 단위 테스트를 만들어야 할 때마다 사용하지만, 특히 테스트 검사가 거의 없거나 문서가 없는 기존 코드를 테스트할 경우 사용합니다. 즉, 코드 사양이 제한되거나 없는 경우 사용합니다. 이 기능은 관찰된 코드 동작의 특징을 결정하는 [스마트 단위 테스트](http://blogs.msdn.com/b/visualstudioalm/archive/2014/11/19/introducing-smart-unit-tests.aspx)와 비슷한 방법을 효과적으로 구현합니다.

그러나 이 기능은 개발자가 일부 코드를 먼저 작성하고 이 코드를 사용하여 유닛 테스트 분야를 부트스트랩하는 상황에도 똑같이 적용할 수 있습니다. 코딩 흐름 내에서 개발자는 특정 코드 조건에 대한 단위 테스트 메서드 스텁을 빠르게 만들어야 할 수 있습니다(적합한 테스트 클래스 및 적합한 테스트 프로젝트 사용).

## <a name="see-also"></a>참고 항목

- [Creating unit test method stubs with “Create Unit Tests”](https://blogs.msdn.microsoft.com/visualstudioalm/2015/03/06/creating-unit-test-method-stubs-with-create-unit-tests/)(“유닛 테스트 만들기”를 사용하여 유닛 테스트 메서드 스텁 만들기)
- [유닛 테스트 블로그 게시물](https://blogs.msdn.microsoft.com/devops/?s=unit+testing)
