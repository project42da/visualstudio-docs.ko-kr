---
title: "&#39;&lt;partialtypename&gt;&#39;에 대해 지정된 &lt;accesslevel1&gt; 액세스가 다른 부분 형식 중 하나에서 지정된 &#39;&lt;accesslevel2&gt;&#39; 액세스와 일치하지 않습니다. | Microsoft Docs"
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
  - "vbc30925"
  - "BC30925"
helpviewer_keywords: 
  - "BC30925"
ms.assetid: aabe0f4a-dc02-4828-a837-20cd47a7bd43
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;partialtypename&gt;&#39;에 대해 지정된 &lt;accesslevel1&gt; 액세스가 다른 부분 형식 중 하나에서 지정된 &#39;&lt;accesslevel2&gt;&#39; 액세스와 일치하지 않습니다.
클래스 또는 구조체가 충돌하는 액세스 수준 사양이 있는 여러 partial 선언에 정의되었습니다.  
  
 여러 partial 선언에서 클래스 또는 구조체의 정의를 나눌 때 컴파일러는 형식을 모든 partial 선언의 공용 구조체로 처리합니다. 이는 멤버뿐만 아니라 구현, 상속 및 액세스 수준에도 적용됩니다.  
  
 클래스 또는 구조체 정의에서는 액세스 수준을 혼합할 수 없습니다.`Protected Friend` 조합도 키워드가 같은 선언문에서 연속하는 경우에는 허용됩니다.  
  
 **오류 ID:** BC30925  
  
### 이 오류를 해결하려면  
  
-   클래스의 액세스 수준을 결정하고 충돌하는 액세스 수준 사양을 제거합니다.  
  
## 참고 항목  
 [Partial](/dotnet/visual-basic/language-reference/modifiers/partial)   
 [Access Levels in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/declared-elements/access-levels)   
 [Class Statement](/dotnet/visual-basic/language-reference/statements/class-statement)   
 [Structure Statement](/dotnet/visual-basic/language-reference/statements/structure-statement)   
 [빌드에 없음: 클래스: 개체에 대한 청사진](http://msdn.microsoft.com/ko-kr/2c86373d-0333-4616-a7d8-4790c4e89f7b)   
 [Structures](/dotnet/visual-basic/programming-guide/language-features/data-types/structures)