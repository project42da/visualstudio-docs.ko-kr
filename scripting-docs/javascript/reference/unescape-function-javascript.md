---
title: "unescape 함수(JavaScript) | Microsoft Docs"
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
  - "unescape"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "Unescape 메서드"
ms.assetid: 4adf0270-88b5-4d54-8110-d879d6ae97c2
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# unescape 함수(JavaScript)
`escape` 함수로 인코딩한 `String` 개체를 디코딩합니다.  사용되지 않습니다.  
  
## 구문  
  
```  
unescape(charString)   
```  
  
## 설명  
 필수 `charString` 인수는 디코딩할 `String` 개체 또는 리터럴입니다.  
  
 `unescape` 함수는 `charstring`의 콘텐츠를 포함하는 문자열 값을 반환합니다.  %*xx* 16진수 형식으로 인코딩된 문자는 모두 해당 ASCII 문자 집합으로 바뀝니다.  
  
 **%u** *xxxx* 형식\(유니코드 문자\)으로 인코딩된 문자는 16진수 인코딩 형식이 *xxxx*인 유니코드 문자로 바뀝니다.  
  
> [!NOTE]
>  `unescape` 함수는 URI\(Uniform Resource Identifiers\)를 디코딩하는 데 사용하면 안 됩니다.  대신 `decodeURI` 및 `decodeURIComponent` 함수를 사용합니다.  
  
## 요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **적용 대상**: [Global 개체](../../javascript/reference/global-object-javascript.md)  
  
## 참고 항목  
 [decodeURI 함수](../../javascript/reference/decodeuri-function-javascript.md)   
 [decodeURIComponent 함수](../../javascript/reference/decodeuricomponent-function-javascript.md)   
 [escape 함수](../../javascript/reference/escape-function-javascript.md)   
 [String 개체](../../javascript/reference/string-object-javascript.md)