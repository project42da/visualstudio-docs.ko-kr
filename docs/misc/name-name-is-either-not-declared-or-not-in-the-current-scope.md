---
title: "&#39;&lt;name&gt;&#39; 이름이 선언되지 않았거나 현재 범위에 없습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc36610"
  - "bc36610"
helpviewer_keywords: 
  - "BC36610"
ms.assetid: e66a4b8a-9252-42ae-a30d-341fad4f74be
caps.latest.revision: 4
caps.handback.revision: 4
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;name&gt;&#39; 이름이 선언되지 않았거나 현재 범위에 없습니다.
LINQ 쿼리는 프로그래밍 요소를 참조하지만 컴파일러에서 정확한 해당 이름이 있는 요소를 찾을 수 없습니다.  
  
 **오류 ID:** BC36610  
  
### 이 오류를 해결하려면  
  
1.  참조하는 문에서 이름의 철자를 검사합니다.[!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)]는 대\/소문자를 구분하지 않지만 철자를 변형하면 다른 이름이 구성됩니다. 밑줄\(`_`\)은 이름의 일부이므로 철자의 일부입니다.  
  
2.  프로그래밍 요소가 범위에 있는지 확인합니다. 참조하는 문이 프로그래밍 요소를 선언하는 영역을 벗어날 경우 요소 이름을 한정해야 할 수도 있습니다. 자세한 내용은 [Scope in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/declared-elements/scope)을 참조하세요.  
  
3.  멤버 액세스 연산자\(`.`\)는 개체와 해당 멤버 사이에 있어야 합니다. 예를 들어 `TextBox1`이라는 <xref:System.Windows.Forms.TextBox> 컨트롤이 있는 경우 해당 <xref:System.Windows.Forms.TextBoxBase.Text%2A> 속성에 액세스하려면 `TextBox1.Text`를 입력해야 합니다.`TextBox1Text`를 대신 입력하면 다른 이름이 만들어집니다.  
  
## 참고 항목  
 [Introduction to LINQ in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/linq/introduction-to-linq)   
 [Visual Basic Naming Conventions](/dotnet/visual-basic/programming-guide/program-structure/naming-conventions)   
 [References to Declared Elements](/dotnet/visual-basic/programming-guide/language-features/declared-elements/references-to-declared-elements)