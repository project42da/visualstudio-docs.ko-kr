---
title: "컴파일러 오류 CS0082 | Microsoft Docs"
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
  - "CS0082"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS0082"
ms.assetid: 7612976f-de2c-4f6b-87c9-43175821650c
caps.latest.revision: 6
caps.handback.revision: 6
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS0082
'type' 형식에서 매개 변수 형식이 같은 'name' 멤버를 이미 예약했습니다.  
  
 컴파일 시간의 속성이 `get_` 및\/또는 `set_`가 식별자 앞에 있는 메서드로 변환됩니다. 메서드 이름과 충돌하는 사용자 고유의 메서드를 정의하면 오류가 생성됩니다.  
  
## 예제  
 다음 예제에서는 CS0082를 생성합니다.  
  
```  
//cs0082.cs class MyClass { //property public int MyProp { get //CS0082 { return 1; } } //conflicting Get public int get_MyProp() { return 2; } public static int Main() { return 1; } }  
```  
  
## 참고 항목  
 [속성](/dotnet/csharp/programming-guide/classes-and-structs/properties)