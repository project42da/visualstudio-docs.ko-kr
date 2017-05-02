---
title: "toLocaleLowerCase 메서드(String)(JavaScript) | Microsoft Docs"
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
  - "toLocaleLowerCase"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "toLocaleLowerCase 메서드"
ms.assetid: add894d3-d14a-4dbc-a9b9-7ad1d3a2e581
caps.latest.revision: 12
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 12
---
# toLocaleLowerCase 메서드(String)(JavaScript)
호스트 환경의 현재 로캘을 고려하여 모든 영문자를 소문자로 변환합니다.  
  
## 구문  
  
```  
  
stringVar.toLocaleLowerCase( )  
```  
  
## 설명  
 필수 `stringVar` 참조는 `String` 개체 또는 문자열 리터럴입니다.  
  
 `toLocaleLowerCase` 메서드는 호스트 환경의 현재 로캘을 고려하여 문자열의 문자를 변환합니다.  대부분의 경우 결과는 `toLowerCase` 메서드의 결과와 같습니다.  언어 규칙이 정규 유니코드 대\/소문자 매핑과 충돌하면 결과가 달라집니다.  
  
## 요구 사항  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
 **적용 대상**: [String 개체](../../javascript/reference/string-object-javascript.md)  
  
## 참고 항목  
 [toLocaleUpperCase 메서드\(String\)](../../javascript/reference/tolocaleuppercase-method-string-javascript.md)   
 [toLowerCase 메서드](../../javascript/reference/tolowercase-method-javascript.md)