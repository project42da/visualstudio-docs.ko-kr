---
title: "컴파일러 오류 CS0554 | Microsoft Docs"
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
  - "CS0554"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0554"
ms.assetid: 884db4b2-3a69-4434-9a25-526f596e03c8
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0554
'conversion routine': 사용자가 파생 클래스로\/에서의 변환을 정의했습니다.  
  
 파생 클래스 값으로의 사용자 정의 변환은 허용되지 않습니다. 이러한 연산자는 필요하지 않습니다.  
  
 사용자 정의 변환에 대한 자세한 내용은 C\# 언어 사양의 6장을 참조하세요.  
  
 다음 샘플에서는 CS0554를 생성합니다.  
  
```  
// CS0554.cs namespace x { public class ii { // delete the conversion routine to resolve CS0554 public static implicit operator ii(a aa) // CS0554 { return new ii(); } } public class a : ii { public static void Main() { } } }  
```