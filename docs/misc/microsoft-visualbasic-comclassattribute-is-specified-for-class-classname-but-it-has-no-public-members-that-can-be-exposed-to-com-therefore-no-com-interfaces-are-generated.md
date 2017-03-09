---
title: "&#39;&lt;classname&gt;&#39; 클래스에 &#39;Microsoft.VisualBasic.ComClassAttribute&#39;가 지정되어 있지만 COM에 노출할 수 있는 public 멤버가 없으므로 COM 인터페이스가 생성되지 않았습니다. | Microsoft Docs"
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
  - "bc40011"
  - "vbc40011"
helpviewer_keywords: 
  - "BC40011"
ms.assetid: 39aed273-bf27-4667-8116-022c4dd8f3c5
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;classname&gt;&#39; 클래스에 &#39;Microsoft.VisualBasic.ComClassAttribute&#39;가 지정되어 있지만 COM에 노출할 수 있는 public 멤버가 없으므로 COM 인터페이스가 생성되지 않았습니다.
`COMClassAttribute` 특성 블록을 사용하는 클래스는 `Public` 속성 또는 메서드를 정의하지 않습니다. 클래스를 COM 개체로 노출해야 하는 경우 해당 속성과 메서드를 `Public` 액세스 권한으로 선언해야 합니다.  
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Visual Basic에서 경고 구성](../ide/configuring-warnings-in-visual-basic.md)을 참조하세요.  
  
 **오류 ID:** BC40011  
  
### 이 오류를 해결하려면  
  
-   클래스의 하나 이상 속성 또는 메서드에 `Public` 키워드를 추가하거나 `COMClassAttribute` 특성 블록을 제거합니다.  
  
## 참고 항목  
 [빌드에 없음: Visual Basic에서 사용되는 특성](http://msdn.microsoft.com/ko-kr/22231318-8a40-49af-9245-e0aab723563b)   
 [빌드에 없음: 특성 적용](http://msdn.microsoft.com/ko-kr/2b1703ed-4437-49b3-bc0b-568094324f47)   
 [Public](/dotnet/visual-basic/language-reference/modifiers/public)   
 [ComClassAttribute 클래스](http://msdn.microsoft.com/ko-kr/5c2f0835-9210-47dc-bc59-5c1769953574)