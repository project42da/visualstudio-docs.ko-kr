---
title: "&#39;&lt;keyword&gt;&#39;는 클래스 안에서만 사용할 수 있습니다. | Microsoft Docs"
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
  - "bc32002"
  - "vbc32002"
helpviewer_keywords: 
  - "BC32002"
ms.assetid: 773d8d50-abb8-4257-83a5-6e017c199d82
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;keyword&gt;&#39;는 클래스 안에서만 사용할 수 있습니다.
`Me` 또는 `MyClass`와 같은 클래스 관련 키워드가 클래스 정의 외부에서 사용되었습니다.  
  
 **오류 ID:** BC32002  
  
### 이 오류를 해결하려면  
  
-   해당 키워드를 사용하는 코드가 클래스 인스턴스와 관련되는 경우 클래스 구현으로 이동합니다.  
  
-   해당 키워드를 사용하는 코드가 클래스에 적용되지 않는 경우 잘못된 키워드를 제거합니다.  
  
## 참고 항목  
 [Me](http://msdn.microsoft.com/ko-kr/a65973c7-cf06-4547-9b25-9fba885525c2)   
 [MyClass \- 삭제](http://msdn.microsoft.com/ko-kr/5db36f9b-f796-4b6a-ba34-cac1fde6eb62)   
 [Class Statement](/dotnet/visual-basic/language-reference/statements/class-statement)