---
title: "호출 식 또는 인덱스 식이 잘못되었습니다. | Microsoft Docs"
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
  - "vbc32303"
  - "bc32303"
helpviewer_keywords: 
  - "BC32303"
ms.assetid: eed6a16e-4a44-4f72-b1de-d4212940da37
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 호출 식 또는 인덱스 식이 잘못되었습니다.
괄호의 값이 프로시저, 속성 또는 배열이 아닌 식 뒤에 옵니다.  
  
 다음 코드에서는 이 오류를 생성할 수 있습니다.  
  
 `Dim testVariable As Object = Nothing(1)`  
  
 `Nothing`은 인수 또는 인덱스를 사용하지 않으므로 괄호와 함께 사용할 수 없습니다.  
  
 **오류 ID:** BC32303  
  
### 이 오류를 해결하려면  
  
-   괄호 및 괄호 안에 포함된 모든 값을 제거합니다.  
  
## 참고 항목  
 [How to: Call a Procedure That Returns a Value](../Topic/How%20to:%20Call%20a%20Procedure%20That%20Returns%20a%20Value%20\(Visual%20Basic\).md)   
 [How to: Call a Procedure that Does Not Return a Value](../Topic/How%20to:%20Call%20a%20Procedure%20that%20Does%20Not%20Return%20a%20Value%20\(Visual%20Basic\).md)   
 [NOTINBUILD 방법: 값을 배열에 배치](http://msdn.microsoft.com/ko-kr/6dddc79c-cf60-41c2-b572-8bfa49b4fe7e)   
 [NOTINBUILD 방법: 배열에서 값 가져오기](http://msdn.microsoft.com/ko-kr/202a6468-8ccb-4864-bd8b-eab3b42d4288)   
 [How to: Put a Value in a Property](../Topic/How%20to:%20Put%20a%20Value%20in%20a%20Property%20\(Visual%20Basic\).md)   
 [How to: Get a Value from a Property](../Topic/How%20to:%20Get%20a%20Value%20from%20a%20Property%20\(Visual%20Basic\).md)