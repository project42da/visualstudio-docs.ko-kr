---
title: "컴파일러 경고(수준 2) CS0469 | Microsoft Docs"
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
  - "CS0469"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0469"
ms.assetid: 773925ce-a8b2-4098-9ead-b96197442848
caps.latest.revision: 3
caps.handback.revision: 3
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 2) CS0469
'goto case' 값은 'type' 형식으로 암시적으로 변환할 수 없습니다.  
  
 `goto case`를 사용하는 경우 goto case 값에서 스위치 형식으로의 암시적 변환이 있어야 합니다.  
  
## 예제  
 다음 샘플에서는 CS0469를 생성합니다.  
  
```  
// CS0469.cs // compile with: /W:2 class Test { static void Main() { char c = (char)180; switch (c) { case (char)127: break; case (char)180: goto case 127;   // CS0469 // try the following line instead // goto case (char) 127; } } }  
```