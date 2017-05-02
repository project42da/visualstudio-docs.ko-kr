---
title: "message 속성(Error)(JavaScript) | Microsoft Docs"
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
  - "message"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "Message 속성"
ms.assetid: 8cab0392-e0db-4714-827c-47ab04e8b4f2
caps.latest.revision: 16
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 16
---
# message 속성(Error)(JavaScript)
오류 메시지 문자열을 반환합니다.  
  
## 구문  
  
```  
  
errorObj.message  
```  
  
## 매개 변수  
 `errorObj`  
 필수 요소.  `Error` 개체의 인스턴스입니다.  
  
## 설명  
 `message` 속성은 특정 오류와 관련된 오류 메시지를 포함하는 문자열을 반환합니다.  
  
 `description` 및 `message` 속성은 동일한 기능을 제공합니다.  `description` 속성은 이전 버전과의 호환성을 제공합니다. `message` 속성은 ECMA 표준과 호환됩니다.  
  
## 예제  
 다음 예제에서는 TypeError 예외를 throw하고 오류 이름과 해당 메시지를 표시합니다.  
  
```javascript  
try  
{  
    // Cause an error.  
    var x = y;  
}  
catch(e)  
{  
    document.write ("Error Message: " + e.message);  
    document.write ("<br />");  
    document.write ("Error Code: ");  
    document.write (e.number & 0xFFFF)  
    document.write ("<br />");  
    document.write ("Error Name: " + e.name);  
}  
```  
  
## 예제  
 이 코드의 출력은 다음과 같습니다.  
  
```javascript  
Error Message: 'y' is undefined  
Error Code: 5009  
Error Name: TypeError  
```  
  
## 요구 사항  
 [!INCLUDE[jsv5](../../javascript/reference/includes/jsv5-md.md)]  
  
 **적용 대상**: [Error 개체](../../javascript/reference/error-object-javascript.md)  
  
## 참고 항목  
 [description 속성\(Error\)](../../javascript/reference/description-property-error-javascript.md)   
 [name 속성\(Error\)](../../javascript/reference/name-property-error-javascript.md)