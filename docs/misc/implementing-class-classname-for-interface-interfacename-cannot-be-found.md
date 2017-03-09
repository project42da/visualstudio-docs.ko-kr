---
title: "&lt;interfacename&gt; 인터페이스에 대한 &#39;&lt;classname&gt;&#39; 클래스 구현을 찾을 수 없습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc31094"
  - "bc31094"
helpviewer_keywords: 
  - "BC31094"
ms.assetid: 262cb67e-2930-4a4a-a63e-bb2e201b3b93
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;interfacename&gt; 인터페이스에 대한 &#39;&lt;classname&gt;&#39; 클래스 구현을 찾을 수 없습니다.
Interop 어셈블리의 구현하는 클래스를 사용할 수 없습니다.  
  
 **오류 ID:** BC31094  
  
### 이 오류를 해결하려면  
  
1.  COM 개체에 대한 형식 라이브러리가 올바른지 확인합니다.  
  
2.  형식 라이브러리 가져오기 도구\(Tlbimp.exe\)를 사용하여 Interop 어셈블리를 수동으로 만든 다음 프로젝트의 해당 interop 어셈블리에 참조를 추가합니다.  
  
## 참고 항목  
 [Implements Statement](/dotnet/visual-basic/language-reference/statements/implements-statement)   
 [COM Interop](/dotnet/visual-basic/programming-guide/com-interop/index)   
 [Tlbimp.exe\(형식 라이브러리 가져오기\)](../Topic/Tlbimp.exe%20\(Type%20Library%20Importer\).md)