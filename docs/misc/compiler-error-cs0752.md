---
title: "컴파일러 오류 CS0752 | Microsoft Docs"
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
  - "CS0752"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0752"
ms.assetid: f9a373d6-31ed-42db-8206-80cbe9b8c546
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0752
부분 메서드\(Partial Method\)에는 out 매개 변수를 사용할 수 없습니다.  
  
 부분 메서드\(Partial Method\)에는 [out](/dotnet/csharp/language-reference/keywords/out) 매개 변수를 사용할 수 없습니다. 부분 메서드\(Partial method\)가 컴파일러에서 제거된 경우 out 매개 변수가 할당된다는 것을 보장하지 않기 때문에 out 매개 변수가 허용되지 않습니다.  
  
### 이 오류를 해결하려면  
  
1.  매개 변수에서 out 한정자를 제거하고 대신 메서드의 반환 값을 사용하거나 메서드 선언에서 partial 한정자를 제거합니다.  
  
## 예제  
 다음 코드에서는 CS0752를 생성합니다.  
  
```  
// cs0752.cs public partial class C { partial void Part(out int num); // CS0752 // try the following line instead // partial void Part(int num); public static int Main() { return 1; } }  
```  
  
## 참고 항목  
 [Partial 클래스 및 메서드](/dotnet/csharp/programming-guide/classes-and-structs/partial-classes-and-methods)