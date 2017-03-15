---
title: "&lt;namespacename&gt; 루트 네임스페이스가 CLS 규격이 아닙니다. | Microsoft Docs"
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
  - "bc40038"
  - "vbc40038"
helpviewer_keywords: 
  - "BC40038"
ms.assetid: ec850295-b2fe-4f19-b808-d22fe0aaa32d
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;namespacename&gt; 루트 네임스페이스가 CLS 규격이 아닙니다.
어셈블리가 `<CLSCompliant(True)>`로 표시되지만 루트 네임스페이스 이름은 밑줄\(`_`\)로 시작합니다.  
  
 프로그래밍 요소가 하나 이상의 밑줄을 포함할 수 있지만 CLS\([언어 독립성 및 언어 독립적 구성 요소](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md)\) 규격이 되려면 밑줄로 시작하지 않아야 합니다.[Declared Element Names](/dotnet/visual-basic/programming-guide/language-features/declared-elements/declared-element-names)을 참조하세요.  
  
 <xref:System.CLSCompliantAttribute>를 프로그래밍 요소에 적용하는 경우 특성의 `isCompliant` 매개 변수를 `True` 또는 `False`로 설정하여 준수 여부를 나타냅니다. 이 매개 변수에는 기본값이 없으며 값을 제공해야 합니다.  
  
 요소에 <xref:System.CLSCompliantAttribute>를 적용하지 않으면 비규격인 것으로 간주됩니다.  
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Visual Basic에서 경고 구성](../ide/configuring-warnings-in-visual-basic.md)을 참조하세요.  
  
 **오류 ID:** BC40038  
  
### 이 오류를 해결하려면  
  
-   CLS 규격이 필요한 경우 밑줄로 시작하지 않도록 루트 네임스페이스 이름을 변경합니다.  
  
-   루트 네임스페이스 이름을 변경하지 않은 상태로 유지해야 하는 경우 어셈블리에서 <xref:System.CLSCompliantAttribute>를 제거하거나 `<CLSCompliant(False)>`로 표시합니다.  
  
## 참고 항목  
 [Namespace Statement](/dotnet/visual-basic/language-reference/statements/namespace-statement)   
 [Visual Basic의 네임스페이스](/dotnet/visual-basic/programming-guide/program-structure/namespaces)   
 [\/rootnamespace](/dotnet/visual-basic/reference/command-line-compiler/rootnamespace)   
 [NIB: 방법: 응용 프로그램\(Visual Basic\)에 대한 네임스페이스를 변경합니다.](http://msdn.microsoft.com/ko-kr/029d85c0-e173-4f7a-afba-a29f3aaf6ebf)   
 [Declared Element Names](/dotnet/visual-basic/programming-guide/language-features/declared-elements/declared-element-names)   
 [Visual Basic Naming Conventions](/dotnet/visual-basic/programming-guide/program-structure/naming-conventions)   
 [\<PAVE OVER\> CLS 규격 코드 작성](http://msdn.microsoft.com/ko-kr/4c705105-69a2-4e5e-b24e-0633bc32c7f3)