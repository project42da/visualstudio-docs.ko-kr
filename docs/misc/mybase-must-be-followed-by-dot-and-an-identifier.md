---
title: "&#39;MyBase&#39; 뒤에는 &#39;.&#39;와 식별자가 와야 합니다. | Microsoft Docs"
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
  - "bc32027"
  - "vbc32027"
helpviewer_keywords: 
  - "BC32027"
ms.assetid: 39e5512c-ef1e-46a3-a96c-277ea24bfee2
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;MyBase&#39; 뒤에는 &#39;.&#39;와 식별자가 와야 합니다.
`MyBase`는 진정한 개체 변수가 아니며 단독으로 사용될 수 없습니다. 현재 인스턴스의 기본 클래스 멤버에 액세스하는 데만 사용됩니다.  
  
 **오류 ID:** BC32027  
  
### 이 오류를 해결하려면  
  
-   멤버 액세스 권한을 부여하려는 경우 멤버 액세스 연산자\(.\) 및 기본 클래스의 멤버를 `MyBase` 뒤에 지정합니다.  
  
-   멤버 액세스 권한을 부여하지 않으려는 경우 기본 클래스의 인스턴스를 선언 및 초기화하거나 `MyBase`에 대한 참조를 제거합니다.  
  
## 참고 항목  
 [MyBase \- 삭제](http://msdn.microsoft.com/ko-kr/52491d06-6451-4f6f-9aa6-8fab59bbc2b9)   
 [Inheritance Basics](/dotnet/visual-basic/programming-guide/language-features/objects-and-classes/inheritance-basics)