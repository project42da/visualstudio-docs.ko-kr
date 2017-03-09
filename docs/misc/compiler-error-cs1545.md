---
title: "컴파일러 오류 CS1545 | Microsoft Docs"
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
  - "CS1545"
dev_langs: 
  - "CSharp"
helpviewer_keywords: 
  - "CS1545"
ms.assetid: 56c377b5-4cf1-4c7d-b51d-463bad78f3ef
caps.latest.revision: 16
caps.handback.revision: 16
author: "BillWagner"
ms.author: "wiwagn"
manager: "wpickett"
---
# 컴파일러 오류 CS1545
'property' 속성, 인덱서 또는 이벤트는 이 언어에서 지원되지 않습니다. 'set accessor' 또는 'get accessor' 접근자 메서드를 직접 호출해 보세요.  
  
 코드가 기본이 아닌 [인덱서](/dotnet/csharp/programming-guide/indexers/index)가 있는 개체를 사용하여 인덱싱된 구문을 사용하려고 합니다. 이 오류를 해결하려면 속성의 `get` 또는 `set` 접근자 메서드를 호출하세요.  
  
## 예제  
  
```  
// CPP1545.cpp // compile with: /clr /LD // a Visual C++ program using namespace System; public ref struct Employee { Employee( String^ s, int d ) {} property String^ name { String^ get() { return nullptr; } } }; public ref struct Manager { property Employee^ Report [String^] { Employee^ get(String^ s) { return nullptr; } void set(String^ s, Employee^ e) {} } };  
```  
  
## 예제  
 다음 샘플에서는 CS1545를 생성합니다.  
  
```  
// CS1545.cs // compile with: /r:CPP1545.dll class x { public static void Main() { Manager Ed = new Manager(); Employee Bob = new Employee("Bob Smith", 12); Ed.Report[ Bob.name ] = Bob;   // CS1545 Ed.set_Report( Bob.name, Bob);   // OK } }  
```