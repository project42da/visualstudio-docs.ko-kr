---
title: "&#39;MustInherit&#39;은 다른 부분 형식(Partial Type) 중 하나에 지정된 &#39;NotInheritable&#39;과 함께 사용할 수 없으므로 부분 형식 &#39;&lt;partialtypename&gt;&#39;에 대해 지정할 수 없습니다. | Microsoft Docs"
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
  - "vbc30926"
  - "BC30926"
helpviewer_keywords: 
  - "BC30926"
ms.assetid: 59a0b5d9-f53c-4234-88f4-dfc66342f143
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;MustInherit&#39;은 다른 부분 형식(Partial Type) 중 하나에 지정된 &#39;NotInheritable&#39;과 함께 사용할 수 없으므로 부분 형식 &#39;&lt;partialtypename&gt;&#39;에 대해 지정할 수 없습니다.
클래스가 여러 개의 partial 선언, 즉 `MustInherit`를 지정하는 하나의 선언과 `NotInheritable`을 지정하는 또 하나의 선언에서 정의되었습니다.  
  
 여러 partial 선언에서 클래스의 정의를 나눌 때 컴파일러는 클래스를 모든 partial 선언의 공용 구조체로 처리합니다. 이는 멤버뿐만 아니라 구현, 상속 및 액세스 수준에도 적용됩니다.  
  
 한 클래스가 동시에 *abstract*와 *sealed*일 수 없습니다. 이는 상속을 요청하면서 금지할 수 없다는 의미입니다. 따라서 동일한 클래스에 대해 동시에 `MustInherit``NotInheritable`을 지정할 수 없습니다.  
  
 **오류 ID:** BC30926  
  
### 이 오류를 해결하려면  
  
-   클래스가 상속을 요청할지, 상속을 금지할지 아니면 둘 다 하지 않고 결정에 부적절한 키워드를 제거할지 여부를 결정합니다.  
  
## 참고 항목  
 [Partial](/dotnet/visual-basic/language-reference/modifiers/partial)   
 [MustInherit](/dotnet/visual-basic/language-reference/modifiers/mustinherit)   
 [NotInheritable](/dotnet/visual-basic/language-reference/modifiers/notinheritable)   
 [Inheritance Basics](/dotnet/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics)