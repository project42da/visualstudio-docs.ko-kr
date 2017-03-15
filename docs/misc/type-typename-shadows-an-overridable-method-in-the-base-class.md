---
title: "&lt;type&gt; &#39;&lt;typename&gt;&#39;이 기본 클래스의 재정의 가능 메서드를 섀도 처리합니다. | Microsoft Docs"
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
  - "vbc40005"
  - "bc40005"
helpviewer_keywords: 
  - "BC40005"
ms.assetid: 1dadda7f-1d26-4ae8-a668-9f69d55ceb50
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;type&gt; &#39;&lt;typename&gt;&#39;이 기본 클래스의 재정의 가능 메서드를 섀도 처리합니다.
\<type\> '\<typename\>'이 기본 클래스의 재정의 가능 메서드를 섀도 처리합니다. 기본 메서드를 재정의하려면 이 메서드를 'Overrides'로 선언해야 합니다.  
  
 프로그래밍 요소가 기본 클래스에 정의된 속성 또는 재정의 가능한 프로시저와 같은 이름을 사용하여 선언되었습니다. 이 상황에서 이 클래스의 요소는 기본 클래스 요소를 숨깁니다.  
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Visual Basic에서 경고 구성](../ide/configuring-warnings-in-visual-basic.md)을 참조하세요.  
  
 **오류 ID:** BC40005  
  
### 이 오류를 해결하려면  
  
-   기본 프로시저로 재정의하려면 `Overrides` 키워드를 선언에 추가합니다.  
  
-   기본 프로시저를 숨기려면 `Shadows` 키워드를 선언에 추가합니다.  
  
-   재정의 또는 숨기기를 수행하려는 경우가 아니면 선언될 요소 이름을 변경합니다.  
  
## 참고 항목  
 [빌드에 없음: 속성 및 메서드 재정의](http://msdn.microsoft.com/ko-kr/2167e8f5-1225-4b13-9ebd-02591ba90213)   
 [Shadowing in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/declared-elements/shadowing)   
 [Overrides](/dotnet/visual-basic/language-reference/modifiers/overrides)   
 [Shadows](/dotnet/visual-basic/language-reference/modifiers/shadows)