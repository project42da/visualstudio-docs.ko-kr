---
title: "확장 메서드는 하나 이상의 매개 변수를 선언해야 합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc36552"
  - "bc36552"
helpviewer_keywords: 
  - "BC36552"
ms.assetid: a8cc8cdd-cdb5-42ca-b5a1-c9a71abd46eb
caps.latest.revision: 15
caps.handback.revision: 15
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 확장 메서드는 하나 이상의 매개 변수를 선언해야 합니다.
확장 메서드는 하나 이상의 매개 변수를 선언해야 합니다. 첫 번째 매개 변수는 확장할 형식을 지정합니다.  
  
 첫 번째 매개 변수가 메서드가 확장하는 데이터 형식을 지정하므로 매개 변수가 없는 확장 메서드는 올바르지 않습니다. 첫 번째 매개 변수는 메서드를 호출하는 데이터 형식의 인스턴스에 바인딩됩니다.  
  
 **오류 ID:** BC36552  
  
### 이 오류를 해결하려면  
  
-   메서드에서 확장하는 형식의 매개 변수를 추가합니다.  
  
## 예제  
 다음 예제에서 첫 번째 매개 변수는 `Print` 메서드가 `String` 데이터 형식을 확장하는 것을 나타냅니다.  
  
```  
<Extension()> _ Public Sub Print (ByVal str As String) Console.WriteLine(str) End Sub  
```  
  
 확장 메서드가 다음과 같이 호출되는 경우 메서드의 `str` 매개 변수는 `Print`를 호출하는 `String`의 인스턴스인 `greeting`에 바인딩됩니다. 컴파일러에서는 `greeting`을 확장 메서드 `Print`의 인수로 사용합니다.  
  
```  
Dim greeting As String = "Hello" greeting.Print()  
```  
  
## 참고 항목  
 [확장 메서드](/dotnet/visual-basic/programming-guide/language-features/procedures/extension-methods)   
 [Procedure Parameters and Arguments](/dotnet/visual-basic/programming-guide/language-features/procedures/procedure-parameters-and-arguments)   
 [Procedures](/dotnet/visual-basic/programming-guide/language-features/procedures/index)