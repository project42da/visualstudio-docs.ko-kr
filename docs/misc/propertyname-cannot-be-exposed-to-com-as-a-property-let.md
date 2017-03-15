---
title: "&#39;&lt;propertyname&gt;&#39;을 COM에 &#39;Let&#39; 속성으로 노출할 수 없습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc42102"
  - "vbc42102"
helpviewer_keywords: 
  - "BC42102"
ms.assetid: b77c5b7c-ac43-4b2d-b8bc-582e65e6f7e7
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;propertyname&gt;&#39;을 COM에 &#39;Let&#39; 속성으로 노출할 수 없습니다.
'\<propertyname\>'을 COM에 'Let' 속성으로 노출할 수 없습니다. Visual Basic 6.0의 'Let' 문을 사용하여 이 속성에 숫자나 문자열 같은 개체가 아닌 값을 할당할 수 없습니다.  
  
 `COMClassAttribute` 특성 블록을 사용하는 클래스는 `Object` 데이터 형식을 사용하여 `Public` 속성을 선언합니다. Visual Basic 6.0 프로그램에서 `Variant`로 이 속성에 액세스할 수 있지만, `Set` 문에서 이 속성에 개체 참조만 할당할 수 있습니다.`Let` 문에서 값 형식을 할당할 수 없습니다.  
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Visual Basic에서 경고 구성](../ide/configuring-warnings-in-visual-basic.md)을 참조하세요.  
  
 **오류 ID:** BC42102  
  
### 이 경고를 해결하려면  
  
-   이 클래스의 잠재적 Visual Basic 6.0 사용자에게 `Let` 문에서 이 속성을 사용할 수 없다는 사실을 알리는 것이 좋습니다.  
  
## 참고 항목  
 [Default Property Changes in Visual Basic](http://msdn.microsoft.com/ko-kr/9b8cfad7-40ac-4b83-affb-1ff781755a4c)   
 [Property Statement](/dotnet/visual-basic/language-reference/statements/property-statement)   
 [Public](/dotnet/visual-basic/language-reference/modifiers/public)   
 [Object Data Type](/dotnet/visual-basic/language-reference/data-types/object-data-type)   
 [빌드에 없음: Visual Basic에서 사용되는 특성](http://msdn.microsoft.com/ko-kr/22231318-8a40-49af-9245-e0aab723563b)   
 [빌드에 없음: 특성 적용](http://msdn.microsoft.com/ko-kr/2b1703ed-4437-49b3-bc0b-568094324f47)   
 [ComClassAttribute 클래스](http://msdn.microsoft.com/ko-kr/5c2f0835-9210-47dc-bc59-5c1769953574)