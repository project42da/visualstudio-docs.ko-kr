---
title: "&#39;&lt;operatorsymbol&gt; 연산자에 대해 Object 형식의 피연산자를 사용했습니다. 런타임 오류가 발생할 수 있습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "BC42019"
  - "vbc42019"
helpviewer_keywords: 
  - "BC42019"
ms.assetid: f61944ba-863b-4a82-aae4-249bda52ec8d
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;operatorsymbol&gt; 연산자에 대해 Object 형식의 피연산자를 사용했습니다. 런타임 오류가 발생할 수 있습니다.
식이 하나 또는 두 피연산자가 모두 [Object Data Type](/dotnet/visual-basic/language-reference/data-types/object-data-type)인 연산자를 사용합니다.  
  
 변수나 식이 `Object`로 평가되는 경우 컴파일러가 *런타임에 바인딩*을 수행해야 하므로 런타임에 추가 작업이 필요합니다. 또한 응용 프로그램이 잠재적인 런타임 오류에 노출됩니다. 예를 들어 <xref:System.Windows.Forms.Form>을 `Object` 변수에 할당한 다음 [\/ Operator](/dotnet/visual-basic/language-reference/operators/floating-point-division-operator)에서 사용한다고 가정합니다. 이렇게 하는 경우 Visual Basic이 <xref:System.Windows.Forms.Form> 개체를 숫자 값으로 변환할 수 없기 때문에 런타임에서<xref:System.InvalidCastException>을 throw합니다.  
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Visual Basic에서 경고 구성](../ide/configuring-warnings-in-visual-basic.md)을 참조하세요.  
  
 **오류 ID:** BC42019  
  
### 이 오류를 해결하려면  
  
-   가능하면 연산자가 정의된 데이터 형식으로 계산되도록 피연산자를 정렬합니다.  
  
## 참고 항목  
 [Arithmetic Operators in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators)