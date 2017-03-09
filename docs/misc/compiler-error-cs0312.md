---
title: "컴파일러 오류 CS0312 | Microsoft Docs"
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
  - "CS0312"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0312"
ms.assetid: 552db0ae-2ecf-4beb-9606-bbe58e5708f6
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0312
제네릭 형식 또는 메서드 'name'에서 'type1' 형식을 형식 매개 변수 'name'으로 사용할 수 없습니다. nullable 형식 'type1'이 'type2'의 제약 조건을 만족하지 않습니다.  
  
 nullable 형식이 비 nullable 형식과 구분됩니다. 둘 사이에 암시적 참조 변환 또는 식별 변환이 존재하지 않습니다. nullable boxing 변환이 제네릭 형식 제약 조건을 만족하지 않습니다. 다음 예제에서 첫 번째 형식 매개 변수는 `Nullable<int>`이고 두 번째 형식 매개 변수는 `System.Int32`입니다.  
  
### 이 오류를 해결하려면  
  
1.  제약 조건을 제거합니다.  
  
2.  다음 예제에서 두 번째 형식 인수를 `int?` 또는 `object`로 만듭니다.  
  
## 예제  
 다음 코드에서는 CS0312를 생성합니다.  
  
```  
// cs0312.cs class Program { static void MTyVar<T, U>() where T : U { } static int Main() { MTyVar<int?, int>(); // CS0312 return 1; } }  
```  
  
 nullable 형식이 비 nullable 형식과 구분되지만 nullable 값과 비 nullable 값 간에 다양한 변환이 허용됩니다.  
  
## 참고 항목  
 [nullable 형식](/dotnet/csharp/programming-guide/nullable-types/index)