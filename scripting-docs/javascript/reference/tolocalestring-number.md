---
title: "toLocaleString(Number) | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-javascript"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
ms.assetid: 42c05252-13c1-4943-b1a4-b33285aeab3e
caps.latest.revision: 4
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 4
---
# toLocaleString(Number)
현재 로캘 또는 지정된 로캘을 사용하여 숫자를 문자열로 변환합니다.  
  
## 구문  
  
```  
  
numberObj.toLocaleString([locales][, options])   
```  
  
#### 매개 변수  
 `numberObj`  
 필수 요소.  변환할 `Number` 개체입니다.  
  
 `locales`  
 선택 사항입니다.  하나 이상의 언어 또는 로캘 태그를 포함한 로캘 문자열의 배열입니다.  두 개 이상의 로캘 문자열을 포함하는 경우, 첫 번째 항목이 기본 설정 로캘이 되도록 우선 순위를 내림차순으로 나열합니다.  이 매개 변수를 생략하면 JavaScript 런타임 기본 로캘이 사용됩니다.  
  
 `options`  
 선택 사항입니다.  비교 옵션을 지정하는 하나 이상의 속성을 포함하는 개체입니다.  
  
## 설명  
 Internet Explorer 11부터 `toLocaleString`은 `locales` 및 `options` 매개 변수에 대한 지원을 추가하는 비교를 위해 `Intl.NumberFormat`을 내부적으로 사용합니다.  이러한 매개 변수에 대한 자세한 내용은 [Intl.NumberFormat](../../javascript/reference/intl-numberformat-object-javascript.md)을 참조하십시오.  
  
> [!IMPORTANT]
>  `locales` 및 `options` 매개 변수는 모든 문서 모드와 브라우저 버전에서 지원되지 않습니다.  자세한 내용은 요구 사항 부분을 참조하십시오.  
  
> [!NOTE]
>  `locales` 매개 변수를 생략하는 경우 `toLocaleString`를 사용하여 사용자에게 결과를 보여주기만 합니다. 반환되는 결과가 컴퓨터별\(메서드는 현재 로캘을 반환\)로 다르기 때문에 스크립트 내에서 값을 연산하는 데 매개 변수를 사용하지 않습니다.  
  
## 예제  
 다음 예제에서는 매개 변수 없이 `toLocaleString` 메서드를 사용하는 방법을 보여 줍니다.  
  
```javascript  
var n, s;  
n = new Number(100);  
s = "Current locale value is: ";  
s += n.toLocaleString();                 
document.write(s);  
  
// Output:  
// The value 100 as represented by the current locale.  
```  
  
## 예제  
 다음 예제는 `toLocaleString` 메서드를 지정된 로캘 및 비교 옵션과 함께 사용하는 방법을 보여 줍니다.  
  
```javascript  
var number = 123456789;  
var options1 = { style: "percent" };  
var options2 = { style: "currency", currency: "INR" };  
  
document.write(number.toLocaleString("en-US"));  
// 123,456,789  
document.write(number.toLocaleString("ja-JP"));  
// 123,456,789  
document.write(number.toLocaleString("ar-SA", options1));  
// ١٢,٣٤٥,٦٧٨,٩٠٠ %  
document.write(number.toLocaleString("hi-IN", options2));  
// ₹ 12,34,56,789.00  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 `locales` 및 `options` 매개 변수:  
  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]  
  
## 참고 항목  
 [toLocaleDateString 메서드\(Date\)](../../javascript/reference/tolocaledatestring-method-date-javascript.md)