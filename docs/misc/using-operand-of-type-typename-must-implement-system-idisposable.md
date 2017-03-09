---
title: "&#39;&lt;typename&gt;&#39; 형식의 &#39;Using&#39; 피연산자는 System.IDisposable을 구현해야 합니다. | Microsoft Docs"
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
  - "vbc36010"
  - "bc36010"
helpviewer_keywords: 
  - "BC36010"
ms.assetid: ae9ed5d5-68ba-4950-bb7a-61327fa0e7d5
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;typename&gt;&#39; 형식의 &#39;Using&#39; 피연산자는 System.IDisposable을 구현해야 합니다.
`Using` 문이 <xref:System.IDisposable> 인터페이스를 구현하지 않는 형식의 리소스를 지정합니다.  
  
 `Using` 블록의 목적은 블록을 종료할 때 시스템 리소스의 삭제를 보장하는 것입니다. 이 목적을 충족하기 위해 리소스가 <xref:System.IDisposable>에서 구현된 <xref:System.IDisposable.Dispose%2A> 메서드를 노출해야 합니다.  
  
 **오류 ID:** BC36010  
  
### 이 오류를 해결하려면  
  
-   `Using` 문의 리소스 목록에서 리소스를 제거하거나 <xref:System.IDisposable>을 구현하는 리소스로 바꿉니다.  
  
## 참고 항목  
 <xref:System.IDisposable>   
 [Using Statement](/dotnet/visual-basic/language-reference/statements/using-statement)   
 [How to: Dispose of a System Resource](../Topic/How%20to:%20Dispose%20of%20a%20System%20Resource%20\(Visual%20Basic\).md)