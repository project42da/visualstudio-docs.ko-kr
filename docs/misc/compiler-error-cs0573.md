---
title: "컴파일러 오류 CS0573 | Microsoft Docs"
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
  - "CS0573"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0573"
ms.assetid: 10ef9625-44f1-4936-ada3-56938357aa01
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0573
'field declaration': 구조체에는 인스턴스 필드 이니셜라이저를 사용할 수 없습니다.  
  
 [구조체](/dotnet/csharp/language-reference/keywords/struct)의 인스턴스 필드를 초기화할 수 없습니다. 값 형식의 필드는 해당 기본값으로 초기화되고 참조 형식 필드는 `null`로 초기화됩니다.  
  
## 예제  
 다음 샘플에서는 CS0573을 생성합니다.  
  
```  
// CS0573.cs namespace x { public class clx { public static void Main() { } } public struct cly { clx a = new clx();   // CS0573 // clx a;            // OK int i = 7;           // CS0573 // int i;            // OK } }  
```