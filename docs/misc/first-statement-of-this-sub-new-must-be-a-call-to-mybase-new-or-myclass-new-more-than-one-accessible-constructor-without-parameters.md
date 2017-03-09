---
title: "이 &#39;Sub New&#39;의 첫째 문은 &#39;MyBase.New&#39; 또는 &#39;MyClass.New&#39;에 대한 호출이어야 합니다(매개 변수가 없는 둘 이상의 액세스할 수 있는 생성자). | Microsoft Docs"
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
  - "vbc32038"
  - "bc32038"
helpviewer_keywords: 
  - "BC32038"
ms.assetid: 52e4e9df-a85b-46ae-a0cc-7d8fa377fe95
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 이 &#39;Sub New&#39;의 첫째 문은 &#39;MyBase.New&#39; 또는 &#39;MyClass.New&#39;에 대한 호출이어야 합니다(매개 변수가 없는 둘 이상의 액세스할 수 있는 생성자).
'\<derived\>'의 기본 클래스 '\<base\>'에는 인수 없이 호출할 수 있는 액세스 가능한 'Sub New'가 두 개 이상 있으므로 이 'Sub New'의 첫째 문은 'MyBase.New' 또는 'MyClass.New'에 대한 호출이어야 합니다.  
  
 클래스 생성자에서 기본 클래스 생성자에 대한 호출을 제공하지 않으며 호출할 기본 클래스 생성자를 결정할 수 없으므로 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]에서 암시적 호출을 제공할 수 없습니다.  
  
 **오류 ID:** BC32038  
  
### 이 오류를 해결하려면  
  
-   기본 클래스 생성자 `MyBase.New()`, 또는 `MyClass.New()`나 `Me.New()`를 이 생성자의 첫 번째 줄로 사용하여 이 클래스의 다른 생성자에 대한 호출을 추가합니다.  
  
## 참고 항목  
 [Object Lifetime: How Objects Are Created and Destroyed](../Topic/Object%20Lifetime:%20How%20Objects%20Are%20Created%20and%20Destroyed%20\(Visual%20Basic\).md)   
 [빌드에 없음: 생성자 및 소멸자 사용](http://msdn.microsoft.com/ko-kr/548eebe1-86c4-4377-b2f5-447cb8be3d90)   
 [MyBase \- 삭제](http://msdn.microsoft.com/ko-kr/52491d06-6451-4f6f-9aa6-8fab59bbc2b9)