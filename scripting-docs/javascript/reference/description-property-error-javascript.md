---
title: "description 속성(Error)(JavaScript) | Microsoft Docs"
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
  - "Description"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "Description 속성"
  - "오류 처리, 오류 설명"
  - "오류, 설명"
ms.assetid: ea727f1e-2041-4400-965c-67e6d47a1ff0
caps.latest.revision: 18
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 18
---
# description 속성(Error)(JavaScript)
특정 오류와 관련된 설명 문자열을 반환하거나 설정합니다.  
  
## 구문  
  
```  
  
object  
.description [= stringExpression]  
```  
  
## 매개 변수  
 *object*  
 필수 요소.  `Error` 개체의 인스턴스입니다.  
  
 `stringExpression`  
 선택 사항입니다.  오류에 대한 설명을 포함하는 문자열 식입니다.  
  
## 설명  
 **description** 속성에는 특정 오류와 관련된 오류 메시지가 포함됩니다.  이 속성에 포함된 값을 사용하여 오류에 대해 사용자에게 경고를 보냅니다.  
  
 **description** 및 **message** 속성은 동일한 기능을 제공합니다. **description** 속성은 이전 버전과의 호환성을 유지하고 **message** 속성은 ECMA 표준을 따릅니다.  
  
## 예제  
 다음 예제에서는 **description** 속성의 사용법을 보여 줍니다.  
  
```javascript  
try  
{  
// Cause an error:  
    x = y     
}  
catch(e)  
{  
// Prints "[object Error]":  
    document.write(e)  
    document.write (" ");  
// Prints 5009:  
    document.write((e.number & 0xFFFF))    
    document.write (" ");  
// Prints "'y' is undefined":  
    document.write(e.description);  
    document.write (" ");  
// Prints "'y' is undefined":  
    document.write(e.message)  
}  
```  
  
## 요구 사항  
 [!INCLUDE[jsv5](../../javascript/reference/includes/jsv5-md.md)]  
  
 **적용 대상**: [Error 개체](../../javascript/reference/error-object-javascript.md)  
  
## 참고 항목  
 [number 속성\(Error\)](../../javascript/reference/number-property-error-javascript.md)   
 [message 속성\(Error\)](../../javascript/reference/message-property-error-javascript.md)   
 [name 속성\(Error\)](../../javascript/reference/name-property-error-javascript.md)