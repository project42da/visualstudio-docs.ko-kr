---
title: "형식 또는 &#39;New&#39;가 필요합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc32092"
  - "bc32092"
helpviewer_keywords: 
  - "BC32092"
ms.assetid: b3041c1d-837c-4d58-bbb4-5c46f227b66d
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 형식 또는 &#39;New&#39;가 필요합니다.
제네릭 형식 선언의 형식 매개 변수에서 `As` 키워드가 있는 제약 조건 목록을 지정하지만 유효한 제약 조건을 지정하지 않습니다.  
  
 형식 매개 변수에 대한 제약 조건은 유효한 클래스 또는 인터페이스이거나 `Class`, `Structure` 또는 `New` 키워드 중 하나여야 합니다. 잘못된 제약 조건을 지정하거나 키워드를 지정하지 않으면 컴파일러가 이 오류를 생성합니다.  
  
 **오류 ID:** BC32092  
  
### 이 오류를 해결하려면  
  
1.  형식 매개 변수를 제약하는 방법을 확인하고 제약 조건 목록에서 적절한 제약 조건을 지정합니다.  
  
2.  클래스 또는 인터페이스로 형식 매개 변수를 제약하려면 해당 제약 조건에 이름을 정확하게 지정해야 합니다.  
  
3.  단일 형식 매개 변수에서 여러 제약 조건을 쉼표로 구분하고 해당 제약 조건 목록을 중괄호\(`{ }`\)로 묶어야 합니다.  
  
## 참고 항목  
 [Visual Basic의 제네릭 형식](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)   
 [클래스\(Visual Basic\)](http://msdn.microsoft.com/ko-kr/0777c6e6-46bc-451b-ad70-57b49d4ef4f7)   
 [구조체\(Visual Basic\)](http://msdn.microsoft.com/ko-kr/263ce115-ac36-4c05-8cb7-0e0eead5c6d0)   
 [New Operator](/dotnet/visual-basic/language-reference/operators/new-operator)   
 [Type List](/dotnet/visual-basic/language-reference/statements/type-list)