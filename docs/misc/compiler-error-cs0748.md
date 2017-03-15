---
title: "컴파일러 오류 CS0748 | Microsoft Docs"
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
  - "CS0748"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0748"
ms.assetid: da1935af-a5ea-41f4-84ae-58559b750566
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0748
람다 매개 변수가 일관성 없이 사용되었습니다. 모든 매개 변수 형식은 명시적이거나 암시적이어야 합니다.  
  
 람다 식에 여러 개의 입력 매개 변수가 있는 경우 일부 매개 변수에서는 암시적 형식을 사용할 수 없는 반면 일부 매개 변수에서는 명시적 형식을 사용합니다.  
  
### 이 오류를 해결하려면  
  
1.  모든 입력 매개 변수에 대해 암시적 형식을 제공하거나 모두 명시적 형식을 제공합니다.  
  
## 예제  
 `alpha`에는 명시적 형식만 지정되므로 다음 코드는 람다 식에서 CS0748을 생성합니다.  
  
```  
// cs0748.cs class CS0748 { delegate double D(int x, int y); D d = (int alpha, beta) => { return beta / alpha; }; // CS0748 }  
```  
  
## 참고 항목  
 [람다 식](/dotnet/csharp/programming-guide/statements-expressions-operators/lambda-expressions)