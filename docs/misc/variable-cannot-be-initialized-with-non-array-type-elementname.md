---
title: "배열이 아닌 형식 &#39;&lt;elementname&gt;&#39;을 사용하여 변수를 초기화할 수 없습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc36536"
  - "bc36536"
helpviewer_keywords: 
  - "BC36536"
ms.assetid: 959415de-164e-4971-aab0-faad315753e9
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 배열이 아닌 형식 &#39;&lt;elementname&gt;&#39;을 사용하여 변수를 초기화할 수 없습니다.
배열로 선언된 변수는 배열 값으로 초기화되어야 합니다.  
  
```  
' Not valid. ' The following line causes this error when executed with Option Strict off. ' Dim arrayVar1() = 10  
```  
  
 **오류 ID:** BC36536  
  
### 이 오류를 해결하려면  
  
-   배열 값으로 배열 변수를 초기화합니다.  
  
    ```  
    ' With Option Strict off. Dim arrayVar2() = {1, 2, 3} ' With Option Strict on. Dim arrayVar3() As Integer = {1, 2, 3}  
    ```  
  
## 참고 항목  
 [NOTINBUILD 배열 변수](http://msdn.microsoft.com/ko-kr/c2da78bd-6928-46ba-805f-44f819dfaf93)