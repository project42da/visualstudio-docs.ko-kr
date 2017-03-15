---
title: "&#39;Using&#39; 리소스 변수 형식은 배열 형식일 수 없습니다. | Microsoft Docs"
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
  - "vbc36012"
  - "bc36012"
helpviewer_keywords: 
  - "BC36012"
ms.assetid: f98c54b0-6ede-48b6-aa31-438664c219f3
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Using&#39; 리소스 변수 형식은 배열 형식일 수 없습니다.
`Using` 문에서 리소스에 대한 배열 변수를 지정합니다.  
  
 <xref:System.Array> 클래스는 <xref:System.IDisposable> 인터페이스를 구현하지 않으므로 `Using` 블록은 배열 리소스에서 <xref:System.IDisposable.Dispose%2A> 메서드를 호출할 수 없습니다.  
  
 **오류 ID:** BC36012  
  
### 이 오류를 해결하려면  
  
-   `Using` 블록에서 다른 형식의 시스템 리소스를 사용합니다.  
  
## 참고 항목  
 [Using Statement](/dotnet/visual-basic/language-reference/statements/using-statement)   
 [How to: Dispose of a System Resource](../Topic/How%20to:%20Dispose%20of%20a%20System%20Resource%20\(Visual%20Basic\).md)   
 [NOTINBUILD Visual Basic의 배열 개요](http://msdn.microsoft.com/ko-kr/ca50e2f2-b4d2-4c57-9169-9abbcc3392d8)