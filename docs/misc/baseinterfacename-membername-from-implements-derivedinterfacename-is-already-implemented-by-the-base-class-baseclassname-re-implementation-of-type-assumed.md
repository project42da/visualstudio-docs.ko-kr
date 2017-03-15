---
title: "&#39;implements &lt;derivedinterfacename&gt;&#39;의 &#39;&lt;baseinterfacename&gt;.&lt;membername&gt;&#39;은 기본 클래스 &#39;&lt;baseclassname&gt;&#39;에 의해 이미 구현되었습니다. &lt;type&gt;을 다시 구현한다고 간주됩니다. | Microsoft Docs"
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
  - "bc42014"
  - "vbc42014"
helpviewer_keywords: 
  - "BC42014"
ms.assetid: 95fff622-5d54-4ec8-90f0-477de1d58687
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;implements &lt;derivedinterfacename&gt;&#39;의 &#39;&lt;baseinterfacename&gt;.&lt;membername&gt;&#39;은 기본 클래스 &#39;&lt;baseclassname&gt;&#39;에 의해 이미 구현되었습니다. &lt;type&gt;을 다시 구현한다고 간주됩니다.
속성, 프로시저 또는 파생 클래스의 이벤트가 기본 클래스의 기본 인터페이스에서 이미 구현된 파생 인터페이스 멤버를 지정하여 `Implements` 절을 사용합니다.  
  
 구현되는 멤버는 기본 인터페이스에서 정의되고 파생 인터페이스에 상속됩니다. 기본 클래스는 직접 기본 인터페이스를 구현합니다. 파생 클래스는 파생 인터페이스를 구현하며 기본 클래스가 멤버를 이미 구현했다는 사실을 쉽게 놓칠 수 있습니다.  
  
 파생 클래스는 기본 클래스에 의해 구현된 인터페이스 멤버를 다시 구현할 수 있습니다. 이는 기본 클래스 구현 재정의와 다릅니다. 자세한 내용은 [Implements](/dotnet/visual-basic/language-reference/statements/implements-clause)을 참조하세요.  
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Visual Basic에서 경고 구성](../ide/configuring-warnings-in-visual-basic.md)을 참조하세요.  
  
 **오류 ID:** BC42014  
  
### 이 오류를 해결하려면  
  
-   인터페이스 멤버를 다시 구현하려는 경우 어떤 조치도 취할 필요가 없습니다.[MyBase \- 삭제](http://msdn.microsoft.com/ko-kr/52491d06-6451-4f6f-9aa6-8fab59bbc2b9) 키워드를 사용하여 기본 클래스 구현에 액세스하지 않는 경우 파생 클래스의 코드가 다시 구현된 멤버에 액세스합니다.  
  
-   인터페이스 멤버를 다시 구현하지 않으려는 경우 속성, 프로시저 또는 이벤트 선언에서 `Implements` 절을 제거합니다.  
  
## 참고 항목  
 [Interfaces](/dotnet/visual-basic/programming-guide/language-features/interfaces/index)   
 [빌드에 없음: Implements 키워드 및 Implements 문](http://msdn.microsoft.com/ko-kr/b96560f7-6413-480f-a1e2-f80253bab5be)