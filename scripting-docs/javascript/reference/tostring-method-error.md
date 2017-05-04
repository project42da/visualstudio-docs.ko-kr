---
title: "toString 메서드(Error) | Microsoft Docs"
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
ms.assetid: 5d6d9712-c06d-4b31-9bc9-e46f6bb5cd38
caps.latest.revision: 2
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 2
---
# toString 메서드(Error)
오류를 나타내는 문자열을 반환합니다.  
  
## 구문  
  
```  
  
error.toString()  
```  
  
## 매개 변수  
 `date`  
 필수 요소.  문자열로 표현할 오류입니다.  
  
## 반환 값  
 "Error:"와 오류 메시지를 반환합니다.  
  
## 예제  
 다음 예제에서는 오류와 함께 `toString` 메서드를 사용하는 방법을 보여 줍니다  
  
```javascript  
var myError = new Error();  
myError.message = "My Error";  
var errorString = myError.toString();  
document.write(errorString);  
  
// Output: Error: My Error  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]