---
title: "컴파일러 오류 CS0316 | Microsoft Docs"
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
  - "CS0316"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0316"
ms.assetid: 8b70abbe-dd4f-473f-8dfe-f8309abef276
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0316
매개 변수 이름 'name'이 자동으로 생성된 매개 변수 이름과 충돌합니다.  
  
 예약된 단어를 매개 변수 이름으로 사용할 수 없습니다. 다음에 나오는 예제에서 `value`는 기본 속성 또는 인덱서 접근자의 컨텍스트에서 예약어입니다.  
  
### 이 오류를 해결하려면  
  
1.  매개 변수의 이름을 변경합니다.  
  
## 예제  
 다음 코드에서는 CS0316을 생성합니다.  
  
```  
// cs0316.cs // Compile with: /target:library public class Test { public int this[int value] // CS0316 { get { return 1; } set { } } }  
```  
  
## 참고 항목  
 [인덱서](/dotnet/csharp/programming-guide/indexers/index)   
 [C\# 키워드](/dotnet/csharp/language-reference/keywords/index)