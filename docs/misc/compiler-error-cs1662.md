---
title: "컴파일러 오류 CS1662 | Microsoft Docs"
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
  - "CS1662"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1662"
ms.assetid: e61a4fc8-0ef1-4a4a-a27b-3a015c3ba38a
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1662
블록의 반환 형식 중 일부를 암시적으로 대리자 반환 형식으로 변환할 수 없으므로 무명 메서드 블록을 'delegate type' 대리자 형식으로 변환할 수 없습니다.  
  
 이 오류는 무명 메서드 블록의 return 문에 암시적으로 대리자의 반환 형식으로 변환할 수 없는 형식이 있는 경우 발생합니다.  
  
 다음 샘플에서는 CS1662를 생성합니다.  
  
```  
// CS1662.cs delegate int MyDelegate(int i); class C { public static void Main() { MyDelegate d = delegate(int i) { return 1.0; };  // CS1662 // Try this instead: // MyDelegate d = dekegate(int i) { return (int)1.0; }; } }  
```