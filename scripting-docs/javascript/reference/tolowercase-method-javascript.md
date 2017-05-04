---
title: "toLowerCase 메서드(JavaScript) | Microsoft Docs"
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
  - "toLowerCase"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "toLowerCase 메서드"
ms.assetid: dfd543b9-3e7a-4f83-a391-9cde109ad6bc
caps.latest.revision: 14
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 14
---
# toLowerCase 메서드(JavaScript)
문자열에 있는 모든 영문자를 소문자로 변환합니다.  
  
## 구문  
  
```  
  
        strVariable.toLowerCase()  
"String Literal".toLowerCase()   
```  
  
## 설명  
 `toLowerCase` 메서드는 영문자가 아닌 문자에는 효과가 없습니다.  
  
 다음 예제는 `toLowerCase` 메서드의 효과를 보여 줍니다.  
  
```javascript  
var str1 = "This is a STRING.";  
var str2 = str1. toLowerCase();  
document.write(str2);  
  
// Output: this is a string.  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **적용 대상**: [String 개체](../../javascript/reference/string-object-javascript.md)  
  
## 참고 항목  
 [toLocaleLowerCase 메서드\(String\)](../../javascript/reference/tolocalelowercase-method-string-javascript.md)   
 [toUpperCase 메서드\(String\)](../../javascript/reference/touppercase-method-string-javascript.md)