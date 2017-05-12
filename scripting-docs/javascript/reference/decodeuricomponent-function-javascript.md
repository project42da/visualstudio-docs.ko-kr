---
title: "decodeURIComponent 함수(JavaScript) | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-javascript"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "decodeURIComponent"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "decodeURIComponent 메서드"
ms.assetid: 486ccee2-afd7-4863-97ce-4adb50cf39c0
caps.latest.revision: 11
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 11
---
# decodeURIComponent 함수(JavaScript)
인코딩된 URI\(Uniform Resource Identifier\) 구성 요소의 인코딩되지 않은 버전을 가져옵니다.  
  
## 구문  
  
```  
decodeURIComponent(encodedURIString)  
```  
  
## 설명  
 필수 `encodedURIString` 인수는 인코딩된 URI 구성 요소를 나타내는 값입니다.  
  
 URIComponent는 완전한 URI의 일부입니다.  
  
 `encodedURIString`이 유효하지 않으면 URIError가 발생합니다.  
  
## 예제  
 다음 코드는 URI를 먼저 인코딩한 다음 디코딩합니다.  
  
```javascript  
var uriEncode = encodeURI ("http://www.Not a URL.com");  
var uriDecode = decodeURIComponent(uriEncode);  
  
document.write (uriEncode);  
document.write("<br/>");  
document.write (uriDecode);  
  
// Output:  
// http://www.Not%20a%20URL.com  
// http://www.Not a URL.com  
```  
  
## 요구 사항  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
## 참고 항목  
 [decodeURI 함수](../../javascript/reference/decodeuri-function-javascript.md)   
 [encodeURI 함수](../../javascript/reference/encodeuri-function-javascript.md)