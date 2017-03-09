---
title: "컴파일러 경고(수준 3) CS0693 | Microsoft Docs"
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
  - "CS0693"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0693"
ms.assetid: a3902336-49db-4808-b41f-8f0936bff53a
caps.latest.revision: 10
caps.handback.revision: 10
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 3) CS0693
'type parameter' 형식 매개 변수가 'type' 외부 형식의 형식 매개 변수와 이름이 같습니다.  
  
 이 오류는 제네릭 클래스 내의 메서드와 같은 제네릭 멤버가 있는 경우에 발생합니다. 메서드의 형식 매개 변수가 반드시 클래스의 형식 매개 변수와 동일한 것은 아니므로 둘 다에 같은 이름을 제공할 수 없습니다. 자세한 내용은 [제네릭 메서드](/dotnet/csharp/programming-guide/generics/generic-methods)을 참조하세요.  
  
 이 상황을 피하려면 형식 매개 변수 중 하나에 대해 다른 이름을 사용합니다.  
  
## 예제  
 다음 샘플에서는 CS0693을 생성합니다.  
  
```  
// CS0693.cs // compile with: /W:3 /target:library class Outer<T> { class Inner<T> {}   // CS0693 // try the following line instead // class Inner<U> {} }  
```