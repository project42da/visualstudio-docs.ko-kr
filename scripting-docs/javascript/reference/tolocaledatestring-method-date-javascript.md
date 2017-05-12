---
title: "toLocaleDateString 메서드(Date)(JavaScript) | Microsoft Docs"
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
  - "toLocaleDateString"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "toLocaleDateString 메서드"
ms.assetid: 0b83715c-8ced-4bd7-8940-a8007d002d10
caps.latest.revision: 14
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 14
---
# toLocaleDateString 메서드(Date)(JavaScript)
호스트 환경의 현재 로캘 또는 지정된 로캘에 해당하는 문자열 값으로 날짜를 반환합니다.  
  
## 구문  
  
```  
  
dateObj.toLocaleDateString( [locales][, options])   
```  
  
#### 매개 변수  
 `dateObj`  
 필수 요소.  `Date` 개체  
  
 `locales`  
 선택 사항입니다.  하나 이상의 언어 또는 로캘 태그를 포함한 로캘 문자열의 배열입니다.  두 개 이상의 로캘 문자열을 포함하는 경우, 첫 번째 항목이 기본 설정 로캘이 되도록 우선 순위를 내림차순으로 나열합니다.  이 매개 변수를 생략하면 JavaScript 런타임 기본 로캘이 사용됩니다.  
  
 `options`  
 선택 사항입니다.  비교 옵션을 지정하는 하나 이상의 속성을 포함하는 개체입니다.  
  
## 설명  
 Internet Explorer 11부터 `toLocaleDateString`은 `locales` 및 `options` 매개 변수에 대한 지원을 추가하는 `Intl.DateTimeFormat` 날짜를 내부적으로 사용합니다.  이러한 매개 변수에 대한 자세한 내용은 [Intl.DateTimeFormat](../../javascript/reference/intl-datetimeformat-object-javascript.md)을 참조하십시오.  
  
> [!IMPORTANT]
>  `locales` 및 `options` 매개 변수는 모든 문서 모드와 브라우저 버전에서 지원되지 않습니다.  자세한 내용은 요구 사항 부분을 참조하십시오.  
  
 Internet Explorer 10 표준 문서 모드, 이전 문서 모드 및 특수 모드에서 `toLocaleDateString`을 사용하는 경우:  
  
-   현재 표준 시간대의 날짜를 포함하는 문자열 값을 반환합니다.  
  
-   반환된 날짜는 호스트 환경의 현재 로캘 기본 서식으로 되어 있습니다.  
  
 `locales` 매개 변수를 생략하는 경우 이 메서드의 반환 값은 컴퓨터마다 다르므로 스크립팅에서 의존할 수 없습니다.  이 시나리오에서는 메서드를 표시된 텍스트의 서식을 지정하는 데만 사용합니다. 계산의 일부로는 사용하지 않습니다.  
  
## 예제  
 다음 예제는 `toLocaleDateString` 메서드를 지정된 로캘 및 비교 옵션과 함께 사용하는 방법을 보여 줍니다.  
  
```javascript  
var date = new Date(Date.UTC(2013, 1, 1, 14, 0, 0));  
var options = { weekday: "long", year: "numeric", month: "short",  
    day: "numeric" };  
  
// Using I18N toLocaleString  
document.write(date.toLocaleDateString("en-US"));  
document.write(date.toLocaleDateString("ja-JP"));  
document.write(date.toLocaleDateString("ar-SA", options));  
document.write(date.toLocaleDateString("hi-IN", options));  
  
// Output:  
// ‎2‎/‎1‎/‎2013‎   
// ‎2013‎年‎2‎月‎1‎日‎  
// ‏الجمعة‏, ‏٢٠‏ ‏ربيع الأول‏, ‏١٤٣٤  
// ‎शुक्रवार‎, ‎01‎ ‎फरवरी‎ ‎2013  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
 `locales` 및 `options` 매개 변수:  
  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]  
  
## 참고 항목  
 [toDateString 메서드\(Date\)](../../javascript/reference/todatestring-method-date-javascript.md)   
 [toLocaleTimeString 메서드\(Date\)](../../javascript/reference/tolocaletimestring-method-date-javascript.md)