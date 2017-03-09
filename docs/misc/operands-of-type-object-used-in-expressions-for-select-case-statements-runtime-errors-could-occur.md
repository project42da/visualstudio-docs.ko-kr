---
title: "&#39;Select&#39;, &#39;Case&#39; 문의 식에서 Object 형식의 피연산자를 사용했습니다. 런타임 오류가 발생할 수 있습니다. | Microsoft Docs"
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
  - "vbc42036"
  - "bc42036"
helpviewer_keywords: 
  - "BC42036"
ms.assetid: f11e9c9f-aa66-4eb1-8f49-abf713bef885
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Select&#39;, &#39;Case&#39; 문의 식에서 Object 형식의 피연산자를 사용했습니다. 런타임 오류가 발생할 수 있습니다.
`Select`...`Case` 생성은 하나 이상의 [Object Data Type](/dotnet/visual-basic/language-reference/data-types/object-data-type) 식을 사용합니다.  
  
 변수나 식이 `Object`로 평가되는 경우 컴파일러가 *런타임에 바인딩*을 수행해야 하므로 런타임에 추가 작업이 필요합니다. 또한 응용 프로그램이 잠재적인 런타임 오류에 노출됩니다. 예를 들어 <xref:System.Windows.Forms.Form>을 `Object` 변수에 할당하고 숫자와 비교하려고 하는 경우 Visual Basic에서 <xref:System.Windows.Forms.Form> 개체를 숫자 값으로 변환할 수 없기 때문에 런타임에서 <xref:System.InvalidCastException>을 throw합니다.  
  
 `Select`...`Case` 생성의 식은 모두 같은 데이터 형식 또는 서로 변환할 수 있는 밀접하게 관련된 데이터 형식이어야 합니다. 이는 각 `Case` 문이 `Select`...`Case` 구문의 기반이 되는 테스트 식에 대해 하나 이상의 값을 비교하기 때문입니다.  
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Visual Basic에서 경고 구성](../ide/configuring-warnings-in-visual-basic.md)을 참조하세요.  
  
 **오류 ID:** BC42036  
  
### 이 오류를 해결하려면  
  
-   가능하면 모든 식이 비교 연산자가 정의되는 데이터 형식으로 평가되도록 정렬합니다.  
  
## 참고 항목  
 [Select...Case Statement](/dotnet/visual-basic/language-reference/statements/select-case-statement)   
 [Arithmetic Operators in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/operators-and-expressions/arithmetic-operators)   
 [Comparison Operators in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/operators-and-expressions/comparison-operators)