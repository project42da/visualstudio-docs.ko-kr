---
title: "포함하는 연산자 &#39;&lt;operatorsymbol&gt;&#39;을 식이 재귀적으로 호출합니다. | Microsoft Docs"
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
  - "BC42004"
  - "vbc42004"
helpviewer_keywords: 
  - "BC42004"
ms.assetid: a874c44a-3aec-447d-90f7-5659f1b2f5f6
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 포함하는 연산자 &#39;&lt;operatorsymbol&gt;&#39;을 식이 재귀적으로 호출합니다.
연산자 프로시저 내의 식이 정의 중인 연산자를 사용합니다. 그 결과 데이터 형식이 사용 중이기 때문에 연산자 프로시저가 자신을 호출합니다.  
  
 다음 중 하나와 동일한 연산자를 사용하는 경우 정의 중인 연산자 프로시저가 자신을 호출합니다.  
  
-   연산자를 정의 중인 동일한 피연산자  
  
-   연산자를 정의 중인 것과 동일한 데이터 형식의 피연산자  
  
-   연산자를 정의 중인 데이터 형식으로 확장된 데이터 형식의 피연산자  
  
 *재귀적 호출*은 프로시저가 자신을 호출하는 것입니다. 재귀적 호출은 응용 프로그램이 외부적으로 종료될 때까지 컨트롤이 반복적으로 동일한 문 집합을 통과하는 *무한 루프*를 발생시킬 수 있습니다. 코드에 재귀를 종료하는 데 사용할 수 있는 테스트가 하나 이상 포함되지 않은 경우 무한 루프가 발생할 수 있습니다.  
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Visual Basic에서 경고 구성](../ide/configuring-warnings-in-visual-basic.md)을 참조하세요.  
  
 **오류 ID:** BC42004  
  
### 이 오류를 해결하려면  
  
-   논리에 따라 연산자 프로시저가 자신을 호출해야 하는 경우 일부 지점에서 반드시 발생하는 조건을 하나 이상 테스트하고 이 테스트를 사용하여 재귀 호출을 종료합니다.  
  
-   논리에 따라 연산자 프로시저가 자신을 호출할 필요가 없는 경우 재귀적 호출을 모두 제거하거나 자체 프로시저를 호출하지 않는 문으로 바꿉니다.  
  
## 참고 항목  
 [Operator Procedures](/dotnet/visual-basic/programming-guide/language-features/procedures/operator-procedures)   
 [Operator Statement](/dotnet/visual-basic/language-reference/statements/operator-statement)   
 [How to: Define an Operator](../Topic/How%20to:%20Define%20an%20Operator%20\(Visual%20Basic\).md)   
 [How to: Define a Conversion Operator](../Topic/How%20to:%20Define%20a%20Conversion%20Operator%20\(Visual%20Basic\).md)