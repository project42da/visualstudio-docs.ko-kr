---
title: "&#39;&lt;typeparametername1&gt;&#39; 형식 매개 변수 이름이 &#39;&lt;partialtypename&gt;&#39;의 다른 부분 형식(Partial Type) 중 하나에 정의된 해당 형식 매개 변수의 이름 &#39;&lt;typeparametername2&gt;&#39;와 일치하지 않습니다. | Microsoft Docs"
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
  - "vbc30931"
  - "bc30931"
helpviewer_keywords: 
  - "BC30931"
ms.assetid: 01b053c3-d1b5-4e69-b908-3d5cfc73913b
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;typeparametername1&gt;&#39; 형식 매개 변수 이름이 &#39;&lt;partialtypename&gt;&#39;의 다른 부분 형식(Partial Type) 중 하나에 정의된 해당 형식 매개 변수의 이름 &#39;&lt;typeparametername2&gt;&#39;와 일치하지 않습니다.
제네릭 클래스 또는 구조체가 충돌하는 형식 매개 변수 사양이 있는 여러 partial 선언에 정의되었습니다.  
  
 여러 partial 선언에서 클래스 또는 구조체의 정의를 나눌 때 컴파일러는 형식을 모든 partial 선언의 공용 구조체로 처리합니다. 이는 멤버뿐만 아니라 구현, 상속 및 액세스 수준에도 적용됩니다.  
  
 제네릭 클래스 또는 구조체 정의에서 형식 매개 변수에 대해 이름을 여러 개 지정할 수 없습니다.  
  
 **오류 ID:** BC30931  
  
### 이 오류를 해결하려면  
  
-   형식 매개 변수의 이름을 결정하고 모든 partial 선언에 동일한 이름을 사용합니다.  
  
## 참고 항목  
 [Partial](/dotnet/visual-basic/language-reference/modifiers/partial)   
 [Class Statement](/dotnet/visual-basic/language-reference/statements/class-statement)   
 [Structure Statement](/dotnet/visual-basic/language-reference/statements/structure-statement)   
 [빌드에 없음: 클래스: 개체에 대한 청사진](http://msdn.microsoft.com/ko-kr/2c86373d-0333-4616-a7d8-4790c4e89f7b)   
 [Structures](/dotnet/visual-basic/programming-guide/language-features/data-types/structures)   
 [Visual Basic의 제네릭 형식](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)   
 [Type List](/dotnet/visual-basic/language-reference/statements/type-list)