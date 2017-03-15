---
title: "이름이 같은 여러 종류의 멤버가 &lt;type&gt; &#39;&lt;typename&gt;&#39;에 있으므로 &#39;&lt;elementname&gt;&#39;은 모호합니다. | Microsoft Docs"
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
  - "bc31429"
  - "vbc31429"
helpviewer_keywords: 
  - "BC31429"
ms.assetid: fdc92c16-934d-47c0-9c44-332cbd58b73b
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 이름이 같은 여러 종류의 멤버가 &lt;type&gt; &#39;&lt;typename&gt;&#39;에 있으므로 &#39;&lt;elementname&gt;&#39;은 모호합니다.
같은 이름의 멤버 둘 이상이 포함된 클래스, 구조체, 모듈 또는 인터페이스에 정의된 프로그래밍 요소에 식이 액세스합니다.  
  
 이 오류는 대부분 *대\/소문자 구분*으로 인해 발생합니다. Visual Basic 이름은 대\/소문자를 구분하지 않습니다. 즉, 코드의 다른 곳에서 이름의 첫 글자를 대문자로 다르게 바꿀 수 있습니다. 예를 들어 이름 `XYZ`으로 변수를 정의하고 나중에 `xyz`로 액세스하는 경우 컴파일러가 두 이름을 동일한 것으로 간주합니다.  
  
 그러나 [C\#](/dotnet/csharp/csharp) 및 [Visual C\+\+](/visual-cpp/top/visual-cpp-in-visual-studio-2015)와 같은 다른 언어는 대\/소문자를 구분합니다. 이러한 언어에서는 `XYZ`과 `xyz`를 동일한 이름으로 간주하지 않습니다. 따라서 이러한 언어로 작성된 클래스는 `XYZ`로 명명한 변수와 `xyz`로 명명한 속성을 정의할 수 있습니다. CLR\(공용 언어 런타임\)에서는 어셈블리의 대\/소문자 구분을 유지합니다. 그러나 Visual Basic 응용 프로그램이 `XYZ` 및 `xyz` 이름으로 어셈블리에 액세스하는 경우 동일한 이름으로 나타납니다.  
  
 **오류 ID:** BC31429  
  
### 이 오류를 해결하려면  
  
1.  정의 형식의 소스 코드를 제어할 수 있다면 대\/소문자 구분 이외의 방법으로 구별되도록 멤버의 이름을 바꾸는 것이 좋습니다. 정의 형식이 이미 게시되어 다른 응용 프로그램이 사용하고 있는 경우 이렇게 하지 못할 수 있습니다.  
  
2.  정의 형식에서 멤버의 이름을 바꿀 수 없는 경우 코드에서 언급된 프로그래밍 요소를 제거합니다. Visual Basic에 나타나 여러 정의를 갖는 요소에 액세스할 수 없습니다.  
  
## 참고 항목  
 [Declared Element Names](/dotnet/visual-basic/programming-guide/language-features/declared-elements/declared-element-names)   
 [변수 문제 해결](/dotnet/visual-basic/programming-guide/language-features/variables/troubleshooting-variables)   
 [공용 언어 런타임](../Topic/Common%20Language%20Runtime%20\(CLR\).md)