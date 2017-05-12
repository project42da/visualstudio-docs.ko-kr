---
title: "encodeURIComponent 함수(JavaScript) | Microsoft Docs"
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
  - "encodeURIComponent"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "encodeURIComponent 메서드"
ms.assetid: 8202bce6-1342-40dc-a5ef-ac6d210a7d15
caps.latest.revision: 12
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 12
---
# encodeURIComponent 함수(JavaScript)
텍스트 문자열을 유효한 URI\(Uniform Resource Identifier\) 구성 요소로 인코딩합니다.  
  
## 구문  
  
```  
encodeURIComponent(encodedURIString)  
```  
  
## 설명  
 필수 `encodedURIString` 인수는 인코딩된 URI 구성 요소를 나타내는 값입니다.  
  
 `encodeURIComponent` 함수는 인코딩된 URI를 반환합니다.  `decodeURIComponent`에 결과를 전달하면 원래 문자열이 반환됩니다.  `encodeURIComponent` 함수는 모든 문자를 인코딩하기 때문에 문자열이 \/folder1\/folder2\/default.html과 같은 경로를 나타날 때는 주의하세요.  이 경우 슬래시 문자가 인코딩되므로 웹 서버에 요청을 전송할 때 유효하지 않게 됩니다.  문자열에 URI 구성 요소가 두 개 이상 들어 있으면 `encodeURI` 함수를 사용하세요.  
  
## 예제  
 다음 코드는 URI 구성 요소를 먼저 인코딩한 다음 디코딩합니다.  
  
```javascript  
var uriEncode = encodeURIComponent ("www.Not a URL.com");  
var uriDecode = decodeURIComponent(uriEncode);  
  
document.write(uriEncode);  
document.write("<br/>");  
document.write(uriDecode);  
  
// Output:  
// www.Not%20a%20URL.com  
// www.Not a URL.com  
```  
  
## 요구 사항  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
## 참고 항목  
 [decodeURI 함수](../../javascript/reference/decodeuri-function-javascript.md)   
 [decodeURIComponent 함수](../../javascript/reference/decodeuricomponent-function-javascript.md)