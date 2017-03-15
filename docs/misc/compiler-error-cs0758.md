---
title: "컴파일러 오류 CS0758 | Microsoft Docs"
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
  - "CS0758"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0758"
ms.assetid: 06ddd548-1311-40db-9078-8a18107b8346
caps.latest.revision: 5
caps.handback.revision: 5
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0758
두 부분 메서드\(Partial Method\) 선언 모두 params 매개 변수를 사용하거나 params 매개 변수를 사용할 수 없습니다.  
  
 부분 메서드의 한 부분이 `params` 매개 변수를 지정하는 경우 다른 부분에서도 지정해야 합니다.  
  
### 이 오류를 해결하려면  
  
1.  메서드의 한 부분에 `params` 한정자를 추가하거나 다른 부분에서 제거합니다.  
  
## 예제  
 다음 코드에서는 CS0758을 생성합니다.  
  
```  
using System; public partial class C { partial void Part(int i, params char[] array); partial void Part(int i, char[] array) // CS0758 { } public static int Main() { return 1; } }  
```  
  
## 참고 항목  
 [Partial 클래스 및 메서드](/dotnet/csharp/programming-guide/classes-and-structs/partial-classes-and-methods)   
 [params](/dotnet/csharp/language-reference/keywords/params)