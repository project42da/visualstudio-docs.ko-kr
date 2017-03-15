---
title: "&#39;&lt;interfacename&gt;&#39; 인터페이스는 다른 인터페이스에서만 상속할 수 있습니다. &lt;message&gt; | Microsoft Docs"
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
  - "vbc30296"
  - "BC30296"
helpviewer_keywords: 
  - "BC30296"
ms.assetid: a5bc1ae2-2083-4e26-b8a4-3c4dd951fd27
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;interfacename&gt;&#39; 인터페이스는 다른 인터페이스에서만 상속할 수 있습니다. &lt;message&gt;
인터페이스 정의의 [Inherits Statement](/dotnet/visual-basic/language-reference/statements/inherits-statement)에서 자체 인터페이스를 지정합니다.  
  
 다른 인터페이스에서 상속된 인터페이스에는 해당 인터페이스의 모든 멤버도 함께 제공되므로 해당 멤버를 다시 정의할 필요가 없습니다. 이렇게 상속된 인터페이스를 *파생 인터페이스*라고 하며 상속한 인터페이스를 *기본 인터페이스*라고 합니다.  
  
 인터페이스에 자체 멤버가 모두 포함되어 있으므로 자체 상속은 의미가 없습니다.  
  
 **오류 ID:** BC30296  
  
### 이 오류를 해결하려면  
  
1.  `Inherits` 문에서 인터페이스 이름의 철자를 확인합니다.  
  
2.  다른 인터페이스에서 상속하지 않으려면 `Inherits` 문을 완전히 제거합니다.  
  
3.  제시된 메시지에서 제안 사항을 확인합니다.  
  
## 참고 항목  
 [빌드에 없음: Visual Basic의 상속](http://msdn.microsoft.com/ko-kr/e5e6e240-ed31-4657-820c-079b7c79313c)   
 [Interfaces](/dotnet/visual-basic/programming-guide/language-features/interfaces/index)