---
title: "Math.sign 함수(JavaScript) | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-javascript"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
ms.assetid: 8b462020-ceff-4947-8dd1-c78e6aff8d98
caps.latest.revision: 2
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 2
---
# Math.sign 함수(JavaScript)
숫자가 양수, 음수 또는 0인지를 나타내는 숫자의 부호를 반환합니다.  
  
## 구문  
  
```  
Math.sign(number)  
```  
  
## 설명  
 필수 `number` 인수는 부호가 필요한 숫자 식입니다.  
  
 반환 값은 다음 중 하나입니다.  
  
-   `number`가 `NaN`이면 `NaN`입니다.  
  
-   `number`가 \-0이면 \-0입니다.  
  
-   `number`가 \+0이면 \+0입니다.  
  
-   `number`가 음수이고 \-0이 아니면 \-1입니다.  
  
-   `number`가 양수이고 \+0이 아니면 \+1입니다.  
  
## 요구 사항  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]