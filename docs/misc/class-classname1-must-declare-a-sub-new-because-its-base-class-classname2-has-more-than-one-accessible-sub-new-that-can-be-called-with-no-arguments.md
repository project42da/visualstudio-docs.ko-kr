---
title: "&#39;&lt;classname1&gt;&#39; 클래스의 기본 클래스 &#39;&lt;classname2&gt;&#39;에는 인수 없이 호출할 수 있는 액세스 가능한 &#39;Sub New&#39;가 두 개 이상 있으므로 &#39;Sub New&#39;를 선언해야 합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc32036"
  - "vbc32036"
helpviewer_keywords: 
  - "BC32036"
ms.assetid: 9b96387e-337e-4b2a-b49f-783c7e13811a
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;classname1&gt;&#39; 클래스의 기본 클래스 &#39;&lt;classname2&gt;&#39;에는 인수 없이 호출할 수 있는 액세스 가능한 &#39;Sub New&#39;가 두 개 이상 있으므로 &#39;Sub New&#39;를 선언해야 합니다.
파생 클래스는 생성자를 선언하지 않으며, 호출할 기본 클래스 생성자를 확인할 수 없으므로 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]에서 생성자를 생성할 수 없습니다.  
  
 파생 클래스가 생성자를 선언하지 않는 경우 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]이 `MyBase.New()`를 호출하는 매개 변수가 없는 암시적 생성자를 생성하려고 합니다. 인수 없이 호출될 수 있는 기본 클래스에 액세스할 수 있는 생성자가 없거나 둘 이상 있는 경우 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]은 암시적 생성자를 생성할 수 없습니다.  
  
 예를 들어 하나의 기본 클래스 생성자에 단일 `Optional` 인수가 있고 다른 기본 클래스 생성자에 단일 `ParamArray` 인수가 있는 경우 이런 상황이 발생할 수 있습니다. 이러한 각 기본 클래스 생성자는 인수 없이 호출할 수 있습니다.  
  
 **오류 ID:** BC32036  
  
### 이 오류를 해결하려면  
  
1.  파생 클래스의 임의 위치에서 하나 이상의 `Sub New` 생성자를 선언하여 구현합니다.  
  
2.  기본 클래스 생성자 `MyBase.New()`에 모든 `Sub New`의 첫 번째 줄로 호출을 추가합니다.  
  
## 참고 항목  
 [Object Lifetime: How Objects Are Created and Destroyed](../Topic/Object%20Lifetime:%20How%20Objects%20Are%20Created%20and%20Destroyed%20\(Visual%20Basic\).md)   
 [빌드에 없음: 생성자 및 소멸자 사용](http://msdn.microsoft.com/ko-kr/548eebe1-86c4-4377-b2f5-447cb8be3d90)   
 [Optional](/dotnet/visual-basic/language-reference/modifiers/optional)   
 [ParamArray](/dotnet/visual-basic/language-reference/modifiers/paramarray)   
 [Optional Parameters](/dotnet/visual-basic/programming-guide/language-features/procedures/optional-parameters)   
 [Parameter Arrays](/dotnet/visual-basic/programming-guide/language-features/procedures/parameter-arrays)