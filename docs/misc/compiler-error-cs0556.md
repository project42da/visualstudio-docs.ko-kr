---
title: "컴파일러 오류 CS0556 | Microsoft Docs"
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
  - "CS0556"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0556"
ms.assetid: e2430c6e-784f-4ab2-88b9-f660d956e9e8
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0556
사용자 정의 변환은 바깥쪽 형식으로 변환하거나 바깥쪽 형식으로부터 변환해야 합니다.  
  
 사용자 정의 변환 루틴은 루틴을 포함하는 클래스에서 변환해야 합니다.  
  
 다음 샘플에서는 CS0556을 생성합니다.  
  
```  
// CS0556.cs namespace x { public class ii { public class iii { public static implicit operator int(byte aa)   // CS0556 // try the following line instead // public static implicit operator int(iii aa) { return 0; } } public static void Main() { } } }  
```