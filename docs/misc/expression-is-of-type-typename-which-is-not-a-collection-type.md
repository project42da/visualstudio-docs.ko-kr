---
title: "식의 형식이 컬렉션 형식이 아닌 &#39;&lt;typename&gt;&#39;입니다. | Microsoft Docs"
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
  - "bc32023"
  - "vbc32023"
helpviewer_keywords: 
  - "BC32023"
ms.assetid: d0f151be-6b65-498b-b571-03faf24df0d8
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 식의 형식이 컬렉션 형식이 아닌 &#39;&lt;typename&gt;&#39;입니다.
`For Each` 문에 지정된 그룹 변수는 컬렉션 개체 또는 배열이 아니며, 해당 형식이 <xref:System.Collections.IEnumerable> 인터페이스를 구현하지 않습니다. 형식이 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 컬렉션 디자인 패턴을 지원하거나 <xref:System.Collections.IEnumerable>을 구현해야 합니다.  
  
 **오류 ID:** BC32023  
  
### 이 오류를 해결하려면  
  
-   [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 컬렉션 디자인을 지원하거나 <xref:System.Collections.IEnumerable>을 구현하는 클래스 형식으로 그룹 변수를 선언합니다.  
  
## 참고 항목  
 <xref:System.Collections.IEnumerable>   
 [For Each...Next 문](/dotnet/visual-basic/language-reference/statements/for-each-next-statement)   
 [Visual Basic 컬렉션 클래스](http://msdn.microsoft.com/ko-kr/0cb2d1ad-c58d-42c0-8e69-d81f5a15e532)