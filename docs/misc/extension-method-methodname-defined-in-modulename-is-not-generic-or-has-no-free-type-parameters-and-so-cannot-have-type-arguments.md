---
title: "&#39;&lt;modulename&gt;&#39;에 정의된 확장 메서드 &#39;&lt;methodname&gt;&#39;은 제네릭이 아니거나 형식이 자유로운 매개 변수를 포함하지 않으므로 형식 인수를 사용할 수 없습니다. | Microsoft Docs"
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
  - "bc36907"
  - "vbc36907"
helpviewer_keywords: 
  - "BC36907"
ms.assetid: 45191e93-89d1-48ec-99a5-ff9661a2a6ee
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;modulename&gt;&#39;에 정의된 확장 메서드 &#39;&lt;methodname&gt;&#39;은 제네릭이 아니거나 형식이 자유로운 매개 변수를 포함하지 않으므로 형식 인수를 사용할 수 없습니다.
제네릭 매개 변수가 없거나 형식이 아직 지정되지 않은 제네릭 매개 변수가 없는 확장 메서드 호출에서 형식 인수를 지정했습니다. 예를 들어 다음 코드에서는 이 오류를 생성합니다.  
  
```vb#  
' The extension method is not generic. <Extension()> _ Sub Example(ByVal str As String) ' Body of the Sub. End Sub  
```  
  
```vb#  
Dim str = "hi" '' The call to Example specifies a type argument. '' Not valid. 'str.Example(Of String)()  
```  
  
 **오류 ID:** BC36907  
  
### 이 오류를 해결하려면  
  
-   확장 메서드 정의에 형식 매개 변수를 추가합니다.  
  
-   프로시저 호출에서 다른 형식 인수를 제거합니다.  
  
## 참고 항목  
 [확장 메서드](/dotnet/visual-basic/programming-guide/language-features/procedures/extension-methods)   
 [Generic Procedures in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-procedures)