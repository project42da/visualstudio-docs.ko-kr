---
title: "컴파일러 오류 CS2013 | Microsoft Docs"
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
  - "CS2013"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS2013"
ms.assetid: 8a57b4c8-02fc-4f73-b489-121ff468c17d
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS2013
잘못된 'value' 이미지 기준 번호입니다.  
  
 잘못된 값\(숫자 아님\)이 [\/baseaddress](/dotnet/csharp/language-reference/compiler-options/baseaddress-compiler-option) 컴파일러 옵션으로 전달되었습니다.  
  
 다음 샘플에서는 CS2013을 생성합니다.  
  
```  
// CS2013.cs // compile with: /target:library /baseaddress:x // CS2013 expected class MyClass { }  
```