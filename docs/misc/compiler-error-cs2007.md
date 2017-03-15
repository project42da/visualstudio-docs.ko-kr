---
title: "컴파일러 오류 CS2007 | Microsoft Docs"
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
  - "CS2007"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS2007"
ms.assetid: 9be20e8e-2424-4435-9371-778fb12823c0
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS2007
인식할 수 없는 명령줄 옵션: 'option'  
  
 컴파일러에 슬래시\(\/\)로 시작되었지만 [컴파일러 옵션](/dotnet/csharp/language-reference/compiler-options/index)이 아닌 문자열이 전달되었습니다.  
  
 다음 샘플에서는 CS2007을 생성합니다.  
  
```  
// CS2007.cs // compile with: /recur // CS2007 expected class x { public static void Main() {} }  
```