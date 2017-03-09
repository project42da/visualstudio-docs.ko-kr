---
title: "컴파일러 오류 CS0119 | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS0119"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0119"
ms.assetid: 048924f1-378f-4021-bd20-299d3218f810
caps.latest.revision: 10
caps.handback.revision: 10
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0119
'construct1\_name'은 지정한 컨텍스트에서 유효하지 않은 'construct1'입니다.  
  
 컴파일러가 다음과 같은 예기치 않은 구문을 발견했습니다.  
  
-   클래스 생성자가 조건문에서 유효한 테스트 식이 아닙니다.  
  
-   배열 요소를 참조하기 위해 인스턴스 이름 대신 클래스 이름을 사용했습니다.  
  
-   메서드 식별자를 구조체 또는 클래스인 것처럼 사용합니다.  
  
## 예제  
 다음 샘플에서는 CS0119를 생성합니다.  
  
```  
// CS0119.cs using System; public class MyClass { public static void Test() {} public static void Main() { Console.WriteLine(Test.x);   // CS0119 } }  
```