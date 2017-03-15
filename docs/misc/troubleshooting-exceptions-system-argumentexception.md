---
title: "예외 문제 해결: System.ArgumentException | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "ArgumentException 예외"
  - "System.ArgumentException 예외"
ms.assetid: d8052e62-bc73-4828-87e9-a84ef2a39a5b
caps.latest.revision: 14
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# 예외 문제 해결: System.ArgumentException
<xref:System.ArgumentException> 예외는 메서드에 제공된 인수 중 메서드 매개 변수의 사양에 맞지 않는 인수가 최소한 하나 이상 있을 때 throw됩니다.  
  
 다음 예제에서는 `DivideByTwo` 메서드에 전달된 인수가 짝수가 아니면 예외가 throw됩니다.  
  
```vb#  
Module Module1 Sub Main() ' ArgumentException is not thrown in DivideByTwo because 10 is ' an even number. Console.WriteLine("10 divided by 2 is {0}", DivideByTwo(10)) Try ' ArgumentException is thrown in DivideByTwo because 7 is ' not an even number. Console.WriteLine("7 divided by 2 is {0}", DivideByTwo(7)) Catch argEx As ArgumentException ' Tell the user which problem is encountered. Console.WriteLine("7 cannot be evenly divided by 2.") Console.WriteLine("Exception message: " & argEx.Message) End Try ' Uncomment the next statement to see what happens if you call ' DivideByTwo directly. 'Console.WriteLine(DivideByTwo(7)) End Sub Function DivideByTwo(ByVal num As Integer) As Integer ' If num is an odd number, throw an ArgumentException. The ' ArgumentException class provides a number of constructors ' that you can choose from. If num Mod 2 = 1 Then Throw New ArgumentException("Argument for num must be" & _ " an even number.") End If ' Value of num is even, so return half of its value. Return num / 2 End Function End Module  
```  
  
 `ArgumentException` 클래스의 모든 인스턴스에는 유효하지 않은 인수 및 사용 가능한 값 범위를 지정하는 정보가 포함되어 있어야 합니다.<xref:System.ArgumentNullException> 또는 <xref:System.ArgumentOutOfRangeException> 등의 보다 구체적인 예외가 상황을 정확히 설명하는 경우 `ArgumentException` 대신 이러한 예외를 사용해야 합니다.  
  
 다른 언어로 작성된 예제를 비롯하여 이 예제에 대한 자세한 내용은 <xref:System.ArgumentException>을 참조하십시오. 추가 생성자의 목록을 보려면 <xref:System.ArgumentException.%23ctor%2A>을 참조하십시오.  
  
## 참고 항목  
 <xref:System.ArgumentException>   
 [Use the Exception Assistant](../Topic/How%20to:%20Use%20the%20Exception%20Assistant.md)