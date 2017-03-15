---
title: "&#39;System.Nullable&#39;은 형식 매개 변수 &#39;&lt;typeparametername&gt;&#39;에 대한 &#39;Structure&#39; 제약 조건을 만족하지 않습니다. | Microsoft Docs"
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
  - "bc32115"
  - "vbc32115"
helpviewer_keywords: 
  - "BC32115"
ms.assetid: 98053645-fa76-4826-a7c1-f1bdf3511863
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;System.Nullable&#39;은 형식 매개 변수 &#39;&lt;typeparametername&gt;&#39;에 대한 &#39;Structure&#39; 제약 조건을 만족하지 않습니다.
`Structure` 제약 조건이 있는 형식 매개 변수에 <xref:System.Nullable%601>의 형식 인수를 전달하여 제네릭 형식을 호출합니다.  
  
 CLR\(공용 언어 런타임\)에서는 <xref:System.Nullable%601> 구조체를 자체의 형식 인수로 사용할 수 없습니다. 구조체이고 `Structure` 제약 조건을 만족하는 경우에도 재귀적으로 사용하면 `Nullable(Of Nullable(Of Nullable))`과 같은 잘못된 구문이 생성됩니다.  
  
 **오류 ID:** BC32115  
  
### 이 오류를 해결하려면  
  
-   형식 매개 변수에서 `Structure` 제약 조건을 제거하거나 형식 인수를 <xref:System.Nullable%601> 이외의 다른 값 형식으로 변경합니다.  
  
## 참고 항목  
 <xref:System.Nullable%601>   
 [Visual Basic의 제네릭 형식](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)   
 [구조체\(Visual Basic\)](http://msdn.microsoft.com/ko-kr/263ce115-ac36-4c05-8cb7-0e0eead5c6d0)