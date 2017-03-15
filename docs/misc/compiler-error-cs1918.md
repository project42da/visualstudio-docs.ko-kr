---
title: "컴파일러 오류 CS1918 | Microsoft Docs"
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
  - "CS1918"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1918"
ms.assetid: 9ad2cbbd-3c10-4d56-b4cd-385103d005d4
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1918
형식이 'type'인 'name' 속성의 멤버는 값 형식이므로 개체 이니셜라이저를 사용하여 할당할 수 없습니다.  
  
 이 오류는 개체 이니셜라이저를 사용하여 그 자체가 초기화되는 클래스의 속성인 구조체 형식의 속성을 초기화하려는 경우에 발생합니다.  
  
### 이 오류를 해결하려면  
  
1.  개체 이니셜라이저에서 속성의 필드를 완전히 초기화해야 하는 경우 구조체를 클래스 형식으로 변경합니다. 그렇지 않으면 개체 이니셜라이저를 사용하여 개체를 만든 후 별도 메서드 호출에서 구조체 멤버를 초기화합니다.  
  
## 예제  
 다음 예제에서는 CS1918을 생성합니다.  
  
```  
// cs1918.cs public struct MyStruct { public int i; } public class Test { private MyStruct str = new MyStruct(); public MyStruct Str { get { return str; } } public static int Main() { Test t = new Test { Str = { i = 1 } }; // CS1918 return 0; } }  
  
```  
  
## 참고 항목  
 [개체 및 컬렉션 이니셜라이저](/dotnet/csharp/programming-guide/classes-and-structs/object-and-collection-initializers)