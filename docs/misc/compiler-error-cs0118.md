---
title: "컴파일러 오류 CS0118 | Microsoft Docs"
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
  - "CS0118"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0118"
ms.assetid: 9a612432-6e56-4e9b-9d8c-7d7b43f58c1a
caps.latest.revision: 13
caps.handback.revision: 13
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0118
'construct1\_name'은 'construct1'이지만 'construct2'처럼 사용되었습니다.  
  
 컴파일러에서 구문이 잘못된 방식으로 사용되었거나 구문에서 허용되지 않는 작업이 시도된 경우를 발견했습니다. 일반적인 몇 가지 예는 다음과 같습니다.  
  
-   클래스 대신 네임스페이스를 인스턴스화하려는 시도  
  
-   메서드 대신 필드를 호출하려는 시도  
  
-   형식을 변수로 사용하려는 시도  
  
-   extern 별칭을 형식으로 사용하려는 시도  
  
 이 오류를 해결하려면 수행 중인 작업이 작업을 수행하는 형식에 유효한지 확인합니다.  
  
## 예제  
 다음 샘플에서는 CS0118을 생성합니다.  
  
```  
// CS0118.cs // compile with: /target:library namespace MyNamespace { class MyClass { // MyNamespace not a class MyNamespace ix = new MyNamespace ();   // CS0118 } }  
```