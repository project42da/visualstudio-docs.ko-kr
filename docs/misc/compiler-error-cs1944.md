---
title: "컴파일러 오류 CS1944 | Microsoft Docs"
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
  - "CS1944"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1944"
ms.assetid: e5e2c018-9a7e-48ee-8dd3-98e3553777c1
caps.latest.revision: 8
caps.handback.revision: 8
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1944
식 트리에는 안전하지 않은 포인터 연산을 사용할 수 없습니다.  
  
 <xref:System.Linq.Expressions.Expression%601.Compile%2A?displayProperty=fullName> 메서드가 확인할 수 있는 코드를 생성하는 데만 허용되므로 식 트리에서 포인터 형식을 지원하지 않습니다. 주석을 참조하세요.  
  
### 이 오류를 해결하려면  
  
1.  식 트리를 만들려는 경우 포인터 형식을 사용하지 않습니다.  
  
## 예제  
 다음 예제에서는 CS1944를 생성합니다.  
  
<CodeContentPlaceHolder>0</CodeContentPlaceHolder>  
 상황에 따라 식 트리에 포인터가 있어도 됩니다. 예를 들어, 다음 코드를 고려하세요.  
  
 `Expression<Func\<int*[], int*[]>) e = (int*[] i)=>i;`  
  
 포인터 형식인 형식 인수가 없으므로 이 코드는 유효한 식 트리입니다. 형식 인수는 포인터의 배열이며 배열은 포인터 형식이 아닙니다. 또한 식 트리의 본문은 모든 포인터로 어떤 위험한 작업도 수행하지 않습니다.  
  
## 참고 항목  
 [unsafe](/dotnet/csharp/language-reference/keywords/unsafe)