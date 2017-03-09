---
title: "컴파일러 오류 CS0221 | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS0221"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0221"
ms.assetid: 97170b49-54f1-4dac-a865-2f9cc6bf55b1
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0221
'value' 상수 값은 'type'으로 변환할 수 없습니다. 재정의하려면 'unchecked' 구문을 사용하세요.  
  
 데이터 손실을 초래하는 할당 작업이 기본적으로 켜져 있는 [checked](/dotnet/csharp/language-reference/keywords/checked)에 의해 발견되었습니다. 이 오류를 해결하려면 할당을 수정하거나 [unchecked](/dotnet/csharp/language-reference/keywords/unchecked)를 사용합니다. 자세한 내용은 [Checked 및 Unchecked](/dotnet/csharp/language-reference/keywords/checked-and-unchecked)을 참조하세요.  
  
 다음 샘플에서는 CS0221을 생성합니다.  
  
```  
// CS0221.cs public class MyClass { public static void Main() { // unchecked // { int a = (int)0xFFFFFFFF;   // CS0221 a++; // } } }  
```