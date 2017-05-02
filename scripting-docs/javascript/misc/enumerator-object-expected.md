---
title: "Enumerator 개체가 필요합니다. | Microsoft Docs"
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
  - "VS.WebClient.Help.SCRIPT5015"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
ms.assetid: dc6e32c1-a6e6-4e12-ac99-e3f65f91c8d7
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# Enumerator 개체가 필요합니다.
`Enumerator` 형식이 아닌 개체에 대해 **Enumerator.prototype.atEnd, Enumerator.prototype.item, Enumerator.prototype.moveFirst** 또는 **Enumerator.prototype.moveNext** 메서드를 호출하려고 했습니다.  이 호출 형식의 개체는 `Enumerator` 형식이어야 합니다.  다음은 이 규칙을 위반하는 코드 예제입니다.  
  
```javascript  
var o = new Object;  
o.f = Enumerator.prototype.atEnd;  
o.f();  
```  
  
### 이 오류를 해결하려면  
  
-   `Enumerator` 형식이 아닌 개체에 대해서만 **Enumerator.prototype.atEnd**, **Enumerator.prototype.item**, **Enumerator.prototype.moveFirst** 또는 **Enumerator.prototype.moveNext** 메서드를 호출합니다.  개체가 `Enumerator` 개체인지 확인하려면 다음을 사용합니다.  
  
    ```  
    if(x instanceof Enumerator)  
    ```  
  
## 참고 항목  
 [Enumerator 개체](../../javascript/reference/enumerator-object-javascript.md)