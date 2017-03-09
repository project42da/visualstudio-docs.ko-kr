---
title: "컴파일러 오류 CS1632 | Microsoft Docs"
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
  - "CS1632"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1632"
ms.assetid: fa18061a-8c6c-4788-b74e-62bacb16aed8
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1632
제어가 무명 메서드 또는 람다 식의 본문을 벗어날 수 없습니다.  
  
 이 오류는 점프 문\(**break**, `goto`, **continue** 등\)이 무명 메서드 블록 밖으로 컨트롤을 이동하려는 경우 발생합니다. 무명 메서드 블록은 함수 본문이며 return 문이나 블록의 끝에 도달해야만 종료할 수 있습니다.  
  
 다음 샘플에서는 CS1632를 생성합니다.  
  
```  
// CS1632.cs // compile with: /target:library delegate void MyDelegate(); class MyClass { public void Test() { for (int i = 0 ; i < 5 ; i++) { MyDelegate d = delegate { break;   // CS1632 }; } } }  
```