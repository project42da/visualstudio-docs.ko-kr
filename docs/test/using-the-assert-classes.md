---
title: Visual Studio에서 단위 테스트를 위한 Assert 클래스 사용
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: reference
helpviewer_keywords:
- Assert classes
- Assert statements
- unit tests, Assert statements
- unit tests, Assert classes
ms.author: gewarren
manager: douge
ms.workload:
- multiple
author: gewarren
ms.openlocfilehash: 2d56477822fa2d965902d9442d47e2c3ab24d656
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="use-the-assert-classes"></a>Assert 클래스 사용

UnitTestingFramework 네임스페이스의 Assert 클래스를 사용하여 특정 기능을 확인합니다. 단위 테스트 메서드는 개발 코드에서 메서드 코드를 실행하지만, Assert 문을 포함하는 경우에만 코드의 동작이 정확한지 여부를 보고합니다.

## <a name="kinds-of-asserts"></a>Assert의 종류

 <xref:Microsoft.VisualStudio.TestTools.UnitTesting> 네임스페이스는 다음과 같은 여러 종류의 Assert 클래스를 제공합니다.

 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert>

 테스트 메서드에서는 Assert.AreEqual()과 같은 Assert 클래스의 메서드를 원하는 수만큼 사용할 수 있습니다. Assert 클래스에서는 여러 메서드를 선택할 수 있으며, 이러한 메서드는 대부분 여러 오버로드를 포함합니다.

 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.CollectionAssert>

 CollectionAssert 클래스를 사용하여 개체 컬렉션을 비교하고 컬렉션 하나 이상의 상태를 확인합니다.

 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.StringAssert>

 StringAssert 클래스를 사용하여 문자열을 비교합니다. 이 클래스에는 StringAssert.Contains, StringAssert.Matches, StringAssert.StartsWith 등의 여러 가지 유용한 메서드가 포함되어 있습니다.

 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.AssertFailedException>

 테스트가 실패할 때마다 AssertFailedException 예외가 throw됩니다. 테스트는 시간이 초과되거나, 예기치 않은 예외가 throw되거나, Failed 결과를 생성하는 Assert 문을 포함하는 경우 실패합니다.

 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.AssertInconclusiveException>

 테스트 결과 Inconclusive 결과가 생성될 때마다 AssertInconclusiveException 예외가 throw됩니다. 일반적으로는 아직 작업 중엔 테스트에 Assert.Inconclusive 문을 추가하여 해당 테스트가 아직 실행할 준비가 되지 않았음을 나타냅니다.

> [!NOTE]
> Ignore 특성을 사용하여 테스트 실행 준비가 되지 않았음을 표시하는 전략을 사용할 수도 있습니다. 그러나 이 전략을 사용하는 경우 구현 과정이 남아 있는 테스트 수에 대한 보고서를 쉽게 생성할 수 없다는 단점이 있습니다.

 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.UnitTestAssertException>

 새 Assert 예외 클래스를 작성하는 경우 해당 클래스가 기본 클래스 UnitTestAssertException에서 속성을 상속하도록 하면 예외를 어설션 실패로 보다 쉽게 식별할 수 있으며, 테스트 또는 프로덕션 코드에서 예기치 않은 예외가 throw되지 않습니다.

 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.ExpectedExceptionAttribute>

 개발 코드의 메서드가 throw할 것으로 예상했던 예외가 실제로 해당 메서드에서 throw됨을 테스트 메서드가 확인하도록 하려는 경우 ExpectedExceptionAttribute 특성으로 테스트 메서드를 데코레이팅합니다.

## <a name="see-also"></a>참고 항목

- <xref:Microsoft.VisualStudio.TestTools.UnitTesting>
- [코드 단위 테스트](../test/unit-test-your-code.md)
