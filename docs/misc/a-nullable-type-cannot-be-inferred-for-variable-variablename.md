---
title: "&#39;&lt;variablename&gt;&#39; 변수에 대해 nullable 형식을 유추할 수 없습니다. | Microsoft Docs"
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
  - "bc36628"
  - "vbc36628"
helpviewer_keywords: 
  - "BC36628"
ms.assetid: 3e92ae19-6a19-4b0b-9dd9-fba31cdb85a6
caps.latest.revision: 5
caps.handback.revision: 5
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;variablename&gt;&#39; 변수에 대해 nullable 형식을 유추할 수 없습니다.
배열, 클래스, `String` 등의 참조 형식에서 nullable 형식을 유추할 수 없습니다. 데이터 형식이 유추된 값은 값 형식이어야 합니다. 다음 코드에서는 이 오류를 보여 줍니다.  
  
```vb#  
'' Not valid.   
'Dim arrList? = New ArrayList  
'Dim except? = New Exception  
'Dim obj? = New Object  
'Dim stringVar? = "Open the application."  
  
' Valid.  
Dim intVar? = 10  
```  
  
 **오류 ID:** BC36628  
  
### 이 오류를 해결하려면  
  
-   nullable 지정을 제거합니다.  
  
## 참고 항목  
 [Nullable Value Types](/dotnet/visual-basic/programming-guide/language-features/data-types/nullable-value-types)