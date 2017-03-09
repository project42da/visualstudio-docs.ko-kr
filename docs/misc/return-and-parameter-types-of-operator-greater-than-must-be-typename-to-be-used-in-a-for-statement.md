---
title: "&#39;&lt;operator&gt;&#39;의 반환 및 매개 변수 형식은 &#39;For&#39; 문에서 사용할 &#39;&lt;typename&gt;&#39;이어야 합니다. | Microsoft Docs"
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
  - "vbc33039"
  - "bc33039"
helpviewer_keywords: 
  - "BC33039"
ms.assetid: 30e8cfa8-c086-474c-a4f0-ad01d01096e2
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;operator&gt;&#39;의 반환 및 매개 변수 형식은 &#39;For&#39; 문에서 사용할 &#39;&lt;typename&gt;&#39;이어야 합니다.
`For` 루프는 `+` 또는 `-` 연산자를 자체 형식의 반환 값 및 매개 변수로 정의하지 않는 형식의 카운터 변수를 지정합니다.  
  
 카운터 변수는 포함하는 형식에서 완전히 작동하는 더하기\(`+`\) 및 빼기\(`-`\) 연산자를 지원하는 형식이어야 합니다. 즉, 피연산자와 반환 값 모두 카운터 변수의 형식이어야 합니다.  
  
 카운터 변수에 숫자 데이터 형식을 사용하면 `+` 및 `-` 연산자가 포함하는 형식에서 지원됩니다. 사용자 정의 클래스 또는 구조체를 사용하면 두 연산자를 클래스 또는 구조체 형식의 피연산자와 반환 값으로 정의해야 합니다.  
  
 **오류 ID:** BC33039  
  
### 이 오류를 해결하려면  
  
1.  카운터 변수 데이터 형식의 철자가 올바른지 확인합니다.  
  
2.  카운터 변수에 사용자 정의 클래스 또는 구조체를 사용할 경우 클래스 또는 구조체에 완전히 작동하는 `+` 및 `-` 연산자를 정의합니다.  
  
## 참고 항목  
 [For...Next 문](/dotnet/visual-basic/language-reference/statements/for-next-statement)   
 [Operator Procedures](/dotnet/visual-basic/programming-guide/language-features/procedures/operator-procedures)   
 [Operator Statement](/dotnet/visual-basic/language-reference/statements/operator-statement)   
 [How to: Define an Operator](../Topic/How%20to:%20Define%20an%20Operator%20\(Visual%20Basic\).md)   
 [How to: Define a Conversion Operator](../Topic/How%20to:%20Define%20a%20Conversion%20Operator%20\(Visual%20Basic\).md)