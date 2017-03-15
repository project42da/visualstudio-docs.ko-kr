---
title: "컴파일러 오류 CS0821 | Microsoft Docs"
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
  - "CS0821"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0821"
ms.assetid: ef449115-93e8-4fa5-848a-d30dc7f68ddf
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0821
암시적 형식 지역 변수는 fixed일 수 없습니다.  
  
 암시적 형식 지역 변수 및 무명 형식은 `fixed` 컨텍스트에서 지원되지 않습니다.  
  
### 이 오류를 해결하려면  
  
1.  `fixed` 한정자를 변수에서 제거하거나 변수에 명시적 형식을 지정합니다.  
  
## 예제  
 다음 코드에서는 CS0821을 생성합니다.  
  
```  
class A { static int x; public static int Main() { unsafe { fixed (var p = &x) { } } return -1; } }  
```  
  
## 참고 항목  
 [암시적으로 형식화한 지역 변수](/dotnet/csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables)