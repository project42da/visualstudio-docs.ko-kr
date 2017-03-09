---
title: "컴파일러 오류 CS1113 | Microsoft Docs"
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
  - "CS1113"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1113"
ms.assetid: ef2d828f-b5ee-4be9-ba2e-36df5502cc5a
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1113
값 형식 'name'에 정의된 확장 메서드 'name'은 대리자를 만드는 데 사용할 수 없습니다.  
  
 클래스 형식에 대해 정의된 확장 메서드는 대리자를 만드는 데 사용할 수 있습니다. 값 형식에 대해 정의된 확장 메서드는 사용할 수 없습니다.  
  
### 이 오류를 해결하려면  
  
1.  확장 메서드를 클래스 형식과 연결합니다.  
  
2.  메서드를 구조체의 일반 메서드로 만듭니다.  
  
## 예제  
 다음 예제에서는 CS1113을 생성합니다.  
  
```  
// cs1113.cs using System; public static class Extensions { public static S ExtMethod(this S s) { return s; } } public struct S { } public class Test { static int Main() { Func<S> f = new S().ExtMethod; // CS1113 return 1; } }  
  
```  
  
## 참고 항목  
 [확장 메서드](/dotnet/csharp/programming-guide/classes-and-structs/extension-methods)