---
title: "컴파일러 오류 CS0451 | Microsoft Docs"
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
  - "CS0451"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0451"
ms.assetid: e73544f8-856b-4a92-90e0-dd6cb9d688b1
caps.latest.revision: 12
caps.handback.revision: 12
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0451
'new\(\)' 제약 조건은 'struct' 제약 조건과 함께 사용할 수 없습니다.  
  
 제네릭의 형식에 대한 제약 조건을 지정하는 경우 `new()` 제약 조건은 클래스 형식 제약 조건, 인터페이스 형식 제약 조건, 참조 형식 제약 조건 및 형식 매개 변수 제약 조건에만 사용할 수 있고 값 형식 제약 조건에는 사용하지 않습니다.  
  
## 예제  
 다음 샘플에서는 CS0451을 생성합니다.  
  
```  
// CS0451.cs using System; public class C4 { public void F4<T>() where T : struct, new() {}   // CS0451 } // OK public class C5 { public void F5<T>() where T : struct {} } public class C6 { public void F6<T>() where T : new() {} }  
  
```