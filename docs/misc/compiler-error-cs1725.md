---
title: "컴파일러 오류 CS1725 | Microsoft Docs"
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
  - "cs1725"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1725"
ms.assetid: baef9ae3-b036-41d6-972c-9f3cdae1e8bd
caps.latest.revision: 5
caps.handback.revision: 5
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1725
Friend 어셈블리 참조 'reference'가 잘못되었습니다. InternalsVisibleTo 선언에는 버전, 문화권, 공개 키 토큰 또는 프로세서 아키텍처를 지정할 수 없습니다.  
  
 Friend 어셈블리 참조에 버전 문화권을 추가할 수 없습니다. Partial 클래스는 friend 어셈블리에 표시되어야 합니다.  
  
## 예제  
 다음 샘플에서는 CS1725를 생성합니다.  
  
```  
// CS1725.cs // compile with: /target:library using System.Runtime.CompilerServices; [assembly:InternalsVisibleTo("partial01,version=1.1.0.0")]   // CS1725 // try the following line instead // [assembly:InternalsVisibleTo("partial01")] partial class TestClass { public static string strBar = "my string"; }  
```  
  
## 참고 항목  
 [방법: 서명된 Friend 어셈블리 만들기](../Topic/How%20to:%20Create%20Signed%20Friend%20Assemblies%20\(C%23%20and%20Visual%20Basic\).md)