---
title: "변수와 그 형식 모두에 null 허용 한정자 &#39;?&#39;와 배열 한정자 &#39;(&#39; 및 &#39;)&#39;를 지정할 수 없습니다. | Microsoft Docs"
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
  - "vbc33102"
  - "bc33102"
helpviewer_keywords: 
  - "BC33102"
ms.assetid: fd3f65a4-63f9-41dc-ba15-98d86f097ba8
caps.latest.revision: 5
caps.handback.revision: 5
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 변수와 그 형식 모두에 null 허용 한정자 &#39;?&#39;와 배열 한정자 &#39;(&#39; 및 &#39;)&#39;를 지정할 수 없습니다.
nullable 형식 한정자\(?\)가 지정된 변수 형식에 배열 한정자\(괄호\)를 포함하는 변수 선언의 변수에 포함되어 있습니다. 또는 nullable 형식 한정자가 변수에 배열 한정자를 포함하는 변수 선언의 지정된 변수 형식에 포함되어 있습니다.  
  
 **오류 ID:** BC33102  
  
### 이 오류를 해결하려면  
  
1.  다음 예제와 같이 nullable 형식 한정자\(?\)와 배열 한정자\(괄호\) 모두를 선언된 변수 또는 지정된 변수 형식에서 지정합니다.  
  
    ```vb#  
    ' These are incorrect. ' Dim numbers? As Integer() ' Dim values() As Integer? 'These are correct. Dim numbers?() As Integer Dim values As Integer?()  
    ```  
  
## 참고 항목  
 [Nullable Value Types](/dotnet/visual-basic/programming-guide/language-features/data-types/nullable-value-types)