---
title: "&#39;&lt;classname&gt;&#39; 클래스는 자체 클래스에서 상속할 수 없습니다. &lt;message&gt; | Microsoft Docs"
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
  - "vbc30257"
  - "bc30257"
helpviewer_keywords: 
  - "BC30257"
ms.assetid: 03e3034c-a0fa-4619-84b9-5bc9aa0dfe80
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;classname&gt;&#39; 클래스는 자체 클래스에서 상속할 수 없습니다. &lt;message&gt;
클래스 정의의 [Inherits Statement](/dotnet/visual-basic/language-reference/statements/inherits-statement)에서 자체 클래스를 지정합니다.  
  
 다른 클래스에서 상속하는 클래스에는 해당 클래스의 모든 멤버도 함께 제공되므로 해당 멤버를 다시 정의할 필요가 없습니다. 이렇게 상속된 클래스를 *파생 클래스*라고 하며 상속한 클래스를 *기본 클래스*라고 합니다.  
  
 클래스에 자체 멤버가 모두 포함되어 있으므로 자체 상속은 의미가 없습니다.  
  
 **오류 ID:** BC30257  
  
### 이 오류를 해결하려면  
  
1.  `Inherits` 문에서 클래스 이름의 철자를 확인합니다.  
  
2.  다른 클래스에서 상속하지 않으려면 `Inherits` 문을 완전히 제거합니다.  
  
3.  제시된 메시지에서 제안 사항을 확인합니다.  
  
## 참고 항목  
 [빌드에 없음: Visual Basic의 상속](http://msdn.microsoft.com/ko-kr/e5e6e240-ed31-4657-820c-079b7c79313c)   
 [빌드에 없음: 클래스 이해](http://msdn.microsoft.com/ko-kr/cc2355a2-cb98-4353-9440-736585aec46c)