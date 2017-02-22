---
title: "CA1021: out 매개 변수를 사용하지 마십시오. | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CA1021"
  - "AvoidOutParameters"
helpviewer_keywords: 
  - "AvoidOutParameters"
  - "CA1021"
ms.assetid: 970f2304-842c-4fb7-9734-f3871da8d479
caps.latest.revision: 19
caps.handback.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# CA1021: out 매개 변수를 사용하지 마십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|AvoidOutParameters|  
|CheckId|CA1021|  
|범주|Microsoft.Design|  
|변경 수준|주요 변경|  
  
## 원인  
 public 형식의 public 또는 protected 메서드에 `out` 매개 변수가 있습니다.  
  
## 규칙 설명  
 `out` 또는 `ref`를 사용하여 참조로 형식을 전달하려면 포인터를 사용할 수 있고 값 형식과 참조 형식이 어떻게 다른지 알고 있어야 하며 여러 개의 반환 값이 있는 메서드를 처리할 수 있어야 합니다.  또한 `out` 매개 변수와 `ref` 매개 변수의 차이점은 잘 알려져 있지 않습니다.  
  
 참조 형식이 "참조로" 전달된 경우에는 메서드가 매개 변수를 사용하여 개체의 다른 인스턴스를 반환하려는 것입니다.  참조 형식을 참조로 전달하는 것을 이중 포인터, 포인터 대 포인터 또는 이중 간접 참조를 사용한다고도 말합니다.  기본 호출 규칙을 사용하면, 즉 "값으로" 전달하면 참조 형식을 사용하는 매개 변수가 이미 개체에 대한 포인터를 받습니다.  이 경우 가리키는 개체가 아닌 포인터가 값으로 전달됩니다.  값으로 전달된다는 것은 메서드에서 포인터를 참조 형식의 인스턴스를 가리키도록 변경할 수 없음을 의미합니다.  그러나 포인터가 가리키는 개체의 내용은 변경할 수 있습니다.  대부분의 응용 프로그램에서는 이 기능으로도 충분하며 원하는 동작을 만들 수 있습니다.  
  
 메서드에서 다른 인스턴스를 반환해야 하는 경우에는 메서드의 반환 값을 사용하여 이 작업을 수행합니다.  문자열에 대한 작업을 수행하고 문자열의 새 인스턴스를 반환하는 다양한 메서드의 경우에는 <xref:System.String?displayProperty=fullName> 클래스를 참조하십시오.  이 모델을 사용할 경우 호출자가 원래 개체를 보존할 것인지 여부를 결정해야 합니다.  
  
 반환 값은 일반적이며 많이 사용되지만 `out` 및 `ref` 매개 변수를 제대로 적용하려면 중급 수준의 디자인 및 코딩 기술이 필요합니다.  일반 사용자를 대상으로 디자인하는 라이브러리 설계자는 사용자가 `out` 또는 `ref` 매개 변수를 사용하는 작업에 능숙할 것이라고 기대해서는 안 됩니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제가 값 형식 때문에 발생한 경우 이를 해결하려면 메서드가 반환 값으로 개체를 반환하도록 합니다.  메서드에서 여러 개의 값을 반환하면 여러 값을 갖는 개체의 단일 인스턴스를 반환하도록 다시 디자인합니다.  
  
 이 규칙 위반 문제가 참조 형식 때문에 발생한 경우 이를 해결하려면 참조의 새 인스턴스를 반환하는 것이 원하는 동작인지 확인합니다.  그럴 경우 메서드에서 반환 값을 사용하여 이 동작을 수행하도록 합니다.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시하지 않아도 안전합니다.  그러나 이 디자인으로 인해 사용 가능성에 문제가 발생할 수 있습니다.  
  
## 예제  
 다음 라이브러리에서는 사용자의 피드백에 대한 응답을 생성하는 클래스의 두 가지 구현을 보여 줍니다.  첫 번째 구현\(`BadRefAndOut`\)에서는 라이브러리 사용자가 세 가지 반환 값을 관리하도록 합니다.  두 번째 구현\(`RedesignedRefAndOut`\)에서는 데이터를 하나의 단위로 관리하는 컨테이너 클래스의 인스턴스\(`ReplyData`\)를 반환하여 사용자 작업을 간단하게 합니다.  
  
 [!code-cs[FxCop.Design.NoRefOrOut#1](../code-quality/codesnippet/CSharp/ca1021-avoid-out-parameters_1.cs)]  
  
## 예제  
 다음 응용 프로그램에서는 사용자 작업을 보여 줍니다.  다시 디자인한 라이브러리를 호출하는 작업\(`UseTheSimplifiedClass` 메서드\)은 더욱 간단하고 메서드에서 반환된 정보를 관리하기 쉽습니다.  두 메서드의 출력은 동일합니다.  
  
 [!code-cs[FxCop.Design.TestNoRefOrOut#1](../code-quality/codesnippet/CSharp/ca1021-avoid-out-parameters_2.cs)]  
  
## 예제  
 다음 예제 라이브러리에서는 참조 형식에 `ref` 매개 변수를 사용하는 방법을 보여 주고 이 기능을 구현하는 더 좋은 방법을 보여 줍니다.  
  
 [!code-cs[FxCop.Design.RefByRefNo#1](../code-quality/codesnippet/CSharp/ca1021-avoid-out-parameters_3.cs)]  
  
## 예제  
 다음 응용 프로그램에서는 라이브러리의 메서드를 각각 호출하여 해당 동작을 보여 줍니다.  
  
 [!code-cs[FxCop.Design.TestRefByRefNo#1](../code-quality/codesnippet/CSharp/ca1021-avoid-out-parameters_4.cs)]  
  
 이 예제의 결과는 다음과 같습니다.  
  
  **포인터 변경 \- 값에 의해 전달됨:**  
**12345**  
**12345**  
**포인터 변경 \- 참조에 의해 전달됨:**  
**12345**  
**12345 ABCDE**  
**반환 값으로 전달 중:**  
**12345 ABCDE**   
## Try 패턴 메서드  
  
### 설명  
 <xref:System.Int32.TryParse%2A?displayProperty=fullName>와 같이 **Try\<Something\>**패턴을 구현하는 메서드는 이 위반 문제를 발생시키지 않습니다.  다음 예제에서는 <xref:System.Int32.TryParse%2A?displayProperty=fullName>를 구현하는 구조체\(값 형식\)를 보여 줍니다.  
  
### 코드  
 [!code-cs[FxCop.Design.TryPattern#1](../code-quality/codesnippet/CSharp/ca1021-avoid-out-parameters_5.cs)]  
  
## 관련 규칙  
 [CA1045: 참조로 참조 형식을 전달하지 않습니다.](../code-quality/ca1045-do-not-pass-types-by-reference.md)