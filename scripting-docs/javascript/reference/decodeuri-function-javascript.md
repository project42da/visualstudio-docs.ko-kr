---
title: "decodeURI 함수(JavaScript) | Microsoft Docs"
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
  - "decodeURI"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "decodeURI 메서드"
ms.assetid: af6c81dc-10f4-4243-a7ce-d18ae3ea0fb8
caps.latest.revision: 12
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 12
---
# decodeURI 함수(JavaScript)
인코딩된 URI\(Uniform Resource Identifier\)의 인코딩되지 않은 버전을 가져옵니다.  
  
## 구문  
  
```  
decodeURI(URIstring)  
```  
  
## 설명  
 필수 `URIstring` 인수는 인코딩된 URI를 나타내는 값입니다.  
  
 사용되지 않는 `unescape` 함수 대신 `decodeURI` 함수를 사용하세요.  
  
 `decodeURI` 함수는 문자열 값을 반환합니다.  
  
 `URIString`이 유효하지 않으면 URIError가 발생합니다.  
  
 **적용 대상**: [Global 개체](../../javascript/reference/global-object-javascript.md)  
  
## 예제  
 다음 코드는 URI 구성 요소를 먼저 인코딩한 다음 디코딩합니다.  
  
```javascript  
var uriEncode = encodeURIComponent ("www.Not a URL.com");  
var uriDecode = decodeURIComponent(uriEncode);  
  
document.write (uriEncode);  
document.write ("<br/>");  
document.write (uriDecode);  
  
// Output:  
// www.Not%20a%20URL.com  
// www.Not a URL.com  
```  
  
## 요구 사항  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
## 참고 항목  
 [decodeURIComponent 함수](../../javascript/reference/decodeuricomponent-function-javascript.md)   
 [encodeURI 함수](../../javascript/reference/encodeuri-function-javascript.md)   
 [Global 개체](../../javascript/reference/global-object-javascript.md)