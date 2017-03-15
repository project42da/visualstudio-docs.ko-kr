---
title: "특성 생성자의 매개 변수 형식은 &#39;&lt;type&gt;&#39;이며, 이 형식은 정수, 부동 소수점 또는 열거형이 아니며 또한 Char, String, Boolean, System.Type 또는 이러한 형식의 1차원 배열이 아닙니다. | Microsoft Docs"
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
  - "bc30045"
  - "vbc30045"
helpviewer_keywords: 
  - "BC30045"
ms.assetid: 16899755-7901-4c56-ae90-54c3532e8319
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 특성 생성자의 매개 변수 형식은 &#39;&lt;type&gt;&#39;이며, 이 형식은 정수, 부동 소수점 또는 열거형이 아니며 또한 Char, String, Boolean, System.Type 또는 이러한 형식의 1차원 배열이 아닙니다.
매개 변수에 대한 잘못된 데이터 형식을 지정하는 생성자가 사용자 지정 특성 정의에 포함되어 있습니다. 특성의 형식만 어셈블리에 대한 메타데이터로 serialize될 수 있으므로 특성은 특정 데이터 형식만 매개 변수로 사용할 수 있습니다.  
  
 **오류 ID:** BC30045  
  
### 이 오류를 해결하려면  
  
1.  매개 변수의 데이터 형식을 `Byte`, `Short`, `Integer`, `Long`, `Single`, `Double`, `Char`, `String`, `Boolean`, `System.Type` 또는 열거형 형식으로 변경합니다.  
  
## 참고 항목  
 [빌드에 없음: Visual Basic의 사용자 지정 특성](http://msdn.microsoft.com/ko-kr/d72d8a5c-8f64-4614-b15b-cad66845d047)