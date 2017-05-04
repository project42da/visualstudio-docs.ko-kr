---
title: "정규식 개체가 필요합니다. | Microsoft Docs"
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
  - "VS.WebClient.Help.SCRIPT5016"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
ms.assetid: e226096c-c58f-4bcb-a71e-fa32ce474b67
caps.latest.revision: 6
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 6
---
# 정규식 개체가 필요합니다.
`RegExp` 형식이 아닌 개체에 대해 **RegExp.prototype.toString** 또는 **RegExp.prototype.valueOf** 메서드를 호출하려고 했습니다.  이 호출 형식의 개체는 `RegExp` 형식이어야 합니다.  
  
### 이 오류를 해결하려면  
  
-   `RegExp` 형식의 개체에 대해 **RegExp.prototype.toString** 또는 **RegExp.prototype.valueOf** 메서드만 호출합니다.  
  
## 참고 항목  
 [Regular Expression 개체](../../javascript/reference/regular-expression-object-javascript.md)   
 [Regular Expression Syntax \(JavaScript\)](http://msdn.microsoft.com/ko-kr/ab0766e1-7037-45ed-aa23-706f58358c0e)