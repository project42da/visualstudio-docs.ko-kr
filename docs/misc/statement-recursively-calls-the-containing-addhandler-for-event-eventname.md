---
title: "&#39;&lt;eventname&gt;&#39; 이벤트에 대해 포함하는 AddHandler를 문이 재귀적으로 호출합니다. | Microsoft Docs"
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
  - "bc41998"
  - "vbc41998"
helpviewer_keywords: 
  - "BC41998"
ms.assetid: 4375b191-fbd9-4e93-b9bb-9159d533ddf6
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;eventname&gt;&#39; 이벤트에 대해 포함하는 AddHandler를 문이 재귀적으로 호출합니다.
이벤트 정의의 `AddHandler` 접근자에 있는 문에서 이벤트를 직접 참조하면 안 됩니다.  
  
 이벤트를 정의한 클래스, 구조체 또는 모듈의 전용 필드로 이벤트의 처리기 목록을 저장하는 것이 좋습니다. 자세한 내용은 [How to: Declare Custom Events To Avoid Blocking](../Topic/How%20to:%20Declare%20Custom%20Events%20To%20Avoid%20Blocking%20\(Visual%20Basic\).md) 및 [How to: Declare Custom Events To Conserve Memory](../Topic/How%20to:%20Declare%20Custom%20Events%20To%20Conserve%20Memory%20\(Visual%20Basic\).md)를 참조하세요.  
  
 **오류 ID:** BC41998  
  
### 이 오류를 해결하려면  
  
-   재귀를 방지하도록 이벤트 정의를 다시 작성합니다.  
  
## 참고 항목  
 [AddHandler \- 삭제](http://msdn.microsoft.com/ko-kr/fc464cf8-582c-48a6-a9c2-185c4c3d5ff8)   
 [Event Statement](/dotnet/visual-basic/language-reference/statements/event-statement)   
 [How to: Declare Custom Events To Avoid Blocking](../Topic/How%20to:%20Declare%20Custom%20Events%20To%20Avoid%20Blocking%20\(Visual%20Basic\).md)   
 [How to: Declare Custom Events To Conserve Memory](../Topic/How%20to:%20Declare%20Custom%20Events%20To%20Conserve%20Memory%20\(Visual%20Basic\).md)