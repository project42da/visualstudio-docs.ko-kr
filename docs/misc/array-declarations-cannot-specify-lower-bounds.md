---
title: "배열 선언에는 하한을 지정할 수 없습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc30805"
  - "bc30805"
helpviewer_keywords: 
  - "BC30805"
ms.assetid: f2055387-f4dc-4366-89fb-d752929a0258
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 배열 선언에는 하한을 지정할 수 없습니다.
배열의 하한은 항상 0입니다. 코드를 읽기 쉽게 만들려면 0을 하한으로 지정할 수 있습니다. 그러나 다른 하한 값을 지정할 수 없습니다.  
  
 **오류 ID:** BC30805  
  
### 이 오류를 해결하려면  
  
-   총 요소 수보다 1만큼 적은 차원 배열입니다. 예를 들어 `Dim y(6)`은 `Dim x(3 To 9)`과 같은 크기\(7 요소\)를 갖습니다. 또한 `Dim y(0 To 6)`을 지정할 수도 있습니다.  
  
-   0이 아닌 하한으로 시뮬레이트하려면 오프셋을 사용합니다. 다음은 3\-9차원 배열을 시뮬레이트하는 예제입니다.  
  
    ```  
    Const offset As Integer = 3 Dim arrayIndex As Integer ' arrayIndex can vary between 3 and 9. Dim y(0 To 6) ' The preceding statement allocates the same number of elements ' as Dim y(3 To 9). y(arrayIndex - offset) = value ' The preceding statement converts arrayIndex to the ' corresponding index of y.  
    ```  
  
## 참고 항목  
 [배열](/dotnet/visual-basic/programming-guide/language-features/arrays/index)   
 [Array Dimensions in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/arrays/array-dimensions)   
 [NOTINBUILD 방법: 배열에서 0 하한 지정](http://msdn.microsoft.com/ko-kr/20ffd49a-64f7-4634-8ed0-46ba1049d935)