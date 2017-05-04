---
title: "toLocaleUpperCase 메서드(String)(JavaScript) | Microsoft Docs"
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
  - "toLocaleUpperCase"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "toLocaleUpperCase 메서드"
ms.assetid: e927adb6-475e-44b2-91f7-cedda10a39b0
caps.latest.revision: 11
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 11
---
# toLocaleUpperCase 메서드(String)(JavaScript)
호스트 환경의 현재 로캘을 고려하여 모든 영문자가 대문자로 변환된 문자열을 반환합니다.  
  
## 구문  
  
```  
  
stringVar.toLocaleUpperCase( )  
```  
  
## 설명  
 필수 `stringVar` 참조는 `String` 개체 또는 문자열 리터럴입니다.  
  
 `toLocaleUpperCase` 메서드는 호스트 환경의 현재 로캘을 고려하여 문자열의 문자를 변환합니다.  대부분의 경우 결과는 `toUpperCase` 메서드의 결과와 같습니다.  언어 규칙이 정규 유니코드 대\/소문자 매핑과 충돌하면 결과가 달라집니다.  
  
## 요구 사항  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
 **적용 대상**: [String 개체](../../javascript/reference/string-object-javascript.md)  
  
## 참고 항목  
 [toLocaleLowerCase 메서드\(String\)](../../javascript/reference/tolocalelowercase-method-string-javascript.md)   
 [toUpperCase 메서드\(String\)](../../javascript/reference/touppercase-method-string-javascript.md)