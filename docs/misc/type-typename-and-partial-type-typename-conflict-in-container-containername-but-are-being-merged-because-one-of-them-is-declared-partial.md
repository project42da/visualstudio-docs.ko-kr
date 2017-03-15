---
title: "&#39;&lt;typename&gt;&#39; 형식 및 &#39;&lt;typename&gt;&#39; 부분 형식(Partial Type)이 &#39;&lt;containername&gt;&#39; 컨테이너에서 충돌하지만 형식 중 하나가 partial로 선언되었으므로 병합됩니다. | Microsoft Docs"
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
  - "bc40046"
  - "vbc40046"
helpviewer_keywords: 
  - "BC40046"
ms.assetid: c243e70b-ecd5-49ef-a260-a7bb12a4a3b1
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;typename&gt;&#39; 형식 및 &#39;&lt;typename&gt;&#39; 부분 형식(Partial Type)이 &#39;&lt;containername&gt;&#39; 컨테이너에서 충돌하지만 형식 중 하나가 partial로 선언되었으므로 병합됩니다.
클래스 또는 구조체가 동일한 컨테이너 형식에서 여러 정의에 표시되고 둘 이상의 정의가 `Partial`로 표시되지 않습니다.  
  
 클래스 또는 구조체의 여러 정의 중 하나 이상에서 [Partial](/dotnet/visual-basic/language-reference/modifiers/partial) 키워드를 사용해야 하지만 모든 부분 정의에서 사용하는 것이 좋습니다.  
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Visual Basic에서 경고 구성](../ide/configuring-warnings-in-visual-basic.md)을 참조하세요.  
  
 **오류 ID:** BC40046  
  
### 이 오류를 해결하려면  
  
-   클래스 또는 구조체의 모든 부분 정의에 [Partial](/dotnet/visual-basic/language-reference/modifiers/partial) 키워드를 사용합니다.  
  
## 참고 항목  
 [Partial](/dotnet/visual-basic/language-reference/modifiers/partial)