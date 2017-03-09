---
title: "컴파일러 오류 CS0557 | Microsoft Docs"
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
  - "CS0557"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0557"
ms.assetid: beca353e-4fea-4e4f-a48a-eddeebb153bb
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0557
'class' 형식의 사용자 정의 변환이 중복되었습니다.  
  
 중복 변환 루틴은 클래스에서 허용되지 않습니다.  
  
 다음 예제에서는 CS0557을 생성합니다.  
  
```  
// CS0557.cs namespace x { public class ii { public class iii { public static implicit operator int(iii aa) { return 0; } // CS0557, delete duplicate public static explicit operator int(iii aa) { return 0; } } public static void Main() { } } }  
```