---
title: "컴파일러 오류 CS1928 | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CS1928"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1928"
ms.assetid: bcc9dbef-ded5-4ddd-8c03-a9837cb6d165
caps.latest.revision: 5
caps.handback.revision: 5
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1928
'Type'에 'method'에 대한 정의가 없으며 가장 적합한 확장 메서드 오버로드 'method'에 잘못된 인수가 있습니다.  
  
 이 오류는 컴파일러가 호출한 메서드의 이름을 가진 클래스 멤버를 찾을 수 없을 때 발생합니다. 해당 이름의 확장 메서드를 찾을 수 있지만, 이 확장 메서드에는 메서드 호출을 사용하여 전달한 형식과 일치하는 서명이 없습니다.  
  
### 이 오류를 해결하려면  
  
1.  기존 확장 메서드 또는 클래스 메서드와 일치하는 형식을 전달합니다.  
  
## 예제  
 다음 코드에서는 CS1928을 생성합니다.  
  
```  
// cs1928.cs class Test { static void Main() { Test t = new Test(); t.M("hi"); // CS1928 } } static class Ext { public static void M(this Test t, int i) { } }  
```  
  
 이 오류는 종종 CS1503와 함께 발생합니다. 인수 'n'은 'typeA'에서 'typeB'로 변환할 수 없습니다.  
  
## 참고 항목  
 [확장 메서드](/dotnet/csharp/programming-guide/classes-and-structs/extension-methods)