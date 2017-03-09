---
title: "&#39;&lt;constantname&gt;&#39; 상수는 자신의 값에 종속될 수 없습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc30500"
  - "vbc30500"
helpviewer_keywords: 
  - "BC30500"
ms.assetid: 0dad89bc-9196-492f-acd9-7777757362f7
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;constantname&gt;&#39; 상수는 자신의 값에 종속될 수 없습니다.
코드에서 상수가 자체 값에 따라 달라지는 순환 종속성을 만들었습니다. 예를 들어, `Const a = Const b; Const b = Const a`을 입력합니다.  
  
 **오류 ID:** BC30500  
  
### 이 오류를 해결하려면  
  
1.  코드를 검사하여 상수가 계산되는 위치를 확인하고 적절하게 수정합니다.  
  
## 참고 항목  
 [NOTINBUILD 상수 개요](http://msdn.microsoft.com/ko-kr/5c7f57fb-48b2-4a2f-afee-79d8e3adf15b)