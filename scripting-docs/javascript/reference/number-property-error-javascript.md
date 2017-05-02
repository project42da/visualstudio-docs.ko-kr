---
title: "number 속성(Error)(JavaScript) | Microsoft Docs"
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
  - "Number"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "Number 속성"
ms.assetid: 8697e20b-a2b0-4e26-85c0-ab07ddfe8281
caps.latest.revision: 18
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 18
---
# number 속성(Error)(JavaScript)
특정 오류와 관련된 숫자 값을 반환하거나 설정합니다.  `Error` 개체의 기본 속성은 **number**입니다.  
  
## 구문  
  
```  
  
object  
.number [= errorNumber]  
```  
  
## 매개 변수  
 *Object*  
 임의의 `Error` 개체 인스턴스입니다.  
  
 *errorNumber*  
 오류를 나타내는 정수입니다.  
  
## 설명  
 오류 번호는 32비트 값입니다.  상위 16비트 단어는 장치 코드이고 하위 단어가 오류 코드입니다.  오류 코드를 확인하려면 number 속성을 16진수 `0xFFFF`와 결합하기 위해 `&`\(비트 AND\) 연산자를 사용하세요.  
  
## 예제  
 다음 예제에서는 예외를 throw하고 오류 번호에서 파생된 오류 코드를 표시합니다.  
  
```javascript  
try  
    {  
    // Cause an error.  
    var x = y;  
    }  
catch(e)  
    {  
    document.write ("Error Code: ");  
    document.write (e.number & 0xFFFF)  
    document.write ("<br />");  
  
    document.write ("Facility Code: ")  
    document.write(e.number>>16 & 0x1FFF)  
    document.write ("<br />");  
  
    document.write ("Error Message: ")  
    document.write (e.message)  
    }  
```  
  
## 예제  
 이 코드의 출력은 다음과 같습니다.  
  
```javascript  
Error Code: 5009  
Facility Code: 10  
Error Message: 'y' is undefined  
```  
  
## 요구 사항  
 [!INCLUDE[jsv5](../../javascript/reference/includes/jsv5-md.md)]  
  
 **적용 대상**: [Error 개체](../../javascript/reference/error-object-javascript.md)  
  
## 참고 항목  
 [description 속성\(Error\)](../../javascript/reference/description-property-error-javascript.md)   
 [message 속성\(Error\)](../../javascript/reference/message-property-error-javascript.md)   
 [name 속성\(Error\)](../../javascript/reference/name-property-error-javascript.md)