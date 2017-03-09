---
title: "컴파일러 오류 CS1913 | Microsoft Docs"
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
  - "CS1913"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1913"
ms.assetid: 652494b3-9576-4a4c-a9ee-695f86c4a023
caps.latest.revision: 7
caps.handback.revision: 7
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1913
'name' 멤버를 초기화할 수 없습니다. 필드 또는 속성이 아닙니다.  
  
 개체 이니셜라이저는 액세스할 수 있는 필드 또는 속성 초기화에만 사용할 수 있습니다.  
  
### 이 오류를 해결하려면  
  
1.  정규 생성자 또는 다른 초기화 메서드에서 클래스 멤버를 초기화합니다.  
  
## 예제  
 다음 예제에서는 CS1913을 생성합니다.  
  
```  
// cs1912.cs class A { public delegate void D(); public event D myEvent; } public class Test { static void Main() { A a = new A() {myEvent = M}; // CS1913 } public void M(){} }  
```  
  
## 참고 항목  
 [클래스 및 구조체](/dotnet/csharp/programming-guide/classes-and-structs/index)