---
title: "컴파일러 오류 CS0833 | Microsoft Docs"
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
  - "CS0833"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0833"
ms.assetid: 4ae32454-265f-47aa-bf2a-ee1d702330b7
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0833
무명 형식에는 동일한 이름의 속성을 여러 개 사용할 수 없습니다.  
  
 모든 형식과 마찬가지로 무명 형식에 이름이 같은 두 개의 속성을 사용할 수 없습니다.  
  
### 이 오류를 해결하려면  
  
1.  형식의 각 속성에 고유한 이름을 지정합니다.  
  
## 예제  
 다음 예제에서는 CS0833을 생성합니다.  
  
```  
// cs0833.cs using System; public class C { public static int Main() { var c = new { p1 = 1, p1 = 2 }; // CS0833 return 1; } }  
```  
  
## 참고 항목  
 [익명 형식](/dotnet/csharp/programming-guide/classes-and-structs/anonymous-types)