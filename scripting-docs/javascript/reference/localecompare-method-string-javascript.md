---
title: "localeCompare 메서드(String)(JavaScript) | Microsoft Docs"
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
  - "localeCompare"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "localeCompare 메서드"
ms.assetid: 66914079-12dd-4393-a84c-c05f58231c36
caps.latest.revision: 16
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 16
---
# localeCompare 메서드(String)(JavaScript)
두 문자열이 현재 로캘에서 같은지 여부를 확인합니다.  
  
## 구문  
  
```  
  
stringVar.localeCompare(stringExp[, locales][, options])   
```  
  
## 매개 변수  
 `stringVar`  
 필수 요소.  비교할 첫째 문자열입니다.  
  
 `stringExp`  
 필수 요소.  비교할 둘째 문자열입니다.  
  
 `locales`  
 선택 사항입니다.  하나 이상의 언어 또는 로캘 태그를 포함한 로캘 문자열의 배열입니다.  두 개 이상의 로캘 문자열을 포함하는 경우, 첫 번째 항목이 기본 설정 로캘이 되도록 우선 순위를 내림차순으로 나열합니다.  이 매개 변수를 생략하면 JavaScript 런타임 기본 로캘이 사용됩니다.  이 변수는 [BCP 47](http://tools.ietf.org/html/rfc5646) 표준을 따라야 합니다. 자세한 내용은 [Intl.Collator 개체](../../javascript/reference/intl-collator-object-javascript.md)를 참조하십시오.  
  
 `options`  
 선택 사항입니다.  비교 옵션을 지정하는 하나 이상의 속성을 포함하는 개체입니다. 자세한 내용은 [Intl.Collator object](../../javascript/reference/intl-collator-object-javascript.md)를 참조하십시오.  
  
## 설명  
 비교 문자열의 경우 `String` 개체 또는 문자열 리터럴 중 하나만 지정할 수 있습니다.  
  
 Internet Explorer 11부터 `localeCompare`은 `locales` 및 `options` 매개변수에 대한 지원을 추가하는 비교를 위해 `Intl.Collator` 개체를 내부적으로 사용합니다.  이러한 매개 변수에 대한 자세한 내용은 [Intl.Collator](../../javascript/reference/intl-collator-object-javascript.md) 및 [Intl.Collator.compare](../../javascript/reference/compare-property-intl-collator.md)를 참조하십시오.  
  
> [!IMPORTANT]
>  `locales` 및 `options` 매개 변수는 모든 문서 모드와 브라우저 버전에서 지원되지 않습니다.  자세한 내용은 요구 사항 부분을 참조하십시오.  
  
 `localeCompare` 메서드는 `stringVar` 및 `stringExp`의 로캘 구분 문자열 비교를 수행하며 시스템 기본 로캘의 정렬 순서에 따라 다음 결과 중 하나를 반환합니다.  
  
-   `stringVar`이 `stringExp`보다 앞에 정렬되는 경우 \-1입니다.  
  
-   `stringVar`이 `stringExp` 뒤에 정렬되는 경우 \+1입니다.  
  
-   두 문자열이 동일한 경우 0\(영\)입니다.  
  
## 예제  
 다음 코드에서는 `localeCompare`을 사용하는 방법을 보여 줍니다.  
  
```javascript  
var str1 = "def";  
var str2 = "abc"  
  
document.write(str1.localeCompare(str2) + "<br/>");  
  
// Output: 1  
var str3 = "ghi";  
  
document.write(str1.localeCompare(str3)+ "<br/>");  
  
// Output: -1  
var str4 = "def";  
  
document.write(str1.localeCompare(str4));  
  
// Output: 0  
```  
  
## 예제  
 다음 코드는 독일어\(독일\) 로캘로 `localeCompare`를 사용하는 방법을 보여 줍니다.  
  
```javascript  
var str1 = "a";  
var str2 = "b";  
  
document.write(str1.localeCompare(str2, "de-DE"));  
  
// Output  
// - 1  
```  
  
## 예제  
 다음 예제에서는 `localeCompare`를 독일어\(독일\) 로캘과 독일어 전화 번호부의 정렬 순서를 지정하는 로캘별 확장과 함께 사용하는 방법을 보여 줍니다.  이 예제에는 로캘별 차이가 표시됩니다.  
  
```javascript  
var arr = ["ä", "ad", "af", "a"];  
  
document.write(arr[0].localeCompare(arr[1], "de-DE-u-co-phonebk"));  // Returns 1  
document.write (arr[0].localeCompare(arr[2], "de-DE-u-co-phonebk"));  // Returns -1  
document.write (arr[0].localeCompare(arr[3], "de-DE-u-co-phonebk"));  // Returns 1  
  
document.write (arr[0].localeCompare(arr[1], "de-DE"));  // Returns -1  
document.write (arr[0].localeCompare(arr[2], "de-DE"));  // Returns -1  
document.write (arr[0].localeCompare(arr[3], "de-DE"));  // Returns 1  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
 `locales` 및 `options` 매개 변수:  
  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]  
  
## 참고 항목  
 [toLocaleString 메서드\(Object\)](../../javascript/reference/tolocalestring-method-object-javascript.md)