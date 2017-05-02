---
title: "toUpperCase 메서드(String)(JavaScript) | Microsoft Docs"
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
  - "toUpperCase"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "toUpperCase 메서드"
ms.assetid: 4fd4ccc3-e794-498a-9db1-baf48fc1dda1
caps.latest.revision: 15
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 15
---
# toUpperCase 메서드(String)(JavaScript)
문자열에 있는 모든 영문자를 대문자로 변환합니다.  
  
## 구문  
  
```  
  
        strVariable.toUpperCase()  
"String Literal".toUpperCase()   
```  
  
## 설명  
 `toUpperCase` 메서드는 영문자가 아닌 문자에는 효과가 없습니다.  
  
## 예제  
 다음 예제는 `toUpperCase` 메서드의 효과를 보여 줍니다.  
  
```javascript  
var str1 = "This is a STRING.";  
var str2 = str1.toUpperCase();  
document.write(str2);  
  
// Output: THIS IS A STRING.  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **적용 대상**: [String 개체](../../javascript/reference/string-object-javascript.md)  
  
## 참고 항목  
 [toLocaleUpperCase 메서드\(String\)](../../javascript/reference/tolocaleuppercase-method-string-javascript.md)   
 [toLowerCase 메서드](../../javascript/reference/tolowercase-method-javascript.md)