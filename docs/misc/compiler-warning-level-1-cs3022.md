---
title: "컴파일러 경고(수준 1) CS3022 | Microsoft Docs"
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
  - "CS3022"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS3022"
ms.assetid: 9340645c-10c3-4e21-a825-3f05fae02ff7
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 1) CS3022
CLSCompliant 특성을 매개 변수에 적용하면 의미가 없습니다. 대신 이 특성을 메서드에 배치해 봅니다.  
  
 CLS 규격 규칙이 메서드 및 형식 선언에 적용되므로 메서드 매개 변수가 CLS 규격에 대해 확인되지 않습니다.  
  
## 예제  
 다음 샘플에서는 CS3022를 생성합니다.  
  
```  
// CS3022.cs // compile with: /W:1 using System; [assembly: CLSCompliant(true)] [CLSCompliant(true)] public class C { public void F([CLSCompliant(true)] int i) { } public static void Main() { } }  
```