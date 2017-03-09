---
title: "&#39;&lt;procedure1&gt;&#39; 및 &#39;&lt;procedure2&gt;&#39;는 &#39;ByRef&#39; 또는 &#39;ByVal&#39;로 선언된 매개 변수만 다르므로 서로 오버로드할 수 없습니다. | Microsoft Docs"
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
  - "vbc42003"
  - "bc42003"
helpviewer_keywords: 
  - "BC42003"
ms.assetid: f058f1e0-64d2-4497-85fc-a58e16b0d805
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;procedure1&gt;&#39; 및 &#39;&lt;procedure2&gt;&#39;는 &#39;ByRef&#39; 또는 &#39;ByVal&#39;로 선언된 매개 변수만 다르므로 서로 오버로드할 수 없습니다.
'\<procedure1\>' 및 '\<procedure2\>'는 ByRef 또는 ByVal로 선언된 매개 변수만 다르므로 서로 오버로드할 수 없습니다. Shadow로 간주합니다.  
  
 두 프로시저 선언은 동일한 이름 및 인수 목록을 지정하고 하나 이상의 인수에 대해 `ByRef` 또는 `ByVal`을 지정하는 점만 다릅니다. 오버로드된 프로시저 버전은 인수의 번호, 순서 또는 데이터 형식에서 서로 달라야 합니다.  
  
 이 메시지는 경고입니다. 기본적으로 `Shadows`로 간주됩니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Visual Basic에서 경고 구성](../ide/configuring-warnings-in-visual-basic.md)을 참조하세요.  
  
 **오류 ID:** BC42003  
  
### 이 오류를 해결하려면  
  
-   프로시저의 오버로드된 버전 집합을 만들려면 각 버전에서 인수의 번호, 순서 또는 데이터 형식을 다르게 합니다. 또한 `Overloads` 키워드를 각 선언에 추가합니다.  
  
-   프로시저를 오버로드하지 않으려면 선언 중 하나에서 프로시저 이름을 변경합니다.  
  
## 참고 항목  
 [Procedure Overloading](/dotnet/visual-basic/programming-guide/language-features/procedures/procedure-overloading)