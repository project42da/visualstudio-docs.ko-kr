---
title: "컴파일러 오류 CS1010 | Microsoft Docs"
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
  - "CS1010"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1010"
ms.assetid: 3d47277a-253f-464b-a603-e3b37e0e7b0d
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1010
상수에 줄 바꿈 문자가 있습니다.  
  
 [문자열](/dotnet/csharp/language-reference/keywords/string)이 제대로 구분되지 않았습니다.  
  
 다음 샘플에서는 CS1010을 생성합니다.  
  
```  
// CS1010.cs class Sample { static void Main() { string a = "Hello World;   // CS1010 // Use the following line, with end quote before semicolon: string a = "Hello World"; // } }  
```  
  
## 참고 항목  
 [NIB \- 문자열\(C\# 프로그래밍 가이드\)](http://msdn.microsoft.com/ko-kr/1a32b1c9-0d99-468a-9734-e3a47f2e897a)