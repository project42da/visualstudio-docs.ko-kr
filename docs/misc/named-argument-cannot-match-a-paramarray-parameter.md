---
title: "명명된 인수는 ParamArray 매개 변수와 일치할 수 없습니다. | Microsoft Docs"
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
  - "bc30587"
  - "vbc30587"
helpviewer_keywords: 
  - "BC30587"
ms.assetid: aff179af-96f2-4157-971e-881d8e08f5f2
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 명명된 인수는 ParamArray 매개 변수와 일치할 수 없습니다.
명명된 인수\(콜론과 등호가 뒤에 있고 인수 값이 뒤에 있도록 선언된 인수 이름으로 지정\)를 제공했지만 매개 변수 배열을 이름으로 전달할 수 없습니다. 프로시저를 호출할 때 매개 변수 배열에 대해 쉼표로 구분하여 무한한 수의 인수를 제공하지만 컴파일러가 단일 이름에 둘 이상의 인수를 연결할 수 없습니다.  
  
 **오류 ID:** BC30587  
  
### 이 오류를 해결하려면  
  
-   이름보다는 위치로 인수를 전달합니다.  
  
## 참고 항목  
 [ParamArray](/dotnet/visual-basic/language-reference/modifiers/paramarray)   
 [Passing Arguments by Position and by Name](/dotnet/visual-basic/programming-guide/language-features/procedures/passing-arguments-by-position-and-by-name)