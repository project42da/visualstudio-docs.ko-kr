---
title: "컴파일러 오류 CS0828 | Microsoft Docs"
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
  - "CS0828"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0828"
ms.assetid: e18ffe72-2fcc-436d-be7f-8c8365b86129
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0828
무명 형식 속성에는 'expression'을 할당할 수 없습니다.  
  
 무명 형식은 null 값, 안전하지 않은 형식, 메서드 그룹 또는 익명 함수를 사용하여 초기화할 수 없습니다.  
  
### 이 오류를 해결하려면  
  
1.  형식 선언을 할당의 왼쪽에 추가하거나 오른쪽에서 식을 변경하여 허용 가능한 형식을 갖도록 합니다.  
  
## 예제  
 다음 코드에서는 null 값을 사용하여 무명 형식의 멤버를 초기화할 수 없으므로 CS0828을 생성합니다.  
  
```  
// cs0828.cs using System; public class C { public static int Main() { var a = 1; var c = new { p1 = null }; // CS0828 return 1; } }  
```  
  
## 참고 항목  
 [암시적으로 형식화한 지역 변수](/dotnet/csharp/programming-guide/classes-and-structs/implicitly-typed-local-variables)