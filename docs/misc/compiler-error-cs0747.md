---
title: "컴파일러 오류 CS0747 | Microsoft Docs"
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
  - "CS0747"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0747"
ms.assetid: dc1b7e38-cee5-406c-b193-a60ec4faebe1
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0747
잘못된 이니셜라이저 멤버 선언자입니다.  
  
 속성 또는 필드에 값을 할당하는 데 개체 이니셜라이저가 사용됩니다. 속성 또는 필드에 할당되지 않는 식은 컴파일 시간 오류입니다.  
  
### 이 오류를 해결하려면  
  
1.  이니셜라이저의 모든 식이 형식의 필드 또는 속성에 할당되었는지 확인합니다. 다음 예제에서는 `1` 값이 `List<int>`의 필드 또는 속성에 할당되지 않았기 때문에 두 번째 식이 오류입니다.  
  
## 예제  
 다음 코드에서는 CS0747을 생성합니다.  
  
```  
// cs0747.cs using System.Collections.Generic; public class C { public static int Main() { var t = new List<int> { Capacity = 2, 1 }; // CS0747 return 1; } }  
```  
  
## 참고 항목  
 [개체 및 컬렉션 이니셜라이저](/dotnet/csharp/programming-guide/classes-and-structs/object-and-collection-initializers)