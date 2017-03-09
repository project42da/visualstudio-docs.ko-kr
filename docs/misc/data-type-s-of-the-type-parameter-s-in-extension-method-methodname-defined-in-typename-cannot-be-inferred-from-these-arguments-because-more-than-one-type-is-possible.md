---
title: "두 개 이상의 형식이 가능하므로 이 인수에서 &#39;&lt;typename&gt;&#39;에 정의된 확장 메서드 &#39;&lt;methodname&gt;&#39;에 있는 형식 매개 변수의 데이터 형식을 유추할 수 없습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc36655"
  - "vbc36652"
  - "vbc36655"
  - "bc36652"
helpviewer_keywords: 
  - "BC36655"
  - "BC36652"
ms.assetid: 49836f20-c877-4267-8bdc-6f6d108fb8c0
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 두 개 이상의 형식이 가능하므로 이 인수에서 &#39;&lt;typename&gt;&#39;에 정의된 확장 메서드 &#39;&lt;methodname&gt;&#39;에 있는 형식 매개 변수의 데이터 형식을 유추할 수 없습니다.
두 개 이상의 형식이 가능하므로 이 인수에서 '\<typename\>'에 정의된 확장 메서드 '\<methodname\>'에 있는 형식 매개 변수의 데이터 형식을 유추할 수 없습니다. 데이터 형식을 명시적으로 지정하면 이 오류를 해결할 수 있습니다.  
  
 형식 유추를 사용하여 제네릭 확장 메서드 호출에서 형식 매개 변수의 형식을 확인하려고 했습니다. 컴파일러에서는 둘 이상의 형식 매개 변수에 가능한 데이터 형식을 둘 이상 찾고 이 오류를 보고합니다.  
  
> [!NOTE]
>  인수 지정이 옵션이 아닌 경우\(예: 쿼리 식의 쿼리 연산자\) 두 번째 문장 없이 오류 메시지가 나타납니다.  
  
 다음 코드에서는  오류를 보여 줍니다.  
  
```vb#  
Option Strict Off Imports System.Runtime.CompilerServices Module Module1 Sub Main() Dim caller As New Class1 '' Not valid. 'caller.targetExtension(1, "2") End Sub <Extension()> _ Sub targetExtension(Of T)(ByVal p0 As Class1, ByVal p1 As T, ByVal p2 As T) End Sub Class Class1 End Class End Module  
```  
  
 **오류 ID:** BC36655\([!INCLUDE[vbteclinq](../misc/includes/vbteclinq_md.md)] 쿼리 내부\) 및 BC36652\(쿼리 외부\)  
  
### 이 오류를 해결하려면  
  
-   쿼리 외부에서 오류가 나타난 경우 형식 매개 변수의 데이터 형식을 명시적으로 지정합니다.  
  
    ```  
    caller.targetExtension(Of Integer)(1, "2") caller.targetExtension(Of String)(1, "2")  
    ```  
  
## 참고 항목  
 [확장 메서드](/dotnet/visual-basic/programming-guide/language-features/procedures/extension-methods)   
 [Option Strict Statement](/dotnet/visual-basic/language-reference/statements/option-strict-statement)   
 [Generic Procedures in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-procedures)