---
title: "&#39;&lt;keyword&gt;&#39;는 구조체 안에서 사용할 수 없습니다. | Microsoft Docs"
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
  - "bc30044"
  - "vbc30044"
helpviewer_keywords: 
  - "BC30044"
ms.assetid: 252510cf-e084-47e4-9592-4aa8f94fabe4
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;keyword&gt;&#39;는 구조체 안에서 사용할 수 없습니다.
구조체가 참조 형식이 아닌 값 형식입니다. 구조체는 클래스에서 생성되는 인스턴스가 아니므로 `Me`, `MyClass` 및 `MyBase` 키워드는 구조체에서 의미가 없습니다.  
  
 **오류 ID:** BC30044  
  
### 이 오류를 해결하려면  
  
-   구조체를 클래스로 변경하거나 프로시저에서 키워드를 제거합니다.  
  
## 참고 항목  
 [Me](http://msdn.microsoft.com/ko-kr/a65973c7-cf06-4547-9b25-9fba885525c2)   
 [MyClass \- 삭제](http://msdn.microsoft.com/ko-kr/5db36f9b-f796-4b6a-ba34-cac1fde6eb62)   
 [MyBase \- 삭제](http://msdn.microsoft.com/ko-kr/52491d06-6451-4f6f-9aa6-8fab59bbc2b9)   
 [Inheritance Basics](/dotnet/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics)