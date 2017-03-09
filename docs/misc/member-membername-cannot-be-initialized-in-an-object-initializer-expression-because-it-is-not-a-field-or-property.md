---
title: "&#39;&lt;membername&gt;&#39; 멤버는 필드 또는 속성이 아니므로 개체 이니셜라이저 식에서 초기화할 수 없습니다. | Microsoft Docs"
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
  - "bc30990"
  - "vbc30990"
helpviewer_keywords: 
  - "BC30990"
ms.assetid: 3be2c135-20f6-49b2-a324-d213cfdf9ee3
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;membername&gt;&#39; 멤버는 필드 또는 속성이 아니므로 개체 이니셜라이저 식에서 초기화할 수 없습니다.
개체 이니셜라이저 목록은 공유 멤버, 상수 또는 메서드 호출을 포함할 수 없습니다. 이니셜라이저 목록의 멤버는 필드 또는 속성이어야 하며, 속성 멤버가 인수를 요구할 수 없습니다.  
  
 **오류 ID:** BC30990  
  
### 이 오류를 해결하려면  
  
-   개체 이니셜라이저 목록에서 매개 변수가 있는 모든 공유 멤버, 상수, 메서드 호출 또는 속성을 제거합니다.  
  
## 참고 항목  
 [Object Initializers: Named and Anonymous Types](../Topic/Object%20Initializers:%20Named%20and%20Anonymous%20Types%20\(Visual%20Basic\).md)   
 [빌드에 없음: Visual Basic의 공유 멤버](http://msdn.microsoft.com/ko-kr/dbc3783f-83a2-4225-995d-c2d6d025663d)   
 [빌드에 없음: 속성 및 속성 프로시저](http://msdn.microsoft.com/ko-kr/23e2a1ec-7e9d-4109-8940-c703d981077b)   
 [빌드에 없음: 기본 속성](http://msdn.microsoft.com/ko-kr/a70f2a27-8176-4858-935e-f25afdd43ab5)   
 [NotInBuild:개체 멤버](http://msdn.microsoft.com/ko-kr/dfc2cc12-0e66-44fb-a78e-14f931db2309)   
 [Const Statement](/dotnet/visual-basic/language-reference/statements/const-statement)