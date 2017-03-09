---
title: "배열 하한으로는 &#39;0&#39;만 사용할 수 있습니다. | Microsoft Docs"
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
  - "bc32059"
  - "vbc32059"
helpviewer_keywords: 
  - "BC32059"
ms.assetid: 273b69df-910e-45d2-acac-632005d24c5a
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 배열 하한으로는 &#39;0&#39;만 사용할 수 있습니다.
선언 문 또는 `New` 절에서 0이 아닌 하한을 가진 배열을 지정합니다.  
  
 배열 변수를 만들거나 초기화할 때 선택적으로 각 차원의 상한을 지정할 수 있습니다. 이렇게 하면 하한은 항상 0이기 때문에 해당 차원의 길이는 상한에 1을 더한 값이 됩니다. 선택적으로 하한도 지정할 수 있지만 0을 지정해야 합니다. 이렇게 할 때의 이점은 코드를 보다 쉽게 읽을 수 있다는 것입니다.  
  
 **오류 ID:** BC32059  
  
### 이 오류를 해결하려면  
  
-   하한 지정을 0으로 변경하거나 완전히 제거합니다.  
  
## 참고 항목  
 [배열](/dotnet/visual-basic/programming-guide/language-features/arrays/index)   
 [NOTINBUILD 방법: 배열에서 0 하한 지정](http://msdn.microsoft.com/ko-kr/20ffd49a-64f7-4634-8ed0-46ba1049d935)