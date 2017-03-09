---
title: "&#39;&lt;operator&gt;&#39;의 매개 변수 형식은 &#39;For&#39; 문에서 사용할 &#39;&lt;typename&gt;&#39;이어야 합니다. | Microsoft Docs"
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
  - "BC33040"
  - "vbc33040"
helpviewer_keywords: 
  - "BC33040"
ms.assetid: bffbb812-0d69-47e4-96c5-01882722ccdb
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;operator&gt;&#39;의 매개 변수 형식은 &#39;For&#39; 문에서 사용할 &#39;&lt;typename&gt;&#39;이어야 합니다.
`For` 루프는 `>=` 또는 `<=` 연산자를 자체 형식의 매개 변수로 정의하지 않는 형식의 카운터 변수를 지정합니다.  
  
 카운터 변수는 포함하는 형식을 비교하는 크거나 같음\(`>=`\) 및 작거나 같음\(`<=`\) 연산자를 지원하는 형식이어야 합니다. 즉, 두 피연산자 모두 카운터 변수의 형식이어야 합니다.  
  
 카운터 변수에 숫자 데이터 형식을 사용하면 `>=` 및 `<=` 연산자가 포함하는 형식에서 지원됩니다. 사용자 정의 클래스 또는 구조체를 사용하면 두 연산자를 클래스 또는 구조체 형식의 피연산자로 정의해야 합니다.  
  
 **오류 ID:** BC33040  
  
### 이 오류를 해결하려면  
  
1.  카운터 변수 데이터 형식의 철자가 올바른지 확인합니다.  
  
2.  카운터 변수에 사용자 정의 클래스 또는 구조체를 사용할 경우 해당 클래스 또는 구조체를 비교하는 `>=` 및 `<=` 연산자를 정의합니다.  
  
## 참고 항목  
 [For...Next 문](/dotnet/visual-basic/language-reference/statements/for-next-statement)   
 [Operator Procedures](/dotnet/visual-basic/programming-guide/language-features/procedures/operator-procedures)   
 [Operator Statement](/dotnet/visual-basic/language-reference/statements/operator-statement)   
 [How to: Define an Operator](../Topic/How%20to:%20Define%20an%20Operator%20\(Visual%20Basic\).md)   
 [How to: Define a Conversion Operator](../Topic/How%20to:%20Define%20a%20Conversion%20Operator%20\(Visual%20Basic\).md)