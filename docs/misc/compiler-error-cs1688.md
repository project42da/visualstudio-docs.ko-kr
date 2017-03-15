---
title: "컴파일러 오류 CS1688 | Microsoft Docs"
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
  - "CS1688"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1688"
ms.assetid: e15672a1-2570-4e65-99fc-7acc190ae643
caps.latest.revision: 12
caps.handback.revision: 12
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1688
'delegate' 대리자 형식에 out 매개 변수가 하나 이상 있으므로 매개 변수 목록이 없는 무명 메서드 블록을 이 대리자 형식으로 변환할 수 없습니다.  
  
 컴파일러가 대부분의 경우 무명 메서드 블록에서 매개 변수를 생략하는 것을 허용합니다. 무명 메서드 블록에 매개 변수 목록이 없지만 대리자에 `out` 매개 변수가 있는 경우 이 오류가 발생합니다. 컴파일러가 `out` 매개 변수의 존재를 무시\(이는 올바른 동작이 아닐 가능성이 높음\)해야 하기 때문에 이 상황을 허용하지 않습니다.  
  
## 예제  
 다음 코드에서는 CS1688 오류를 생성합니다.  
  
```  
// CS1688.cs using System; delegate void OutParam(out int i); class ErrorCS1676 { static void Main() { OutParam o; o = delegate  // CS1688 // Try this instead: // o = delegate(out int i) { Console.WriteLine(""); }; } }  
```