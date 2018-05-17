---
title: 관리 코드에 대한 단위 테스트 만들기 및 실행
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-ide-test
ms.topic: conceptual
helpviewer_keywords:
- unit tests, walkthrough
- unit tests, creating
- unit tests, generating
- unit tests, running
- unit tests, authoring
ms.author: gewarren
manager: douge
ms.workload:
- dotnet
author: gewarren
ms.openlocfilehash: 29472e2590a767c98c5674bce14712171f16fdbf
ms.sourcegitcommit: a8e01952be5a539104e2c599e9b8945322118055
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/03/2018
---
# <a name="walkthrough-create-and-run-unit-tests-for-managed-code"></a>연습: 관리 코드에 대한 단위 테스트 만들기 및 실행

이 연습에서는 관리 코드에 대한 Microsoft 단위 테스트 프레임워크 및 Visual Studio **테스트 탐색기**를 사용하여 일련의 단위 테스트를 생성, 실행 및 사용자 지정하는 방법을 안내합니다. 개발 중인 C# 프로젝트로 시작하여 해당 코드를 실행해 보는 테스트를 만들어 테스트를 실행하고 결과를 검사합니다. 그런 다음, 프로젝트 코드를 변경하고 테스트를 다시 실행할 수 있습니다.

> [!NOTE]
> 이 연습에서는 관리 코드에 Microsoft 단위 테스트 프레임워크를 사용합니다. **테스트 탐색기**에서는 **테스트 탐색기**용 어댑터가 포함된 타사 단위 테스트 프레임워크의 테스트도 실행할 수 있습니다. 자세한 내용은 [타사 단위 테스트 프레임워크 설치](../test/install-third-party-unit-test-frameworks.md)를 참조하세요.

> [!NOTE]
> 명령줄에서 테스트를 실행하는 방법에 대한 자세한 내용은 [연습: 명령줄 테스트 유틸리티 사용](http://msdn.microsoft.com/Library/52c11992-9e94-4067-a4b7-59f19d69d867)을 참조하세요.

## <a name="prerequisites"></a>전제 조건

- Bank 프로젝트. [단위 테스트를 만들기 위한 샘플 프로젝트](../test/sample-project-for-creating-unit-tests.md)를 참조하세요.

## <a name="create-a-project-to-test"></a>테스트할 프로젝트 만들기

1. Visual Studio를 엽니다.

2. **파일** 메뉴에서 **새로 만들기** > **프로젝트**를 선택합니다.

     **새 프로젝트** 대화 상자가 나타납니다.

3. **설치된 템플릿**에서 **Visual C#** 을 클릭합니다.

4. 응용 프로그램 형식 목록에서 **클래스 라이브러리**를 클릭합니다.

5. In the **이름** 상자에 `Bank` 를 가리킨 다음 **확인**을 참조하세요.

    > [!NOTE]
    > "Bank"라는 이름이 이미 사용되고 있으면 프로젝트에 대해 다른 이름을 선택합니다.

     새 Bank 프로젝트가 만들어져 **솔루션 탐색기**에 표시되고 코드 편집기에 *Class1.cs* 파일이 열립니다.

    > [!NOTE]
    > *Class1.cs* 파일이 코드 편집기에서 열리지 않으면 솔루션 탐색기에서 *Class1.cs* 파일을 두 번 클릭하여 엽니다.

6. [단위 테스트를 만들기 위한 샘플 프로젝트](../test/sample-project-for-creating-unit-tests.md)에서 소스 코드를 복사하고 *Class1.cs*의 원래 내용을 복사된 코드로 바꿉니다.

7. 파일을 *BankAccount.cs*로 저장합니다.

8. **빌드** 메뉴에서 **솔루션 빌드**를 클릭합니다.

이제 Bank라는 프로젝트가 준비되었습니다. 이 프로젝트에는 테스트할 소스 코드와 테스트에 사용할 도구가 들어 있습니다. Bank에 대한 네임스페이스 BankAccountNS에는 다음 절차에서 테스트할 메서드가 포함된 공용 클래스인 BankAccount가 있습니다.

이 문서에서는 테스트가 Debit 메서드에 집중합니다. Debit 메서드는 계좌에서 돈을 인출할 때 호출됩니다. 다음은 메서드 정의입니다.

```csharp
// Method to be tested.
public void Debit(double amount)
{
    if(amount > m_balance)
    {
        throw new ArgumentOutOfRangeException("amount");
    }
    if (amount < 0)
    {
        throw new ArgumentOutOfRangeException("amount");
    }
    m_balance += amount;
}
```

## <a name="create-a-unit-test-project"></a>단위 테스트 프로젝트 만들기

1. **파일** 메뉴에서 **추가** > **새 프로젝트**를 선택합니다.

2. 새 프로젝트 대화 상자에서 **설치됨**, **Visual C#** 을 확장한 다음 **테스트**를 선택합니다.

3. 템플릿 목록에서 **단위 테스트 프로젝트**를 선택합니다.

4. **이름** 상자에 `BankTests`를 입력한 다음, **확인**을 선택합니다.

     **BankTests** 프로젝트가 **Bank** 솔루션에 추가됩니다.

5. **BankTests** 프로젝트에서 **Bank** 프로젝트에 대한 참조를 추가합니다.

     솔루션 탐색기에서 **BankTests** 프로젝트의 **참조**를 선택하고 상황에 맞는 메뉴에서 **참조 추가**를 선택합니다.

6. 참조 관리자 대화 상자에서 **솔루션** 을 확장한 다음 **Bank** 항목을 선택합니다.

## <a name="create-the-test-class"></a>테스트 클래스 만들기

`BankAccount` 클래스를 확인하기 위한 테스트 클래스를 만듭니다. 프로젝트 템플릿에서 생성된 *UnitTest1.cs* 파일을 사용할 수 있지만 파일 및 클래스에 설명이 포함된 이름을 제공할 수 있습니다. **솔루션 탐색기**에서 파일 이름을 바꾸면 한 번에 수행할 수 있습니다.

### <a name="rename-a-class-file"></a>클래스 파일 이름 바꾸기

**솔루션 탐색기**에서 BankTests 프로젝트의 *UnitTest1.cs* 파일을 선택합니다. 상황에 맞는 메뉴에서 **이름 바꾸기**를 선택한 다음, 파일 이름을 *BankAccountTests.cs*로 바꿉니다. 프로젝트에서 코드 요소 `UnitTest1`에 대한 모든 참조 이름을 바꿀지 묻는 대화 상자에서 **예**를 선택합니다.

이 단계에서는 클래스 이름을 `BankAccountTests`로 변경합니다. *BankAccountTests.cs* 파일에는 이제 다음 코드가 들어 있습니다.

```csharp
using System;
using Microsoft.VisualStudio.TestTools.UnitTesting;

namespace BankTests
{
    [TestClass]
    public class BankAccountTests
    {
        [TestMethod]
        public void TestMethod1()
        {
        }
    }
}
```

### <a name="add-a-using-statement-to-the-project-under-test"></a>테스트에서 프로젝트에 using 문 추가

`using` 문을 클래스에 추가하여 정규화된 이름을 사용하지 않고 테스트 중인 프로젝트를 호출할 수 있습니다. 클래스 파일의 맨 위에 다음을 추가합니다.

```csharp
using BankAccountNS;
```

### <a name="test-class-requirements"></a>테스트 클래스 요구 사항

테스트 클래스의 최소 요구 사항은 다음과 같습니다.

- `[TestClass]` 특성은 테스트 탐색기에서 실행하려는 단위 테스트 메서드가 포함된 모든 클래스의 관리 코드에 대한 Microsoft 단위 테스트 프레임워크에 필요합니다.

- 테스트 탐색기에서 실행하려는 각 테스트 메서드에는 `[TestMethod]`특성이 있어야 합니다.

`[TestClass]` 특성이 없는 단위 테스트 프로젝트에 다른 클래스를 사용하거나 `[TestMethod]` 특성이 없는 테스트 클래스에 다른 메서드를 사용할 수 있습니다. 테스트 메서드에서 이러한 다른 클래스와 메서드를 사용할 수 있습니다.

## <a name="create-the-first-test-method"></a>첫 번째 테스트 메서드 만들기

이 절차에서는 단위 테스트 메서드를 작성하여 `Debit` 클래스의 `BankAccount` 메서드 동작을 확인합니다. `Debit` 메서드는 이 문서의 앞부분에 나와 있습니다.

확인해야 하는 동작이 3개 이상 있습니다.

- 이 메서드는 대변 금액이 잔액보다 큰 경우 <xref:System.ArgumentOutOfRangeException> 을 발생시킵니다.

- 이 메서드는 차변 금액이 0보다 작을 경우 <xref:System.ArgumentOutOfRangeException>을 throw합니다.

- 대변 금액이 유효한 경우 이 메서드는 잔고에서 차변 금액을 뺍니다.

> [!TIP]
> 이 연습에서 사용하지 않으므로 기본 `TestMethod1` 메서드를 삭제할 수 있습니다.

### <a name="to-create-a-test-method"></a>테스트 메서드를 만들려면

첫 번째 테스트에서는 유효 금액(잔고보다 작고 0보다 큰 값)이 계좌로부터 올바른 금액을 인출하는지 확인합니다. 다음 메서드를 `BankAccountTests` 클래스에 추가합니다.

```csharp
[TestMethod]
public void Debit_WithValidAmount_UpdatesBalance()
{
    // Arrange
    double beginningBalance = 11.99;
    double debitAmount = 4.55;
    double expected = 7.44;
    BankAccount account = new BankAccount("Mr. Bryan Walton", beginningBalance);

    // Act
    account.Debit(debitAmount);

    // Assert
    double actual = account.Balance;
    Assert.AreEqual(expected, actual, 0.001, "Account not debited correctly");
}
```

메서드가 간단함: 기초 잔액으로 새 `BankAccount` 개체를 만든 다음, 유효한 금액을 인출합니다. <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.AreEqual%2A> 메서드를 사용하여 최종 잔액이 기대한 것과 같은지 확인합니다.

### <a name="test-method-requirements"></a>테스트 메서드 요구 사항

테스트 메서드는 다음 요구 사항을 충족해야 합니다.

- `[TestMethod]` 특성으로 데코레이트됩니다.

- `void`를 반환합니다.

- 매개 변수를 사용할 수 없습니다.

## <a name="build-and-run-the-test"></a>테스트 빌드 및 실행

1. **빌드** 메뉴에서 **솔루션 빌드**를 선택합니다.

   오류가 없는 경우 **실행하지 않은 테스트** 그룹에 나열된 **Debit_WithValidAmount_UpdatesBalance**와 함께 **테스트 탐색기**가 나타납니다.

   > [!TIP]
   > 빌드에 성공한 후 **테스트 탐색기**가 나타나지 않는 경우 메뉴에서 **테스트** 를 선택하고, **창**을 선택한 다음, **테스트 탐색기**를 선택합니다.

2. **모두 실행** 을 선택하여 테스트를 실행합니다. 테스트가 실행되는 동안 창 맨 위의 상태 표시줄에 애니메이션이 사용됩니다. 테스트 실행이 끝날 때 테스트 메서드가 통과했으면 녹색이 되고 테스트가 실패하면 빨간색이 됩니다.

3. 이러한 경우 테스트가 실패합니다. 테스트 메서드가 **실패한 테스트** 그룹으로 이동합니다. 창 하단에서 세부 정보를 보려면 **테스트 탐색기**에서 메서드를 선택합니다.

## <a name="fix-your-code-and-rerun-your-tests"></a>코드를 수정하고 테스트 다시 실행

**테스트 결과 분석**

테스트 결과에 실패를 설명하는 메시지가 포함됩니다. `AreEquals` 메서드의 경우 메시지에 예상 값(**Expected\<*value*>** 매개 변수)과 실제로 수신한 값(**Actual\<*value*>** 매개 변수)이 표시됩니다. 잔고가 감소할 것으로 예상했지만 실제로는 인출금만큼 증가했습니다.

단위 테스트에서 버그 발견됨: *차감*해야 할 경우 잔고에 인출금이 *추가*됩니다.

**버그 수정**

오류를 수정하려면 다음 줄을

```csharp
m_balance += amount;
```

다음으로 바꿉니다.

```csharp
m_balance -= amount;
```

**테스트 다시 실행**

테스트 탐색기에서 **모두 실행** 을 선택하여 테스트를 다시 실행합니다. 빨강/녹색 막대가 테스트 통과를 나타내는 녹색으로 바뀌고 테스트는 **통과한 테스트** 그룹으로 이동합니다.

## <a name="use-unit-tests-to-improve-your-code"></a>단위 테스트를 사용하여 코드 개선

이 섹션에서는 반복적인 분석 프로세스, 단위 테스트 개발 및 리팩터링을 통해 프로덕션 코드를 보다 강력하고 효과적으로 만드는 방법을 설명합니다.

**문제 분석**

유효한 금액이 `Debit` 메서드에서 제대로 공제되었는지 확인하기 위한 테스트 메서드를 만들었습니다. 이제 차변 금액이 다음 중 하나인 경우 메서드가 <xref:System.ArgumentOutOfRangeException>을 throw하는지 확인합니다.

- 잔고보다 크거나
- 0보다 작음

**테스트 메서드 만들기**

차변 금액이 0보다 작은 경우 올바른 동작을 확인하기 위해 테스트 메서드를 만듭니다.

```csharp
[TestMethod]
[ExpectedException(typeof(ArgumentOutOfRangeException))]
public void Debit_WhenAmountIsLessThanZero_ShouldThrowArgumentOutOfRange()
{
    // Arrange
    double beginningBalance = 11.99;
    double debitAmount = -100.00;
    BankAccount account = new BankAccount("Mr. Bryan Walton", beginningBalance);

    // Act
    account.Debit(debitAmount);

    // Assert is handled by the ExpectedException attribute on the test method.
}
```

<xref:Microsoft.VisualStudio.TestTools.UnitTesting.ExpectedExceptionAttribute> 특성을 사용하여 올바른 예외가 throw되었음을 어설션합니다. <xref:System.ArgumentOutOfRangeException> 을 throw되는 경우가 아니면 이 특성으로 인해 테스트에 실패합니다. 차변 금액이 0보다 작을 때, 보다 일반적인 <xref:System.ApplicationException>을 throw하기 위해 테스트 중인 메서드를 일시적으로 수정하면 테스트가 올바르게 작동합니다&mdash;즉, 실패합니다.

인출한 금액이 잔고보다 많을 경우를 테스트하려면 다음 단계를 수행합니다.

1. `Debit_WhenAmountIsMoreThanBalance_ShouldThrowArgumentOutOfRange`라는 새 테스트 메서드를 만듭니다.

2. `Debit_WhenAmountIsLessThanZero_ShouldThrowArgumentOutOfRange` 의 메서드 본문을 새 메서드로 복사합니다.

3. `debitAmount` 를 잔액보다 큰 값으로 설정합니다.

**테스트 실행**

두 테스트 메서드를 실행하면 테스트가 올바르게 작동하는지 알 수 있습니다.

**분석 계속 수행**

하지만 마지막 두 테스트 메서드는 문제가 있습니다. 테스트가 실행될 때 테스트 중인 메서드의 어떤 조건이 예외를 throw하는지를 확신할 수 없습니다. 마이너스 차변 금액 또는 잔고보다 큰 금액이라는 두 가지 조건을 구별하는 몇 가지 방법으로 테스트에서 신뢰도를 높일 수 있습니다.

테스트 중인 메서드를 다시 살펴보면 인수 이름을 매개 변수로 받는 `ArgumentOutOfRangeException` 생성자가 두 조건문 모두에 사용된다는 사실을 알 수 있습니다.

```csharp
throw new ArgumentOutOfRangeException("amount");
```

훨씬 많은 정보를 보고하는 데 사용할 수 있는 생성자가 있음: <xref:System.ArgumentOutOfRangeException.%23ctor%2A>`(String, Object, String)`에는 인수 이름, 인수 값 및 사용자 정의 메시지가 포함됩니다. 이 생성자를 사용하도록 테스트 중인 메서드를 리팩터링할 수 있습니다. 더 좋은 점은 공개적으로 사용할 수 있는 형식 멤버를 사용하여 오류를 지정할 수 있다는 점입니다.

**테스트 중인 코드 리팩터링**

먼저 클래스 범위에서 오류 메시지에 대한 두 개 상수를 정의합니다. 다음을 테스트 중인 클래스에 배치합니다(`Bank`).

```csharp
public const string DebitAmountExceedsBalanceMessage = "Debit amount exceeds balance";
public const string DebitAmountLessThanZeroMessage = "Debit amount is less than zero";
```

그런 다음, `Debit` 메서드에서 두 조건문을 수정합니다.

```csharp
    if (amount > m_balance)
    {
        throw new ArgumentOutOfRangeException("amount", amount, DebitAmountExceedsBalanceMessage);
    }

    if (amount < 0)
    {
        throw new ArgumentOutOfRangeException("amount", amount, DebitAmountLessThanZeroMessage);
    }
```

**테스트 메서드 리팩터링**

`ExpectedException` 테스트 메서드 특성을 제거하고 대신, throw된 예외를 catch하며 관련 메시지를 확인합니다. <xref:Microsoft.VisualStudio.TestTools.UnitTesting.StringAssert.Contains%2A?displayProperty=fullName> 메서드는 두 문자열을 비교하는 기능을 제공합니다.

이제 `Debit_WhenAmountIsMoreThanBalance_ShouldThrowArgumentOutOfRange`는 다음과 같습니다.

```csharp
[TestMethod]
public void Debit_WhenAmountIsMoreThanBalance_ShouldThrowArgumentOutOfRange()
{
    // Arrange
    double beginningBalance = 11.99;
    double debitAmount = 20.0;
    BankAccount account = new BankAccount("Mr. Bryan Walton", beginningBalance);

    // Act
    try
    {
        account.Debit(debitAmount);
    }
    catch (ArgumentOutOfRangeException e)
    {
        // Assert
        StringAssert.Contains(e.Message, BankAccount.DebitAmountExceedsBalanceMessage);
    }
}
```

**재테스트, 재작성 및 재분석**

테스트 중인 메서드에 버그가 있다고 가정하고 `Debit` 메서드가 <xref:System.ArgumentOutOfRangeException>을 *throw*하지 않으며 예외와 함께 올바른 메시지를 출력하지 않는 것에 염려하지 마세요. 현재는 테스트 메서드가 이러한 사례를 처리하지 않습니다. `debitAmount` 값이 유효하면(즉, 잔액보다 작지만 0보다 큼) 예외가 catch되지 않으므로 어설션이 절대로 시작되지 않습니다. 그런데도 테스트 메서드를 통과합니다. 예외가 throw되지 않는 경우에도 테스트 메서드가 실패하지 않아야 하므로 이 방법은 좋지 않습니다.

이것은 테스트 메서드의 버그입니다. 문제를 해결하려면 테스트 메서드 끝에 예외가 throw되지 않은 경우를 처리하도록 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.Fail%2A> 어설션을 추가합니다.

하지만 테스트를 다시 실행하여 올바른 예외가 catch되면 테스트가 *실패*한다는 점이 확인되었습니다. `catch` 블록은 예외를 catch하지만 메서드가 계속 실행되고 새로운 <xref:Microsoft.VisualStudio.TestTools.UnitTesting.Assert.Fail%2A> 어설션에서 실패합니다. 이 문제를 해결하려면 `catch` 블록에서 `StringAssert` 다음에 `return`문을 추가합니다. 테스트를 다시 실행하여 이 문제가 수정되었는지 확인합니다. `Debit_WhenAmountIsMoreThanBalance_ShouldThrowArgumentOutOfRange`의 최종 버전은 다음과 같습니다.

```csharp
[TestMethod]
public void Debit_WhenAmountIsMoreThanBalance_ShouldThrowArgumentOutOfRange()
{
    // Arrange
    double beginningBalance = 11.99;
    double debitAmount = 20.0;
    BankAccount account = new BankAccount("Mr. Bryan Walton", beginningBalance);

    // Act
    try
    {
        account.Debit(debitAmount);
    }
    catch (ArgumentOutOfRangeException e)
    {
        // Assert
        StringAssert.Contains(e.Message, BankAccount.DebitAmountExceedsBalanceMessage);
        return;
    }

    Assert.Fail("The expected exception was not thrown.");
}
```

테스트 코드가 개선되어 보다 강력하고 유익한 테스트 메서드가 제공됩니다. 하지만 무엇보다도 중요한 것은 테스트 중인 코드 역시 향상되었다는 점입니다.
