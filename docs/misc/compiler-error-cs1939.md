---
title: "컴파일러 오류 CS1939 | Microsoft Docs"
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
  - "CS1939"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1939"
ms.assetid: 9a7cdd48-3d45-473a-a799-c7771ef8158d
caps.latest.revision: 5
caps.handback.revision: 5
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1939
범위 변수 'name'을 out 또는 ref 매개 변수로 전달할 수 없습니다.  
  
 범위 변수는 쿼리 식에서 정의되고 소스 시퀀스에서 각 연속 요소의 식별자로 사용되는 읽기 전용 변수입니다. 어떤 방식으로든 수정할 수 없으므로 `ref` 또는 `out`으로 전달하는 것은 의미가 없습니다. 따라서 두 작업은 잘못된 것입니다.  
  
### 이 오류를 해결하려면  
  
1.  범위 변수를 값으로 전달합니다.  
  
## 예제  
 다음 예제에서는 CS1939를 생성합니다.  
  
```  
// cs1939.cs using System.Linq; class Test { public static void F(ref int i) { } public static void Main() { var list = new int[] { 0, 1, 2, 3, 4, 5 }; var q = from x in list let k = x select Test.F(ref x); // CS1939 } }  
```