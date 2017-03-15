---
title: "컴파일러 경고(수준 1) CS3015 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS3015"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS3015"
ms.assetid: 58182215-0c2f-4497-8baf-ffb29f18d6c7
caps.latest.revision: 9
caps.handback.revision: 9
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 경고(수준 1) CS3015
'method signature'에는 CLS 규격 형식만 사용하는 액세스 가능 생성자가 없습니다.  
  
 CLS\(공용 언어 사양\)를 따르려면 특성 클래스의 인수 목록이 배열을 포함할 수 없습니다. CLS 규격에 대한 자세한 내용은 [CLS 규격 코드 작성](http://msdn.microsoft.com/ko-kr/4c705105-69a2-4e5e-b24e-0633bc32c7f3) 및 [언어 독립성 및 언어 독립적 구성 요소](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md)을 참조하세요.  
  
## 예제  
 다음 샘플에서는 C3015를 생성합니다.  
  
```  
// CS3015.cs // compile with: /target:library using System; [assembly:CLSCompliant(true)] public class MyAttribute : Attribute { public MyAttribute(int[] ai) {}   // CS3015 // try the following line instead // public MyAttribute(int ai) {} }  
```