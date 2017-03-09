---
title: "컴파일러 오류 CS0017 | Microsoft Docs"
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
  - "CS0017"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0017"
ms.assetid: 5e2a3eb3-6f6e-485d-8293-ceabea4d6905
caps.latest.revision: 10
caps.handback.revision: 10
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0017
'output file name' 프로그램에 둘 이상의 진입점이 정의되었습니다. \/main으로 컴파일하여 진입점을 포함하는 형식을 지정합니다.  
  
 프로그램에는 [Main](/dotnet/csharp/programming-guide/main-and-command-args/main-and-command-line-arguments) 메서드가 하나만 있어야 합니다.  
  
 이 오류를 해결하려면 코드에서 Main 메서드를 하나만 남기고 모두 삭제하거나 [\/main](/dotnet/csharp/language-reference/compiler-options/main-compiler-option) 컴파일러 옵션을 사용하여 사용하려는 Main 메서드를 지정할 수 있습니다.  
  
 다음 샘플에서는 CS0017을 생성합니다.  
  
```  
// CS0017.cs // compile with: /target:exe public class clx { static public void Main() { } } public class cly { public static void Main()   // CS0017, delete one Main or use /main { } }  
```