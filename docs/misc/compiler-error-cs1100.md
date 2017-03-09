---
title: "컴파일러 오류 CS1100 | Microsoft Docs"
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
  - "CS1100"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1100"
ms.assetid: ea233371-36b6-49ae-a98c-a00ee3b79e53
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1100
'name' 메서드의 첫 번째 매개 변수가 아닌 매개 변수에 매개 변수 한정자 'this'가 있습니다.  
  
 `this` 한정자는 메서드의 첫 번째 매개 변수에서만 사용할 수 있습니다. 이는 컴파일러에 메서드가 확장 메서드라는 것을 나타냅니다.  
  
### 이 오류를 해결하려면  
  
1.  메서드의 첫 번째 매개 변수를 제외한 모든 매개 변수에서 `this` 한정자를 제거합니다.  
  
## 예제  
 `this`  매개 변수가 두 번째 매개 변수를 수정하고 있기 때문에 다음 코드에서 CS1100을 생성합니다.  
  
```  
// cs1100.cs static class Test { static void ExtMethod(int i, this Test c) // CS1100 { } }  
```  
  
## 참고 항목  
 [확장 메서드](/dotnet/csharp/programming-guide/classes-and-structs/extension-methods)