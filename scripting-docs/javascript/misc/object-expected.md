---
title: "개체가 필요합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "javascript"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VS.WebClient.Help.SCRIPT5007"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
ms.assetid: 5d88c93d-e5b5-4b11-9bb5-bf1a5e41ccc3
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# 개체가 필요합니다.
`Object`가 아닌 다른 형식의 개체에 대해 메서드 또는 속성을 호출하려고 했거나, `Object`가 필요할 때 `Object`가 아닌 다른 형식의 인수를 전달했습니다.  
  
### 이 오류를 해결하려면  
  
-   `Object` 형식의 개체에 대해서만 메서드 또는 속성을 호출합니다.  
  
-   개체가 아닌 인수에 대해 오류가 발생하는 경우 `Object` 형식의 개체를 전달합니다.  
  
-   `Object` 형식의 개체 대신 정의되지 않았거나 null 참조가 호출되는지 여부를 확인합니다.  
  
     예를 들어 다음 코드의 myVar에서 이 오류가 발생하는 경우  
  
    ```javascript  
    var str = myVar.toString();  
    ```  
  
     다음 코드를 대신 사용할 수 있습니다.  
  
    ```javascript  
    if (myVar) {  
        var str = myVar.toString();  
    }  
    ```  
  
## 참고 항목  
 [Object 개체](../../javascript/reference/object-object-javascript.md)   
 [Object 및 Array](../../javascript/objects-and-arrays-javascript.md)