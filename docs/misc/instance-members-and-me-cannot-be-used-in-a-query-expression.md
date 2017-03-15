---
title: "인스턴스 멤버와 &#39;Me&#39;는 쿼리 식에 사용할 수 없습니다. | Microsoft Docs"
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
  - "vbc36535"
  - "bc36535"
helpviewer_keywords: 
  - "BC36535"
ms.assetid: afb5281b-70a7-48c7-a46d-39522b96b1ff
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 인스턴스 멤버와 &#39;Me&#39;는 쿼리 식에 사용할 수 없습니다.
`Structure`의 LINQ 쿼리에는 `Me`에 대한 참조 또는 구조체의 인스턴스 멤버에 대한 참조가 있습니다.`Me` 또는 인스턴스 멤버에 대한 참조는 `Structure` 내의 쿼리 식에서 허용되지 않습니다.  
  
 **오류 ID:** BC36535  
  
### 이 오류를 해결하려면  
  
1.  다음 예제와 같이 `Me`에 대한 참조에서 반환된 값 또는 인스턴스 멤버의 복사본을 만들고 쿼리 식에서 복사본을 사용합니다.  
  
    ```vb#  
    Structure SampleStructure Public SearchValue As Integer Public Sub SetSearchValue(ByVal number As Integer) SearchValue = number End Sub Public Sub GetData() Dim sv = SearchValue Dim SampleData = New Integer() {1, 2, 3, 4} Dim query = From number In SampleData _ Where number < sv End Sub End Structure  
    ```  
  
## 참고 항목  
 [Introduction to LINQ in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/linq/introduction-to-linq)   
 [LINQ](/dotnet/visual-basic/programming-guide/language-features/linq/index)   
 [Me](http://msdn.microsoft.com/ko-kr/a65973c7-cf06-4547-9b25-9fba885525c2)   
 [구조체\(Visual Basic\)](http://msdn.microsoft.com/ko-kr/263ce115-ac36-4c05-8cb7-0e0eead5c6d0)