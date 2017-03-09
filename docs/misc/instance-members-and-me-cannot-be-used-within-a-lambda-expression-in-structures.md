---
title: "인스턴스 멤버와 &#39;Me&#39;는 구조체의 람다 식에 사용할 수 없습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc36638"
  - "bc36638"
helpviewer_keywords: 
  - "BC36638"
ms.assetid: 5c24a7c7-50f6-4ffb-9ed2-07e2abc4eaf3
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 인스턴스 멤버와 &#39;Me&#39;는 구조체의 람다 식에 사용할 수 없습니다.
구조체 내에서 구조체의 인스턴스 멤버를 참조하거나 `Me`를 사용하는 람다 식을 정의했습니다. 다음 코드에서는 이러한 두 개의 잘못된 참조를 보여 줍니다.  
  
```vb#  
Structure Structure1 Public InstanceMember As Integer Public Function ExampleFun() As Integer '' The error is caused by use of InstanceMember. 'Dim fun1 = Function() InstanceMember '' The error is caused by use of Me. 'Dim fun2 = Function() Me.InstanceMember 'Return fun1() End Function End Structure  
```  
  
 **오류 ID:** BC36638  
  
### 이 오류를 해결하려면  
  
-   인스턴스 멤버를 지역 변수에 할당하고 문에서 지역 변수를 사용합니다.  
  
    ```vb#  
    Public Function ExampleFunFix() As Integer Dim temp = InstanceMember Dim fun1 = Function() temp Return fun1() End Function  
    ```  
  
## 참고 항목  
 [Lambda Expressions](/dotnet/visual-basic/programming-guide/language-features/procedures/lambda-expressions)   
 [Me](http://msdn.microsoft.com/ko-kr/a65973c7-cf06-4547-9b25-9fba885525c2)   
 [Structure Statement](/dotnet/visual-basic/language-reference/statements/structure-statement)