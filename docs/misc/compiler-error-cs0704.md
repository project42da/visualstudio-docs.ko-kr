---
title: "컴파일러 오류 CS0704 | Microsoft Docs"
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
  - "CS0704"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0704"
ms.assetid: a16ae7f3-11e0-45f3-ac40-91a853eea4e5
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0704
'type'은 형식 매개 변수이므로 멤버를 조회할 수 없습니다.  
  
 형식 매개 변수를 통해 내부 형식을 지정할 수 없습니다. 원하는 종류를 명시적으로 사용하세요.  
  
## 예제  
 다음 샘플에서는 CS0704를 생성합니다.  
  
```  
// CS0704.cs class B { public class I { } } class C<T> where T : B { T.I f;  // CS0704 – member lookup on type parameter // Try this instead: // B.I f; } class CMain { public static void Main() {} }  
```