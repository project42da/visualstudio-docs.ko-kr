---
title: "컴파일러 오류 CS0412 | Microsoft Docs"
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
  - "CS0412"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0412"
ms.assetid: eeb2afbc-9416-4bcf-b116-d6adc5cfd4ca
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0412
'generic': 매개 변수 또는 지역 변수에는 메서드 형식 매개 변수와 같은 이름을 사용할 수 없습니다.  
  
 제네릭 메서드의 형식 매개 변수와 메서드 또는 메서드의 매개 변수 중 하나의 지역 변수 간에 이름 충돌이 발생합니다. 이 오류를 방지하려면 모든 충돌하는 매개 변수 또는 지역 변수의 이름을 바꿉니다.  
  
## 예제  
 다음 샘플에서는 CS0412를 생성합니다.  
  
```  
// CS0412.cs using System; class C { // Parameter name is the same as method type parameter name public void G<T>(int T)  // CS0412 { } public void F<T>() { // Method local variable name is the same as method type // parameter name double T = 0.0;  // CS0412 Console.WriteLine(T); } public static void Main() { } }  
```