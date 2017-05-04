---
title: "Error 개체(JavaScript) | Microsoft Docs"
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
  - "Error"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "Error 개체"
ms.assetid: 0b27d6ec-3997-4e91-a6c0-5afbaf494db7
caps.latest.revision: 25
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 25
---
# Error 개체(JavaScript)
오류 정보가 들어 있습니다.  
  
## 구문  
  
```  
  
      errorObj = new Error()  
errorObj = new Error([number])  
errorObj = new Error([number[, description]])  
```  
  
## 매개 변수  
 `errorObj`  
 필수입니다.  `Error` 개체가 할당되는 변수 이름입니다.  `throw` 문을 사용하여 오류를 만들면 변수 할당이 생략됩니다.  
  
 `number`  
 선택 사항  오류에 할당된 숫자 값입니다.  생략하면 0이 할당됩니다.  
  
 `description`  
 선택 사항  오류를 설명하는 간단한 문자열입니다.  생략하면 빈 문자열이 할당됩니다.  
  
## 설명  
 런타임 오류가 발생할 때마다 `Error` 개체의 인스턴스가 생성되어 오류를 설명합니다.  이 인스턴스에는 오류 설명이 포함되어 있는 두 가지 내장 속성\(`description` 속성\) 및 오류 번호\(`number` 속성\)가 있습니다.  자세한 내용은 [JavaScript 런타임 오류](../../javascript/reference/javascript-run-time-errors.md)을 참조하십시오.  
  
 오류 번호는 32비트 값입니다.  상위 16비트 단어는 장치 코드이고 하위 16비트 단어가 실제 오류 코드입니다.  
  
 `Error` 개체는 위에 있는 구문을 사용하여 명시적으로 만들거나 `throw` 문을 사용하여 throw할 수도 있습니다.  두 가지 경우 선택한 속성을 추가하여 `Error` 개체의 기능을 확장할 수 있습니다.  
  
 일반적으로 **try...catch** 문에서 생성된 지역 변수는 암시적으로 생성된 `Error` 개체를 참조합니다.  그 결과 사용자가 선택한 방법으로 오류 번호 및 설명을 사용할 수 있습니다.  
  
## 예제  
 다음 예제에서는 `Error` 개체를 사용하는 방법을 보여줍니다.  
  
```  
function checkInput(x) {  
    try  
    {  
        if (isNaN(parseInt(x))) {  
            throw new Error("Input is not a number.");  
        }  
    }  
    catch(e)  
    {  
        document.write(e.description);  
    }  
}  
  
checkInput("not a number");  
```  
  
## 예제  
 다음 예제에서는 암시적으로 생성된 `Error` 개체를 사용하는 방법을 보여줍니다.  
  
```javascript  
try  
   {  
   // Cause an error.  
   x = y;  
   }  
catch(e)  
   {  
      document.write(e);  
      document.write ("<br />");  
  
      document.write ("Number: ");  
      document.write (e.number & 0xFFFF);  
      document.write ("<br />");  
  
      document.write ("Facility Code: ");  
      document.write(e.number>>16 & 0x1FFF);  
      document.write ("<br />");  
  
      document.write ("Description: ");  
      document.write (e.description);  
   }  
  
// Output:  
// ReferenceError: 'y' is undefined  
// Number: 5009  
// Facility Code: 10  
// Description: 'y' is undefined  
  
```  
  
## 메서드  
 [toString 메서드\(Error\)](../../javascript/reference/tostring-method-error.md) &#124; [valueOf 메서드\(Date\)](../../javascript/reference/valueof-method-date.md)  
  
## 속성  
 [constructor 속성\(Error\)](../../javascript/reference/constructor-property-error.md) &#124; [description 속성](../../javascript/reference/description-property-error-javascript.md) &#124; [message 속성](../../javascript/reference/message-property-error-javascript.md) &#124; [name 속성](../../javascript/reference/name-property-error-javascript.md) &#124; [number 속성](../../javascript/reference/number-property-error-javascript.md) &#124; [prototype 속성\(Error\)](../../javascript/reference/prototype-property-error.md) &#124; [stack 속성\(Error\)](../../javascript/reference/stack-property-error-javascript.md) &#124; [stackTraceLimit 속성\(Error\)](../../javascript/reference/stacktracelimit-property-error-javascript.md)  
  
## 요구 사항  
 [!INCLUDE[jsv5](../../javascript/reference/includes/jsv5-md.md)]  
  
## 참고 항목  
 [new 연산자](../../javascript/reference/new-operator-decrementjavascript.md)   
 [throw 문](../../javascript/reference/throw-statement-javascript.md)   
 [try...catch...finally 문](../../javascript/reference/try-dot-dot-dot-catch-dot-dot-dot-finally-statement-javascript.md)   
 [var 문](../../javascript/reference/var-statement-javascript.md)   
 [Hilo JavaScript 샘플 응용 프로그램\(Windows 스토어\)](http://hilojs.codeplex.com/SourceControl/latest)