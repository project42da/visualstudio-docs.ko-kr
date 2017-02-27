---
title: "CA2233: 연산은 오버플로되지 않아야 합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "OperationsShouldNotOverflow"
  - "CA2233"
helpviewer_keywords: 
  - "CA2233"
  - "OperationsShouldNotOverflow"
ms.assetid: 3a2b06ba-6d1b-4666-9eaf-e053ef47ffaa
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 19
---
# CA2233: 연산은 오버플로되지 않아야 합니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|OperationsShouldNotOverflow|  
|CheckId|CA2233|  
|범주|Microsoft.Usage|  
|변경 수준|주요 변경 아님|  
  
## 원인  
 메서드에서 산술 연산을 수행하며 피연산자에 대해 사전에 오버플로를 방지하기 위한 유효성 검사를 수행하지 않습니다.  
  
## 규칙 설명  
 산술 연산을 수행하려면 먼저 피연산자의 유효성을 검사하여 연산의 결과가 관련 데이터 형식의 가능한 값 범위를 벗어나지 않도록 해야 합니다.  실행 컨텍스트와 관련 데이터 형식에 따라 산술 오버플로로 인해 <xref:System.OverflowException?displayProperty=fullName>이 발생하거나 결과 값의 최상위 비트가 삭제될 수 있습니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 연산을 수행하기 전에 피연산자의 유효성을 검사합니다.  
  
## 경고를 표시하지 않는 경우  
 피연산자의 가능한 값이 산술 연산 오버플로를 일으키지 않는 경우에는 이 규칙에서 경고를 표시하지 않도록 설정해도 안전합니다.  
  
## 규칙 위반 예  
  
### 설명  
 다음 예제의 메서드는 이 규칙을 위반하는 정수를 조작합니다.  [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]에서 이 예제가 실행되도록 하려면 정수 오버플로 **해제** 옵션을 사용하지 않도록 설정해야 합니다.  
  
### 코드  
 [!code-vb[FxCop.Usage.OperationOverflow#1](../code-quality/codesnippet/VisualBasic/ca2233-operations-should-not-overflow_1.vb)]
 [!code-cs[FxCop.Usage.OperationOverflow#1](../code-quality/codesnippet/CSharp/ca2233-operations-should-not-overflow_1.cs)]  
  
### 설명  
 이 예제의 메서드가 <xref:System.Int32.MinValue?displayProperty=fullName>에 전달되면 연산이 언더플로됩니다.  이 경우 결과의 최상위 비트가 삭제됩니다.  다음 코드에서는 이러한 작업이 수행되는 방식을 보여 줍니다.  
  
 \[C\#\]  
  
```  
public static void Main()  
{  
    int value = int.MinValue;    // int.MinValue is -2147483648   
    value = Calculator.Decrement(value);   
    Console.WriteLine(value);  
}  
```  
  
 \[VB\]  
  
```  
Public Shared Sub Main()       
    Dim value = Integer.MinValue    ' Integer.MinValue is -2147483648   
    value = Calculator.Decrement(value)   
    Console.WriteLine(value)   
End Sub  
```  
  
### Output  
  
```  
2147483647  
```  
  
## 입력 매개 변수 유효성 검사를 사용한 해결 방법  
  
### 설명  
 다음 예제에서는 입력 값의 유효성을 검사하여 앞의 위반 문제를 해결합니다.  
  
### 코드  
 [!code-cs[FxCop.Usage.OperationOverflowFixed#1](../code-quality/codesnippet/CSharp/ca2233-operations-should-not-overflow_2.cs)]
 [!code-vb[FxCop.Usage.OperationOverflowFixed#1](../code-quality/codesnippet/VisualBasic/ca2233-operations-should-not-overflow_2.vb)]  
  
## 검사된 블록을 사용한 해결 방법  
  
### 설명  
 다음 예제에서는 연산을 검사된 블록에 래핑하여 앞의 위반 문제를 해결합니다.  연산에서 오버플로가 발생하면 <xref:System.OverflowException?displayProperty=fullName>이 throw됩니다.  
  
 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]에서는 검사된 블록이 지원되지 않습니다.  
  
### 코드  
 [!code-cs[FxCop.Usage.OperationOverflowChecked#1](../code-quality/codesnippet/CSharp/ca2233-operations-should-not-overflow_3.cs)]  
  
## 확인된 산술 연산 오버플로\/언더플로 설정  
 C\#에서 확인된 산술 연산 오버플로\/언더플로를 설정할 경우 이는 모든 정수 연산을 검사된 블록에 래핑하는 것과 같습니다.  
  
 **C\#에서 확인된 산술 연산 오버플로\/언더플로를 설정하려면**  
  
1.  **솔루션 탐색기**에서 프로젝트를 마우스 오른쪽 단추로 클릭하고 **속성**을 선택합니다.  
  
2.  **빌드** 탭을 선택하고 **고급**을 클릭합니다.  
  
3.  **산술 연산 오버플로\/언더플로 확인**을 선택하고 **확인**을 클릭합니다.  
  
## 참고 항목  
 <xref:System.OverflowException?displayProperty=fullName>   
 [C\# 연산자](/dotnet/csharp/language-reference/operators/index)   
 [Checked 및 Unchecked](/dotnet/csharp/language-reference/keywords/checked-and-unchecked)