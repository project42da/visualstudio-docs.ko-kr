---
title: "컴파일러 오류 CS1661 | Microsoft Docs"
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
  - "CS1661"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1661"
ms.assetid: 162d5736-ca3c-4a09-a5d9-a19da3d5bf24
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1661
지정한 무명 메서드 블록의 매개 변수 형식이 대리자 매개 변수 형식과 일치하지 않으므로 무명 메서드 블록을 'delegate type' 대리자 형식으로 변환할 수 없습니다.  
  
 이 오류는 무명 메서드 정의에서 무명 메서드의 매개 변수 형식이 대리자 매개 변수 형식과 일치하지 않는 경우에 발생합니다. 매개 변수 수, 매개 변수 형식, ref 또는 out 매개 변수를 확인하고 정확히 일치하는지 확인합니다.  
  
 다음 샘플에서는 CS1661을 생성합니다.  
  
```  
// CS1661.cs delegate void MyDelegate(int i); class C { public static void Main() { MyDelegate d = delegate(string s) { };  // CS1661 } }  
```