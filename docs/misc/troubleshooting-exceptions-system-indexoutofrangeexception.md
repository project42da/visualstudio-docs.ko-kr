---
title: "예외 문제 해결: System.IndexOutOfRangeException | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "JScript"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "IndexOutOfRangeException 클래스"
ms.assetid: 9e28623c-93fc-4111-a0cb-c380e0b5de0c
caps.latest.revision: 25
caps.handback.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 예외 문제 해결: System.IndexOutOfRangeException
<xref:System.IndexOutOfRangeException> 예외는 0보다 작거나 배열의 경계 바깥에 있는 인덱스를 사용하여 컬렉션이나 배열의 요소에 액세스하려는 경우에 throw됩니다.  
  
## 관련 팁  
 **목록의 최대 인덱스가 목록 크기보다 작은지 확인하십시오.**  
 목록의 최대 인덱스는 목록 크기보다 작아야 합니다.  
  
 **인덱스가 음수가 아닌지 확인하십시오.**  
 이 예외는 인덱스가 0보다 작은 경우에 throw됩니다.  
  
 **데이터 열 이름이 올바른지 확인하십시오.**  
 <xref:System.Data.DataView.Sort%2A?displayProperty=fullName> 속성에 제공한 데이터 열 이름이 올바르지 않으면 이 예외가 throw될 수 있습니다. 자세한 내용은 <xref:System.Data.DataView> 클래스를 참조하세요.  
  
## 예제  
  
### 설명  
 다음 예제에서는 `Try…Catch` 블록을 사용하여 인덱스 `IndexOutOfRangeException`가 배열 경계인 0~3을 벗어날 때 `i`을 트래핑합니다. 이 예제는 다음을 표시합니다.  
  
 `Element at index 0: 3`  
  
 `Element at index 2: 5`  
  
 `Element at index -1: IndexOutOfRangeException caught`  
  
 `Element at index 4: IndexOutOfRangeException caught`  
  
### 코드  
  
```vb#  
Module Module1 Sub Main() ' The first two tests will display the value of the array element. IndexTest(0) IndexTest(2) ' The following two calls will display the information that ' an IndexOutOfRangeException was caught. IndexTest(-1) IndexTest(4) End Sub Sub IndexTest(ByVal i As Integer) Dim testArray() As Integer = {3, 4, 5, 6} Console.Write("Element at index {0}: ", i) Try Console.WriteLine(testArray(i)) Catch ex As IndexOutOfRangeException Console.WriteLine("IndexOutOfRangeException caught") End Try End Sub End Module  
```  
  
## 참고 항목  
 <xref:System.IndexOutOfRangeException>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)   
 [배열](/dotnet/visual-basic/programming-guide/language-features/arrays/index)