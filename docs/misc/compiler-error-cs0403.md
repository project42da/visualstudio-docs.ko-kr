---
title: "컴파일러 오류 CS0403 | Microsoft Docs"
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
  - "CS0403"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0403"
ms.assetid: 6e5d55ce-d6bf-419d-aded-aaa2e5963bb6
caps.latest.revision: 14
caps.handback.revision: 14
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0403
null을 허용하지 않는 값 형식일 수 있으므로 null을 형식 매개 변수 'name'으로 변환할 수 없습니다. 대신 default\('T'\)를 사용하세요.  
  
 null 할당을 허용하지 않는 값 형식일 수 있으므로 명명된 알 수 없는 형식에 null을 할당할 수 없습니다. 제네릭 클래스에서 값 형식을 사용할 수 없는 경우 클래스 형식 제약 조건을 사용합니다. 기본 제공 형식 등의 값 형식을 사용할 수 있는 경우 다음 예제와 같이 null로 할당을 `default(T)` 식으로 바꿀 수도 있습니다.  
  
## 예제  
 다음 샘플에서는 CS0403을 생성합니다.  
  
```  
// CS0403.cs // compile with: /target:library class C<T> { public void f() { T t = null;  // CS0403 T t2 = default(T);   // OK } } class D<T> where T : class { public void f() { T t = null;  // OK } }  
```