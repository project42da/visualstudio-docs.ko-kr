---
title: "컴파일러 오류 CS0756 | Microsoft Docs"
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
  - "CS0756"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0756"
ms.assetid: 847b20b0-bbf0-43a2-8728-4b54cb3d9cd6
caps.latest.revision: 5
caps.handback.revision: 5
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0756
부분 메서드\(Partial Method\)에는 하나의 정의 선언만 사용할 수 있습니다.  
  
 부분 메서드\(Partial Method\)의 선언 정의에 메서드 서명 지정은 포함되지만 구현\(메서드 본문\)은 포함되지 않습니다. 부분 메서드\(Partial Method\)에는 각 고유 서명에 대해 정확히 하나의 정의 선언이 있어야 합니다. 오버로드된 각 버전의 부분 메서드\(Partial Method\)에는 자체 정의 선언이 있어야 합니다.  
  
### 이 오류를 해결하려면  
  
1.  부분 메서드\(Partial Method\)에 대한 정의 선언을 제외한 나머지를 모두 제거합니다.  
  
## 예제  
  
```  
// cs0756.cs using System; public partial class C { partial void Part(); partial void Part(); // CS0756 public static int Main() { return 1; } }  
```  
  
## 참고 항목  
 [Partial 클래스 및 메서드](/dotnet/csharp/programming-guide/classes-and-structs/partial-classes-and-methods)