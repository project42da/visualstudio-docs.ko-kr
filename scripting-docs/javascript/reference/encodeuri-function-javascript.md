---
title: "encodeURI 함수(JavaScript) | Microsoft Docs"
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
  - "encodeURI"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "encodeURI 메서드"
ms.assetid: 17bab5a2-bcd4-46c2-8b52-b2b5a0ed98a3
caps.latest.revision: 12
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 12
---
# encodeURI 함수(JavaScript)
텍스트 문자열을 유효한 URI\(Uniform Resource Identifier\)로 인코딩합니다.  
  
## 구문  
  
```  
  
encodeURI(  
URIString  
)  
  
```  
  
## 설명  
 필수 `URIString` 인수는 인코딩된 URI를 나타내는 값입니다.  
  
 `encodeURI` 함수는 인코딩된 URI를 반환합니다.  `decodeURI`에 결과를 전달하면 원래 문자열이 반환됩니다.  `encodeURI` 함수는 ":", "\/", ";", "?" 등의 문자를 인코딩하지 않으므로  이 문자들을 인코딩하려면 `encodeURIComponent`를 사용합니다.  
  
## 예제  
 다음 코드는 URI를 먼저 인코딩한 다음 디코딩합니다.  
  
```javascript  
var uriEncode = encodeURI ("http://www.Not a URL.com");  
var uriDecode = decodeURIComponent(uriEncode);  
  
document.write(uriEncode);  
document.write("<br/>");  
document.write(uriDecode);  
  
// Output:  
// http://www.Not%20a%20URL.com  
// http://www.Not a URL.com  
```  
  
## 요구 사항  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
## 참고 항목  
 [decodeURI 함수](../../javascript/reference/decodeuri-function-javascript.md)   
 [decodeURIComponent 함수](../../javascript/reference/decodeuricomponent-function-javascript.md)