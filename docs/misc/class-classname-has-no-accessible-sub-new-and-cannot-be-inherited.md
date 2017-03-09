---
title: "&#39;&lt;classname&gt;&#39; 클래스에 액세스 가능한 &#39;Sub New&#39;가 없으므로 상속할 수 없습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc31399"
  - "BC31399"
helpviewer_keywords: 
  - "BC31399"
ms.assetid: 035b333f-ff6a-4fc4-bd36-82f40b1d8bab
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;classname&gt;&#39; 클래스에 액세스 가능한 &#39;Sub New&#39;가 없으므로 상속할 수 없습니다.
클래스가 [Inherits Statement](/dotnet/visual-basic/language-reference/statements/inherits-statement)을 사용하여 기본 클래스를 지정하지만 원하는 기본 클래스의 생성자에 액세스할 수 없습니다.  
  
 이 오류는 원하는 기본 클래스에 생성자가 없거나, 다른 클래스에서 액세스할 수 없도록 하는 액세스 수준을 가진 생성자가 있는 경우에 발생할 수 있습니다.  
  
 클래스를 상속하는 경우 생성자가 [MyBase \- 삭제](http://msdn.microsoft.com/ko-kr/52491d06-6451-4f6f-9aa6-8fab59bbc2b9)를 사용하여 기본 클래스 생성자를 호출해야 합니다. 이 호출을 수행하지 않거나 명시적 생성자를 작성하지 않을 경우 Visual Basic에서 `MyBase.New()`을 호출하는 암시적 생성자를 생성합니다.  
  
 **오류 ID:** BC31399  
  
### 이 오류를 해결하려면  
  
1.  원하는 기본 클래스에 대한 소스를 제어할 수 있는 경우 다른 클래스가 액세스할 수 있도록 생성자 중 하나 이상의 액세스 수준을 변경합니다.  
  
2.  원하는 기본 클래스 생성자의 액세스 수준을 변경할 수 없는 경우 다른 클래스에서 상속하거나 전혀 상속하지 않습니다.  
  
## 참고 항목  
 [Inherits Statement](/dotnet/visual-basic/language-reference/statements/inherits-statement)   
 [Inheritance Basics](/dotnet/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics)   
 [MyBase \- 삭제](http://msdn.microsoft.com/ko-kr/52491d06-6451-4f6f-9aa6-8fab59bbc2b9)   
 [New Operator](/dotnet/visual-basic/language-reference/operators/new-operator)   
 [Access Levels in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/declared-elements/access-levels)