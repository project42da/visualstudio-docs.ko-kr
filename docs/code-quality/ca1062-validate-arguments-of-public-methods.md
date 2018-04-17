---
title: 'CA1062: public 메서드의 인수의 유효성을 검사 | Microsoft Docs'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-code-analysis
ms.topic: conceptual
f1_keywords:
- CA1062
- ValidateArgumentsOfPublicMethods
- Validate arguments of public methods
helpviewer_keywords:
- CA1062
- ValidateArgumentsOfPublicMethods
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 6a14017c63c9012609f91005378f44a5e4a8401e
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="ca1062-validate-arguments-of-public-methods"></a>CA1062: public 메서드의 인수의 유효성을 검사하십시오.

|||
|-|-|
|TypeName|ValidateArgumentsOfPublicMethods|
|CheckId|CA1062|
|범주|Microsoft.Design|
|변경 수준|주요 변경 아님|

## <a name="cause"></a>원인

외부에 표시 되는 메서드는 참조 인수 중 하나를 해당 인수 인지 확인 하지 않고 역참조 `null` (`Nothing` Visual basic에서).

## <a name="rule-description"></a>규칙 설명

외부에서 볼 수 있는 메서드에 전달 되는 모든 참조 인수를 검사 해야 `null`합니다. 필요한 경우 throw 한 <xref:System.ArgumentNullException> 인수가 때 `null`합니다.

메서드를 호출할 수 알 수 없는 어셈블리에서 public 또는 protected로 선언 되었으므로 메서드의 모든 매개 변수 유효성을 검사 해야 합니다. 내부 메서드를 확인 하 고 적용 해야 알려진된 어셈블리에 의해서만 호출 될 반환 하는 경우는 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 메서드를 포함 하는 어셈블리에 대 한 특성입니다.

## <a name="how-to-fix-violations"></a>위반 문제를 해결하는 방법

이 규칙 위반 문제를 해결 하려면 각 참조 인수에 대해 유효성을 검사 `null`합니다.

## <a name="when-to-suppress-warnings"></a>경고를 표시하지 않는 경우

역참조 매개 변수는 함수에서 다른 메서드 호출 검증 된 확신 하는 경우이 규칙에서는 경고를에서 억제할 수 있습니다.

## <a name="example"></a>예제

다음 예제에서는 규칙을 위반 하는 메서드 및 규칙을 충족 하는 메서드를 보여 줍니다.

 ```csharp
 using System;

namespace DesignLibrary
{
    public class Test
    {
        // This method violates the rule.
        public void DoNotValidate(string input)
        {
            if (input.Length != 0)
            {
                Console.WriteLine(input);
            }
        }

        // This method satisfies the rule.
        public void Validate(string input)
        {
            if (input == null)
            {
                throw new ArgumentNullException("input");
            }
            if (input.Length != 0)
            {
                Console.WriteLine(input);
            }
        }
    }
}
```

```vb
Imports System

Namespace DesignLibrary

    Public Class Test

        ' This method violates the rule.
        Sub DoNotValidate(ByVal input As String)

            If input.Length <> 0 Then
                Console.WriteLine(input)
            End If

        End Sub

        ' This method satisfies the rule.
        Sub Validate(ByVal input As String)

            If input Is Nothing Then
                Throw New ArgumentNullException("input")
            End If

            If input.Length <> 0 Then
                Console.WriteLine(input)
            End If

        End Sub

    End Class

End Namespace
```

## <a name="example"></a>예제

개체를 참조 하는 필드 또는 속성을 채우는 복사 생성자는 CA1062 규칙을 위반할 수 있습니다. 복사 생성자에 전달 되는 복사 된 개체 수 있기 때문에 위반이 발생 `null` (`Nothing` Visual basic에서). 위반을 해결 하려면 정적 (Visual Basic의 경우 Shared) 메서드를 사용 하 여 복사한 개체 null 인지 확인 합니다.

다음에서 `Person` 클래스 예제는 `other` 에 전달 되는 개체는 `Person` 복사 생성자 수도 `null`합니다.

```csharp
public class Person
{
    public string Name { get; private set; }
    public int Age { get; private set; }

    public Person(string name, int age)
    {
        Name = name;
        Age = age;
    }

    // Copy constructor CA1062 fires because other is dereferenced
    // without being checked for null
    public Person(Person other)
        : this(other.Name, other.Age)
    {
    }
}
```

## <a name="example"></a>예제

다음 수정 된 `Person` 예제에서는 `other` 에서 null에 대 한 복사 생성자에 전달 되는 개체를 먼저 검사는 `PassThroughNonNull` 메서드.

```csharp
public class Person
{
    public string Name { get; private set; }
    public int Age { get; private set; }

    public Person(string name, int age)
    {
        Name = name;
        Age = age;
    }

    // Copy constructor
    public Person(Person other)
        : this(PassThroughNonNull(other).Name,
          PassThroughNonNull(other).Age)
    {
    }

    // Null check method
    private static Person PassThroughNonNull(Person person)
    {
        if (person == null)
            throw new ArgumentNullException("person");
        return person;
    }
}

```