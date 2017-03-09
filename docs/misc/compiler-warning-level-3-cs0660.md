---
title: "컴파일러 경고(수준 3) CS0660 | Microsoft Docs"
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
  - "CS0660"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0660"
ms.assetid: 2f77b45b-c5c6-46af-abe9-002e67887896
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 3) CS0660
'class'는 \=\= 연산자 또는 \!\= 연산자를 정의하지만 Object.Equals\(object o\)를 재정의하지 않습니다.  
  
 컴파일러에서 사용자 정의 같음 또는 같지 않음 연산자는 검색했지만 **Equals** 함수에 대한 재정의는 검색하지 못했습니다. 사용자 정의 같음 또는 같지 않음 연산자는 **Equals** 함수 역시 재정의하고자 함을 나타냅니다. 자세한 내용은 [NIB \- Equals\(\) 및 연산자 \=\= 재정의에 대한 지침\(C\# 프로그래밍 가이드\)](http://msdn.microsoft.com/ko-kr/7e4c24c5-7693-4c45-88fb-ba5204fbcb20)을 참조하세요.  
  
 다음 샘플에서는 CS0660을 생성합니다.  
  
```  
// CS0660.cs // compile with: /W:3 /warnaserror class Test   // CS0660 { public static bool operator == (object o, Test t) { return true; } // uncomment the Equals function to resolve // public override bool Equals(object o) // { //    return true; // } public override int GetHashCode() { return 0; } public static void Main() { } }  
```