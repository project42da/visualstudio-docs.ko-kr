---
title: "컴파일러 오류 CS0196 | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS0196"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0196"
ms.assetid: d361484e-73b8-439a-99c7-714e61d73755
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0196
포인터는 한 값에 의해서만 인덱싱되어야 합니다.  
  
 포인터에 여러 개의 인덱스가 있을 수 없습니다. 자세한 내용은 [포인터 형식](/dotnet/csharp/programming-guide/unsafe-code-pointers/pointer-types)을 참조하세요.  
  
 다음 샘플에서는 CS0196을 생성합니다.  
  
```  
// CS0196.cs public class MyClass { public static void Main () { int *i = null; int j = 0; j = i[1,2];   // CS0196 // try the following line instead // j = i[1]; } }  
```