---
title: "컴파일러 오류 CS1041 | Microsoft Docs"
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
  - "CS1041"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1041"
ms.assetid: 9f62c058-cd28-4cb5-835c-d0f25f4fd08e
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1041
식별자가 필요합니다. 'keyword'는 키워드입니다.  
  
 식별자가 필요한 C\# 언어의 예약어를 발견했습니다.[keyword](/dotnet/csharp/language-reference/keywords/index)를 사용자 지정 식별자로 바꿉니다.  
  
## 예제  
 다음 샘플에서는 CS1041을 생성합니다.  
  
```  
// CS1041a.cs class MyClass { public void f(int long)   // CS1041 // Try the following instead: // public void f(int i) { } public static void Main() { } }  
```  
  
## 예제  
 동일한 예약어 집합이 없는 다른 프로그래밍 언어에서 가져오는 경우 @ 접두사를 포함하는 예약된 식별자를 다음 샘플과 같이 수정할 수 있습니다.  
  
 `@` 접두사를 포함하는 식별자를 축자 식별자라고 합니다.  
  
```  
// CS1041b.cs class MyClass { public void f(int long)   // CS1041 // Try the following instead: // public void f(int @long) { } public static void Main() { } }  
```