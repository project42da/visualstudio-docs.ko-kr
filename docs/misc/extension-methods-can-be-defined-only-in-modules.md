---
title: "확장 메서드는 모듈에만 정의할 수 있습니다. | Microsoft Docs"
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
  - "vbc36551"
  - "bc36551"
helpviewer_keywords: 
  - "BC36551"
ms.assetid: c832d523-5bf6-4baf-b91c-bd26d94453ed
caps.latest.revision: 22
caps.handback.revision: 22
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 확장 메서드는 모듈에만 정의할 수 있습니다.
이 오류는 확장 메서드가 모듈 외부에서 정의된 경우에 발생합니다. Visual Basic에서 모든 확장 메서드는 표준 모듈 내에서 정의되어야 합니다.  
  
 **오류 ID:** BC36551  
  
### 이 오류를 해결하려면  
  
-   확장 메서드를 모듈에 배치합니다.  
  
## 예제  
 다음 예제에서는 `Print` 메서드를 추가하여 `String` 클래스를 확장합니다.  
  
```  
Imports StringUtility Imports System.Runtime.CompilerServices Namespace StringUtility <Extension()> _ Module StringExtensions <Extension()> _ Public Sub Print (ByVal str As String) Console.WriteLine(str) End Sub End Module End Namespace  
```  
  
## 참고 항목  
 [빌드에 없음: 특성 적용](http://msdn.microsoft.com/ko-kr/2b1703ed-4437-49b3-bc0b-568094324f47)   
 [확장 메서드](/dotnet/visual-basic/programming-guide/language-features/procedures/extension-methods)   
 [Module \<keyword\>](../Topic/Module%20%3Ckeyword%3E%20\(Visual%20Basic\).md)   
 [Module Statement](/dotnet/visual-basic/language-reference/statements/module-statement)