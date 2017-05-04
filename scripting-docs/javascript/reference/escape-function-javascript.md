---
title: "escape 함수(JavaScript) | Microsoft Docs"
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
  - "escape"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "String 개체 인코딩"
  - "Escape 메서드"
  - "16진수"
  - "String 개체, 인코딩"
ms.assetid: caa92bea-ba69-4109-a68a-6e2debda463a
caps.latest.revision: 11
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 11
---
# escape 함수(JavaScript)
모든 컴퓨터에서 읽을 수 있도록 문자열을 인코딩합니다.  사용되지 않습니다.  
  
## 구문  
  
```  
escape(charString)   
```  
  
## 설명  
 필수 `charString` 인수는 인코딩할 임의의 `String` 개체 또는 리터럴입니다.  
  
 **escape** 함수는 `charstring`의 내용을 포함하는 문자열 값\(유니코드 형식\)을 반환합니다.  공백과 문장 부호, 악센트 부호가 있는 문자, 그 외 비ASCII 문자는 모두 `%`*xx* 인코딩으로 바뀝니다. 여기서 *xx*는 해당 문자를 나타내는 16진수입니다.  예를 들어 공백은 "%20"으로 반환됩니다.  
  
 값이 255보다 큰 문자는 **%u** *xxxx* 형식으로 저장됩니다.  
  
> [!NOTE]
>  **escape** 함수는 URI\(Uniform Resource Identifiers\)를 인코딩하는 데 사용하면 안 됩니다.  대신 `encodeURI` 및 `encodeURIComponent` 함수를 사용합니다.  
  
 **적용 대상**: [Global 개체](../../javascript/reference/global-object-javascript.md)  
  
## 요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## 참고 항목  
 [encodeURI 함수](../../javascript/reference/encodeuri-function-javascript.md)   
 [encodeURIComponent 함수](../../javascript/reference/encodeuricomponent-function-javascript.md)   
 [String 개체](../../javascript/reference/string-object-javascript.md)   
 [unescape 함수](../../javascript/reference/unescape-function-javascript.md)