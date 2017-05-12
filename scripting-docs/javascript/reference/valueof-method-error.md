---
title: "valueOf 메서드(Error) | Microsoft Docs"
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
ms.assetid: ca25c57d-c9ad-445b-8235-561390de680c
caps.latest.revision: 2
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 2
---
# valueOf 메서드(Error)
오류의 문자열 값을 반환합니다.  
  
## 구문  
  
```  
  
error.valueOf()  
```  
  
#### 매개 변수  
 `error` 개체는 임의의 Error 인스턴스입니다.  
  
## 반환 값  
 문자열 "Error:"와 오류 메시지입니다.  
  
## 예제  
 다음 예제에서는 `valueOF` 메서드 및 날짜를 사용하는 방법을 보여 줍니다.  
  
```javascript  
var myError = new Error();  
myError.message = "This is an error.";  
var value = myError.valueOf();  
document.write(value);  
  
// Output: Error: This is an error.  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]