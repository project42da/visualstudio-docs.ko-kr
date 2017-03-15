---
title: "컴파일러 오류 CS0729 | Microsoft Docs"
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
  - "CS0729"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0729"
ms.assetid: e0421d06-e818-404f-af97-d101272f4d07
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0729
'type' 형식이 이 어셈블리에 정의되었지만 형식 전달자가 지정되었습니다.  
  
 동일한 어셈블리에서 정의된 형식에 형식 전달자를 사용할 수 없습니다.  
  
## 예제  
 다음 샘플에서는 CS0729를 생성합니다.  
  
```  
// CS0729.cs // compile with: /target:library using System.Runtime.CompilerServices; [assembly:TypeForwardedTo(typeof(TestClass))]   // CS0729 class TestClass {}  
```