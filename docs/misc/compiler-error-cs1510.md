---
title: "컴파일러 오류 CS1510 | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS1510"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1510"
ms.assetid: 3f5a69f1-7672-4194-a4ee-5753370fc736
caps.latest.revision: 10
caps.handback.revision: 10
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1510
ref 또는 out 인수는 할당 가능한 변수여야 합니다.  
  
 변수만 메서드 호출에서 [ref](/dotnet/csharp/language-reference/keywords/ref) 매개 변수로 전달할 수 있습니다.`ref` 값은 포인터를 전달하는 것과 같습니다.  
  
## 예제  
 다음 샘플에서는 CS1510을 생성합니다.  
  
```  
// CS1510.cs public class C { public static int j = 0; public static void M(ref int j) { j++; } public static void Main () { M (ref 2);   // CS1510, can't pass a number as a ref parameter // try the following to resolve the error // M (ref j); } }  
```