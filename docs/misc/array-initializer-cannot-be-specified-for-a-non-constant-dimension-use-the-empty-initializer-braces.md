---
title: "비상수 차원에는 배열 이니셜라이저를 지정할 수 없습니다. 빈 이니셜라이저 &#39;{}&#39;를 사용하세요. | Microsoft Docs"
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
  - "vbc30949"
  - "bc30949"
helpviewer_keywords: 
  - "BC30949"
ms.assetid: b3d27d9c-7a1f-4bac-ad71-388b24b807b3
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 비상수 차원에는 배열 이니셜라이저를 지정할 수 없습니다. 빈 이니셜라이저 &#39;{}&#39;를 사용하세요.
배열에서 컴파일 시간에 알려지지 않은 차원을 초기화합니다.  
  
 다음 코드에서는 이 오류를 생성합니다.  
  
```  
Dim j As Integer Dim intArray As Integer = New Integer(1, j) {{0, 100}, {1,101}}  
```  
  
 다음 코드에서는 오류를 방지합니다.  
  
```  
Dim intArray As Integer = New Integer(1, j) {} For i As Integer = 0 To j intArray(0, i) = i intArray(1, i) = 100 + i Next i  
```  
  
 **오류 ID:** BC30949  
  
### 이 오류를 해결하려면  
  
-   가능하면 배열 선언에 상수 차원을 지정합니다.  
  
-   상수 차원을 지정할 수 없는 경우 비상수 차원이 알려질 때 루프를 사용하여 배열을 초기화해야 합니다.  
  
## 참고 항목  
 [For Each...Next 문](/dotnet/visual-basic/language-reference/statements/for-each-next-statement)   
 [NOTINBUILD Visual Basic의 배열 개요](http://msdn.microsoft.com/ko-kr/ca50e2f2-b4d2-4c57-9169-9abbcc3392d8)   
 [How to: Initialize an Array Variable in Visual Basic](../Topic/How%20to:%20Initialize%20an%20Array%20Variable%20in%20Visual%20Basic.md)   
 [NOTINBUILD 방법: 다차원 배열 초기화](http://msdn.microsoft.com/ko-kr/502dcf8b-d86c-46f1-ad7d-3ce809645774)