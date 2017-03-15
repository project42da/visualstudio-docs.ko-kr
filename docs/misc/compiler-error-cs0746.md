---
title: "컴파일러 오류 CS0746 | Microsoft Docs"
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
  - "CS0746"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0746"
ms.assetid: 36baf7f2-b092-422c-ab53-95154bfceb0a
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0746
잘못된 무명 형식 멤버 선언자입니다. 무명 형식 멤버는 멤버 할당, 단순한 이름 또는 멤버 액세스로 선언되어야 합니다.  
  
 무명 형식은 멤버 할당, 단순한 이름 또는 멤버 액세스로 선언되어야 합니다.  
  
### 이 오류를 해결하려면  
  
1.  선언에서 멤버 할당, 단순한 이름 또는 멤버 액세스 식만 사용하는지 확인합니다.  
  
## 예제  
 다음 코드는 `incorrect_1` 및 `incorrect_2` 선언에서 CS0746을 생성합니다. 다음 선언은 무명 형식을 선언하는 두 가지 올바른 방법을 보여 줍니다.  
  
```  
// cs0746.cs public class C { public static int Main() { int i = 100; string s = "Bottles of beer."; var incorrect_1 = new { a.b = 1 }; // CS0746 var incorrect_2 = new {100, "Bottles of beer."}; // CS0746 var correct_1 = new { i, s }; //OK var correct_2 = new {num = i, message = s}; // OK return 1; } }  
  
```  
  
## 참고 항목  
 [익명 형식](/dotnet/csharp/programming-guide/classes-and-structs/anonymous-types)