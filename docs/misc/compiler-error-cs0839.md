---
title: "컴파일러 오류 CS0839 | Microsoft Docs"
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
  - "CS0839"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0839"
ms.assetid: 6f2f1062-8551-4125-8880-68bfbfbcf061
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0839
인수가 없습니다.  
  
 메서드 호출에 인수가 없습니다.  
  
### 이 오류를 해결하려면  
  
1.  메서드의 서명을 다시 확인하고 누락된 인수를 찾아서 제공합니다.  
  
## 예제  
 다음 예제에서는 CS0839를 생성합니다.  
  
```  
// cs0839.cs using System; namespace TestNamespace { class Test { static int Add(int i, int j) { return i + j; } static int Main() { int i = Test.Add( , 5); // CS0839 return 1; } } }  
```