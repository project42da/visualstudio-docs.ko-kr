---
title: "컴파일러 오류 CS2019 | Microsoft Docs"
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
  - "CS2019"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS2019"
ms.assetid: eafd2531-8b3a-499c-9e12-a605a011396f
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS2019
잘못된 \/target의 대상 형식입니다. 'exe', 'winexe', 'library' 또는 'module'을 지정해야 합니다.  
  
 [\/target](/dotnet/csharp/language-reference/compiler-options/target-compiler-option) 컴파일러 옵션을 사용했지만 잘못된 매개 변수가 전달되었습니다. 이 오류를 해결하려면 출력 파일에 적합한 **\/target** 옵션의 형식을 사용하여 프로그램을 다시 컴파일합니다.  
  
 다음 샘플에서는 CS2017을 생성합니다.  
  
```  
// CS2019.cs // compile with: /target:libra // CS2019 expected class MyClass { }  
```