---
title: "컴파일러 오류 CS1104 | Microsoft Docs"
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
  - "CS1104"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1104"
ms.assetid: 65bfe85f-8dd1-4aed-bcd1-1f7e0635868c
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1104
매개 변수 배열은 확장 메서드의 'this' 한정자와 함께 사용할 수 없습니다.  
  
 확장 메서드의 첫 번째 매개 변수는 매개 변수 배열이 될 수 없습니다.  
  
### 이 오류를 해결하려면  
  
1.  확장 메서드 정의의 첫 번째 매개 변수는 메서드가 "확장"할 형식을 지정합니다. 입력 매개 변수가 아닙니다. 따라서 이 위치에 매개 변수 배열을 사용하는 것은 의미가 없습니다. 매개 변수 배열을 전달해야 하는 경우 두 번째 매개 변수로 지정합니다.  
  
## 예제  
 다음 예제에서는 CS1104를 생성합니다.  
  
```  
// cs1104.cs // Compile with: /target:library public static class Extensions { public static void Test<T>(this params T[] tArr) {} // CS1104 }   
```  
  
## 참고 항목  
 [확장 메서드](/dotnet/csharp/programming-guide/classes-and-structs/extension-methods)   
 [params](/dotnet/csharp/language-reference/keywords/params)