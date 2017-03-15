---
title: "컴파일러 경고(수준 2) CS0440 | Microsoft Docs"
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
  - "CS0440"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0440"
ms.assetid: ade6761f-4d7d-42bc-a0c5-bbb1b987a1aa
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 2) CS0440
'global::'은 별칭이 아니라 전역 네임스페이스를 항상 참조하므로 별칭 이름을 'global'로 정의하지 않는 것이 좋습니다.  
  
 이 경고는 전역이라는 별칭을 정의할 때 발생합니다.  
  
## 예제  
 다음 예제에서는 CS0440을 생성합니다.  
  
```  
// CS0440.cs // Compile with: /W:1 using global = MyClass;   // CS0440 class MyClass { static void Main() { // Note how global refers to the global namespace // even though it is redefined above. global::System.Console.WriteLine(); } }  
```