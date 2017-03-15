---
title: "컴파일러 경고(수준 3) CS0659 | Microsoft Docs"
ms.custom: ""
ms.date: "12/13/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS0659"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0659"
ms.assetid: 63435ee6-c92f-4124-95d4-d8f4e5f0af80
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 3) CS0659
'class'는 Object.Equals\(object o\)를 재정의하지만 Object.GetHashCode\(\)를 재정의하지 않습니다.  
  
 컴파일러에서 **Equals** 함수의 재정의는 검색했지만 **GetHashCode**에 대한 재정의는 검색하지 못했습니다.**Equals**의 재정의는 **GetHashCode** 역시 재정의하고자 함을 나타냅니다.  
  
 詳細については、次のトピックを参照してください。  
  
-   <xref:System.Collections.Hashtable>.  
  
-   [같음 연산자](../Topic/Equality%20Operators.md)  
  
-   [NIB: Equals 메서드 구현](http://msdn.microsoft.com/ko-kr/30f28aaf-8b9e-46cd-a746-58a12473af2c)  
  
-   <xref:System.Object.GetHashCode%2A>  
  
 다음 샘플에서는 CS0659를 생성합니다.  
  
```  
// CS0659.cs // compile with: /W:3 /target:library class Test { public override bool Equals(object o) { return true; }   // CS0659 } // OK class Test2 { public override bool Equals(object o) { return true; } public override int GetHashCode() { return 0; } }  
```