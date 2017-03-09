---
title: "CLS 규격 경고 CLS03202 | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CLS03202"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CLS03202"
ms.assetid: 2219c86c-9276-4244-a2ff-bce578c4d65f
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "douge"
---
# CLS 규격 경고 CLS03202
이벤트에 대한 add 및 remove 메서드는 이벤트 유형 정의 형식을 갖는 하나의 매개 변수를 각각 사용해야 하며, 해당 형식은 System.Delegate에서 파생된 것이어야 합니다.  
  
 이벤트에 대한 add 및 remove 메서드는 이벤트 유형 정의 형식을 갖는 하나의 매개 변수를 각각 사용해야 하며, 해당 형식은 System.Delegate에서 파생된 것이어야 합니다.  
  
 CLS 규격 검사에 대한 자세한 내용은 [CLS 규격 어셈블리](http://msdn.microsoft.com/ko-kr/3320b57e-ea55-4697-a17d-f509a36a3c93)를 참조하세요.  
  
 다음 함수 선언\(MSIL 어셈블리 언어 사용\)에서는 CLS03202를 발생시키는 원인을 보여 줍니다.  
  
```  
// bad .method public specialname instance void add_MyEvent(class MyDelegate __unnamed000, int32 __extra) cil managed {}  
```  
  
 이벤트 접근자에서 하나의 매개 변수만 사용하는 경우 이 경고를 해결할 수 있습니다.  
  
```  
.method public specialname instance void add_MyEvent(class MyDelegate __unnamed000) cil managed {}  
```