---
title: "개체 이니셜라이저 구문은 &#39;Object&#39;의 인스턴스를 초기화하는 데 사용할 수 없습니다. | Microsoft Docs"
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
  - "bc30994"
  - "vbc30994"
helpviewer_keywords: 
  - "BC30994"
ms.assetid: 2ef65965-f014-4fc1-8c7d-c603f0a764df
caps.latest.revision: 5
caps.handback.revision: 5
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 개체 이니셜라이저 구문은 &#39;Object&#39;의 인스턴스를 초기화하는 데 사용할 수 없습니다.
개체 이니셜라이저 구문을 사용하여 `Object`의 인스턴스를 초기화할 수 없습니다.`Object` 인스턴스에 값을 할당할 속성 또는 필드가 없습니다. 개체 이니셜라이저 구문에 하나 이상 이러한 속성 또는 필드가 필요합니다.  
  
```  
' Not valid. ' Dim obj1 = New Object With {} ' Dim obj2 = New Object With {.ToString = <some value>}  
```  
  
 **오류 ID:** BC30994  
  
### 이 오류를 해결하려면  
  
1.  이니셜라이저 목록을 사용하지 않고 `Object` 형식의 인스턴스를 선언합니다.  
  
    ```  
    Dim obj3 as Object Dim obj4 as New Object()  
    ```  
  
## 참고 항목  
 [Object Initializers: Named and Anonymous Types](../Topic/Object%20Initializers:%20Named%20and%20Anonymous%20Types%20\(Visual%20Basic\).md)   
 [Object Data Type](/dotnet/visual-basic/language-reference/data-types/object-data-type)