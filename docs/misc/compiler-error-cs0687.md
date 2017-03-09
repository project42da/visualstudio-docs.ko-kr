---
title: "컴파일러 오류 CS0687 | Microsoft Docs"
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
  - "CS0687"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0687"
ms.assetid: b51c5e7c-f4de-4aa4-97b1-ebe220cd19b0
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0687
네임스페이스 별칭 한정자 '::'은 항상 형식 또는 네임스페이스를 확인하므로 여기에 사용할 수 없습니다. 대신 '.'를 사용하세요.  
  
 파서가 예상치 못한 위치에서 형식으로 해석한 것을 사용한 경우 이 오류가 발생합니다. 형식 또는 네임스페이스의 이름은 멤버 액세스\(**.**\) 연산자를 사용하는 멤버 액세스 식에서만 유효합니다. 이는 다른 컨텍스트에서 전역 범위 연산자\(::\)를 사용할 경우 발생할 수 있습니다.  
  
## 예제  
 다음 샘플에서는 CS0687을 생성합니다.  
  
```  
// CS0687.cs using M = Test; using System; public class Test { public static int x = 77; public static void Main() { Console.WriteLine(M::x); // CS0687 // To resolve use the following line instead: // Console.WriteLine(M.x); } }  
```