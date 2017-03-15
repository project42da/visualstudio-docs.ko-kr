---
title: "CA2208: 인수 예외를 올바르게 인스턴스화하십시오. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CA2208"
  - "InstantiateArgumentExceptionsCorrectly"
helpviewer_keywords: 
  - "CA2208"
  - "InstantiateArgumentExceptionsCorrectly"
ms.assetid: e2a48939-d9fa-478c-b2f9-3bdbce07dff7
caps.latest.revision: 19
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 19
---
# CA2208: 인수 예외를 올바르게 인스턴스화하십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|InstantiateArgumentExceptionsCorrectly|  
|CheckId|CA2208|  
|범주|Microsoft.Usage|  
|변경 수준|주요 변경 아님|  
  
## 원인  
 이 오류가 발생하는 원인은 다음과 같습니다.  
  
-   [System.ArgumentException](assetId:///System.ArgumentException?qualifyHint=True&autoUpgrade=True)에서 파생되었거나 예외 형식의 매개 변수가 없는 기본 생성자를 호출한 경우  
  
-   [System.ArgumentException.](assetId:///System.ArgumentException.?qualifyHint=True&autoUpgrade=True)에서 파생되었거나 매개 변수가 있는 예외 형식의 생성자에 잘못된 문자열 인수를 전달한 경우  
  
## 규칙 설명  
 기본 생성자를 호출하는 대신 보다 의미 있는 예외 메시지를 제공하는 생성자 오버로드 중 하나를 호출합니다.  예외 메시지는 개발자를 대상으로 하고 오류 조건과 예외 상황을 해결하거나 방지할 수 있는 방법을 명확하게 설명해야 합니다.  
  
 <xref:System.ArgumentException>과 해당 파생 형식의 문자열 생성자 하나와 두 개에 대한 시그니처는 `message` 및 `paramName` 매개 변수에 있어 일관성이 없습니다.  이러한 생성자가 올바른 문자열 인수를 사용하여 호출되는지 확인하십시오.  시그니처는 다음과 같습니다.  
  
 <xref:System.ArgumentException>\(string `message`\)  
  
 <xref:System.ArgumentException>\(string `message`, string `paramName`\)  
  
 <xref:System.ArgumentNullException>\(string `paramName`\)  
  
 <xref:System.ArgumentNullException>\(string `paramName`, string `message`\)  
  
 <xref:System.ArgumentOutOfRangeException>\(string `paramName`\)  
  
 <xref:System.ArgumentOutOfRangeException>\(string `paramName`, string `message`\)  
  
 <xref:System.DuplicateWaitObjectException>\(string `parameterName`\)  
  
 <xref:System.DuplicateWaitObjectException>\(string `parameterName`, string `message`\)  
  
## 위반 문제를 해결하는 방법  
 이 규칙 위반 문제를 해결하려면 메시지, 매개 변수 이름 또는 이 둘을 모두 사용하는 생성자를 호출하고 호출되는 <xref:System.ArgumentException> 형식에 대해 인수가 적절한지 확인합니다.  
  
## 경고를 표시하지 않는 경우  
 올바른 문자열 인수를 사용하여 매개 변수가 있는 생성자를 호출하는 경우에는 이 규칙에서 경고를 표시하지 않아도 안전합니다.  
  
## 예제  
 다음 예제에서는 ArgumentNullException 형식의 인스턴스를 잘못 인스턴스화하는 생성자를 보여 줍니다.  
  
 [!code-cpp[FxCop.Usage.InstantiateArgumentExceptionsCorrectly#1](../code-quality/codesnippet/CPP/ca2208-instantiate-argument-exceptions-correctly_1.cpp)]
 [!code-cs[FxCop.Usage.InstantiateArgumentExceptionsCorrectly#1](../code-quality/codesnippet/CSharp/ca2208-instantiate-argument-exceptions-correctly_1.cs)]
 [!code-vb[FxCop.Usage.InstantiateArgumentExceptionsCorrectly#1](../code-quality/codesnippet/VisualBasic/ca2208-instantiate-argument-exceptions-correctly_1.vb)]  
  
## 예제  
 다음 예제에서는 생성자 인수를 교체하여 위에 나와 있는 규칙 위반을 해결합니다.  
  
 [!code-cpp[FxCop.Usage.InstantiateArgumentExceptionsCorrectly#2](../code-quality/codesnippet/CPP/ca2208-instantiate-argument-exceptions-correctly_2.cpp)]
 [!code-cs[FxCop.Usage.InstantiateArgumentExceptionsCorrectly#2](../code-quality/codesnippet/CSharp/ca2208-instantiate-argument-exceptions-correctly_2.cs)]
 [!code-vb[FxCop.Usage.InstantiateArgumentExceptionsCorrectly#2](../code-quality/codesnippet/VisualBasic/ca2208-instantiate-argument-exceptions-correctly_2.vb)]