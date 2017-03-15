---
title: "네임스페이스 이름 &#39;&lt;namespacename1&gt;&#39;의 대/소문자 표기가 파일 &#39;&lt;filepath&gt;&#39;의 네임스페이스 이름 &#39;&lt;namespacename2&gt;&#39;의 대/소문자 표기와 일치하지 않습니다. | Microsoft Docs"
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
  - "vbc40055"
  - "bc40055"
helpviewer_keywords: 
  - "BC40055"
ms.assetid: adaac2fe-1513-4234-afe7-633a76089f36
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 네임스페이스 이름 &#39;&lt;namespacename1&gt;&#39;의 대/소문자 표기가 파일 &#39;&lt;filepath&gt;&#39;의 네임스페이스 이름 &#39;&lt;namespacename2&gt;&#39;의 대/소문자 표기와 일치하지 않습니다.
프로젝트에서 두 번 이상 나타나는 네임스페이스가 서로 다른 대\/소문자 표기를 사용하고 있습니다.  
  
 *대\/소문자 표기*는 프로그래밍 요소 이름에서 대문자와 소문자의 사용을 의미합니다. Visual Basic은 대\/소문자를 구분하지 않지만 CLR\(공용 언어 런타임\)은 대\/소문자를 구분합니다. 자세한 내용은 [Declared Element Names](/dotnet/visual-basic/programming-guide/language-features/declared-elements/declared-element-names)에 있는 "이름에서 대\/소문자 구분"을 참조하세요.  
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Visual Basic에서 경고 구성](../ide/configuring-warnings-in-visual-basic.md)을 참조하세요.  
  
 **오류 ID:** BC40055  
  
### 이 오류를 해결하려면  
  
-   예방 조치로 네임스페이스를 참조할 때마다 항상 동일한 대\/소문자 표기를 사용합니다. 그러면 공용 언어 런타임에서 잘못 해석하는 것을 방지할 수 있습니다.  
  
## 참고 항목  
 [Namespace Statement](/dotnet/visual-basic/language-reference/statements/namespace-statement)   
 [Visual Basic의 네임스페이스](/dotnet/visual-basic/programming-guide/program-structure/namespaces)   
 [Declared Element Names](/dotnet/visual-basic/programming-guide/language-features/declared-elements/declared-element-names)   
 [Visual Basic Naming Conventions](/dotnet/visual-basic/programming-guide/program-structure/naming-conventions)