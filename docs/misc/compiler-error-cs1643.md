---
title: "컴파일러 오류 CS1643 | Microsoft Docs"
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
  - "CS1643"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1643"
ms.assetid: 521f352b-00fb-4d62-89be-44251db3cc5b
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1643
코드 경로 중 일부에서만 'type\!' 형식의 메서드에 있는 값을 반환합니다.  
  
 이 오류는 대리자 본문에 return 문이 없거나 컴파일러에서 확인할 수 없는 return 문이 있는 경우 발생합니다. 아래 예제에서 컴파일러는 무명 메서드 블록이 항상 값을 반환하는지 확인하기 위해 분기 조건의 결과를 예측하지 않습니다.  
  
## 예제  
 다음 샘플에서는 CS1643을 생성합니다.  
  
```  
// CS1643.cs delegate int MyDelegate(); class C { static void Main() { MyDelegate d = delegate {                 // CS1643 int i = 0; if (i == 0) return 1; }; } }  
```