---
title: "&#39;MyClass&#39; 뒤에는 &#39;.&#39;과 식별자가 와야 합니다. | Microsoft Docs"
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
  - "bc32028"
  - "vbc32028"
helpviewer_keywords: 
  - "BC32028"
ms.assetid: a7e92b54-32b8-4072-9576-632942f05e0f
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;MyClass&#39; 뒤에는 &#39;.&#39;과 식별자가 와야 합니다.
`MyClass`는 진정한 개체 변수가 아니며 단독으로 사용될 수 없습니다. 기본 클래스의 `NotOverridable`처럼 현재 인스턴스의 멤버를 액세스하는 데만 사용됩니다.  
  
 **오류 ID:** BC32028  
  
### 이 오류를 해결하려면  
  
1.  클래스 멤버에 액세스하려는 경우 `MyClass` 뒤에 멤버 액세스 연산자\(`.`\) 및 현재 인스턴스의 멤버를 지정합니다.  
  
2.  클래스 멤버에 액세스하지 않으려는 경우 `Me` 키워드를 사용합니다.  
  
## 참고 항목  
 [MyClass \- 삭제](http://msdn.microsoft.com/ko-kr/5db36f9b-f796-4b6a-ba34-cac1fde6eb62)   
 [Me](http://msdn.microsoft.com/ko-kr/a65973c7-cf06-4547-9b25-9fba885525c2)   
 [NotOverridable](/dotnet/visual-basic/language-reference/modifiers/notoverridable)   
 [Inheritance Basics](/dotnet/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics)