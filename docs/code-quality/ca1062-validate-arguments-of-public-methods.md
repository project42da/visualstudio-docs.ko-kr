---
title: "CA1062: public 메서드의 인수의 유효성을 검사하십시오. | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CA1062"
  - "ValidateArgumentsOfPublicMethods"
  - "Validate arguments of public methods"
helpviewer_keywords: 
  - "CA1062"
  - "ValidateArgumentsOfPublicMethods"
ms.assetid: db1f69ca-68f7-477e-94f3-d135cc5dfcbc
caps.latest.revision: 27
caps.handback.revision: 27
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA1062: public 메서드의 인수의 유효성을 검사하십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|ValidateArgumentsOfPublicMethods|  
|CheckId|CA1062|  
|범주|Microsoft.Design|  
|변경 수준|주요 변경 아님|  
  
## 원인  
 외부에서 볼 수 있는 메서드에서 해당 인수가 `null`\(Visual Basic의 경우 `Nothing`\)인지 여부를 확인하지 않고 참조 인수 중 하나를 역참조합니다.  
  
## 규칙 설명  
 외부에서 볼 수 있는 메서드에 전달되는 모든 참조 인수는 `null`인지 여부를 검사해야 합니다.  적절한 경우 인수가 `null`이면 <xref:System.ArgumentNullException>을 throw합니다.  
  
 공용 또는 보호로 선언되기 때문에 알 수 없는 어셈블리에서 메서드를 호출할 수 있는 경우 메서드의 모든 매개 변수의 유효성을 검사해야 합니다.  메서드가 알려진 어셈블리로만 호출하도록 디자인된 경우 내부 메서드를 만들고 이 모델이 들어 있는 어셈블리에 <xref:System.Runtime.CompilerServices.InternalsVisibleToAttribute> 특성을 적용해야 합니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 각 참조 인수가 `null`인지 확인합니다.  
  
## 경고를 표시하지 않는 경우  
 역참조된 매개 변수가 함수에 있는 다른 메서드 호출에 의해 확인된 경우 이 규칙에서 경고를 표시하지 않을 수 있습니다.  
  
## 예제  
 다음 예제에서는 이 규칙을 위반하는 메서드와 규칙을 충족하는 메서드를 보여 줍니다.  
  
 [!code-cs[FxCop.Design.ValidateArguments#1](../code-quality/codesnippet/CSharp/ca1062-validate-arguments-of-public-methods_1.cs)]
 [!code-cs[FxCop.Design.ValidateArguments#1](../code-quality/codesnippet/CSharp/ca1062-validate-arguments-of-public-methods_1.cs)]
 [!code-vb[FxCop.Design.ValidateArguments#1](../code-quality/codesnippet/VisualBasic/ca1062-validate-arguments-of-public-methods_1.vb)]  
  
## 예제  
 [!INCLUDE[vsprvslong](../code-quality/includes/vsprvslong_md.md)]에서 이 규칙은 유효성을 검사하는 다른 메서드로 매개 변수가 전달되는 경우를 감지할 수 없습니다.  
  
 [!code-cs[FxCop.Design.ValidateArguments#2](../code-quality/codesnippet/CSharp/ca1062-validate-arguments-of-public-methods_2.cs)]
 [!code-cs[FxCop.Design.ValidateArguments#2](../code-quality/codesnippet/CSharp/ca1062-validate-arguments-of-public-methods_2.cs)]
 [!code-vb[FxCop.Design.ValidateArguments#2](../code-quality/codesnippet/VisualBasic/ca1062-validate-arguments-of-public-methods_2.vb)]  
  
## 예제  
 개체를 참조하는 필드 또는 속성을 채우는 복사 생성자는 CA1062 규칙을 위반할 수 있습니다.  복사 생성자에 전달되는 복사된 개체가 `null`\(Visual Basic에서는 `Nothing`\)이 될 수 있기 때문에 위반이 발생합니다.  위반 문제를 해결하려면 정적\(Visual Basic에서는 공유\) 메서드를 사용하여 복사된 개체가 null이 아닌지 확인합니다.  
  
 다음 `Person` 클래스 예제에서 `Person` 복사 생성자에 전달되는 `other` 개체는 `null`일 수 있습니다.  
  
```  
  
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
  
## 예제  
 다음 수정된 `Person` 예제에서 복사 생성자에 전달되는 `PassThroughNonNull` 메서드에서 `other` 개체가 null인지 먼저 확인합니다.  
  
```  
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