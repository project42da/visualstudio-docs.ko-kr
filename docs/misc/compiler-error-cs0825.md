---
title: "컴파일러 오류 CS0825 | Microsoft Docs"
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
  - "CS0825"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0825"
ms.assetid: 49393d23-ec5f-4b44-a3fd-7e0a95ac0edd
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0825
상황별 키워드 'var'는 지역 변수 선언에만 표시할 수 있습니다.  
  
 `var` 키워드를 사용한 암시적 형식화는 로컬 메서드 범위의 변수에만 적용할 수 있습니다.  
  
### 이 오류를 해결하려면  
  
1.  변수가 클래스 범위에 속하는 경우 명시적 형식을 지정합니다.  그렇지 않으면 사용되는 메서드 내부로 이동합니다.  
  
## 예제  
 다음 코드에서는 `var`가 클래스 필드에서 사용되었기 때문에 CS0825를 생성합니다.  
  
```  
// cs0825.cs class Test { private var myField; //CS0825 static int Main() { var a = 1; // var is OK here return -1; } }  
```  
  
## 참고 항목  
 [암시적으로 형식화한 지역 변수](/dotnet/csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables)