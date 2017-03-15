---
title: "컴파일러 오류 CS0832 | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS0832"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0832"
ms.assetid: b5527209-a9bd-4f8c-a432-2e89bb1905d1
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0832
식 트리에는 대입 연산자를 사용할 수 없습니다.  
  
 식 트리에는 변수 상태가 유지되지 않거나 저장소 위치 개념이 없습니다.  
  
### 이 오류를 해결하려면  
  
1.  람다 또는 쿼리 식에서 대입 연산자를 제거합니다.  
  
## 예제  
 모든 람다 식에서와 같이 예제 코드에서 `x`은 값으로 전달되는 입력 매개 변수일 뿐입니다. 식 트리에서 해당 값을 변경할 수 없습니다. 대리자 람다에서 변경할 수 있습니다.  
  
```  
// cs0843.cs using System; using System.Linq; using System.Linq.Expressions; public class C { public static int Main() { Expression<Func<int, int>> e = x => x += 5; // CS0843 return 1; } }  
```