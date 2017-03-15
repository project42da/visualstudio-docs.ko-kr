---
title: "컴파일러 오류 CS1958 | Microsoft Docs"
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
  - "CS1958"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1958"
ms.assetid: bb6f3bb2-ea93-4d2e-984c-da9c99f5653f
caps.latest.revision: 5
caps.handback.revision: 5
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1958
개체 및 컬렉션 이니셜라이저 식은 대리자 생성 식에 적용할 수 없습니다.  
  
 대리자에 클래스 또는 구조체와 같은 멤버가 없으므로 개체 이니셜라이저가 초기화할 항목이 없습니다. 이 오류가 발생하는 경우 그 이유는 대리자 생성 식 뒤에 중괄호가 있기 때문일 수 있습니다. 중괄호만 제거하면 이 오류가 사라집니다.  
  
### 이 오류를 해결하려면  
  
1.  중괄호를 제거합니다.  
  
## 예제  
 다음 코드에서는 CS1958을 생성합니다.  
  
```  
// cs1958.cs public class MemberInitializerTest { delegate void D<T>(); public static void GenericMethod<T>() { } public static void Run() { D<int> genD = new D<int>(GenericMethod<int>) { }; // CS1958 // Try the following line instead // D<int> genD = new D<int>(GenericMethod<int>); } }  
```