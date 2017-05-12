---
title: "toLocaleTimeString 메서드(Date)(JavaScript) | Microsoft Docs"
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
  - "toLocaleTimeString"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "toLocaleTimeString 메서드"
ms.assetid: 8ad75bf5-864c-4a2a-be90-220e87dce172
caps.latest.revision: 15
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 15
---
# toLocaleTimeString 메서드(Date)(JavaScript)
호스트 환경의 현재 로캘 또는 지정된 로캘에 적합한 문자열 값으로 시간을 반환합니다.  
  
## 구문  
  
```  
  
dateObj.toLocaleTimeString([locales][, options])  
```  
  
#### 매개 변수  
 `dateObj`  
 필수.  `Date` 개체입니다.  
  
 `locales`  
 선택 사항입니다.  하나 이상의 언어 또는 로캘 태그를 포함한 로캘 문자열의 배열입니다.  두 개 이상의 로캘 문자열을 포함하는 경우, 첫 번째 항목이 기본 설정 로캘이 되도록 우선 순위를 내림차순으로 나열합니다.  이 매개 변수를 생략하면 JavaScript 런타임 기본 로캘이 사용됩니다.  
  
 `options`  
 선택 사항입니다.  비교 옵션을 지정하는 하나 이상의 속성이 포함된 개체입니다.  
  
## 설명  
 Internet Explorer 11부터 `toLocaleTimeString`은 내부적으로 `Intl.DateTimeFormat`을 사용하여 시간 형식을 지정하며 이에 따라 `locales` 및 `options` 매개 변수에 대한 지원이 추가되었습니다.  이러한 매개 변수에 대한 자세한 내용은 [Intl.DateTimeFormat](../../javascript/reference/intl-datetimeformat-object-javascript.md)을 참조하세요.  
  
> [!IMPORTANT]
>  `locales` 및 `options` 매개 변수는 일부 문서 모드 및 브라우저 버전에서는 지원되지 않습니다.  자세한 내용은 요구 사항 섹션을 참조하세요.  
  
 `toLocaleTimeString`을 Internet Explorer 10 표준 문서 모드, 이전 문서 모드, 쿼크 모드에서 사용하는 경우  
  
-   현재 표준 시간대의 시간이 포함된 문자열 값을 반환합니다.  
  
-   반환되는 값은 호스트 환경의 현재 로캘의 기본 형식입니다.  
  
 `locales` 매개 변수를 생략하는 경우에는 이 메서드의 반환 값이 컴퓨터마다 달라지므로 이 값에 의존하여 스크립팅할 수 없습니다.  이 시나리오에서는 표시되는 텍스트의 서식을 지정하는 데만 이 메서드를 사용하며 계산의 일부로는 사용하지 않습니다.  
  
## 예제  
 다음 예제에서는 지정된 로캘 및 비교 옵션과 함께 `toLocaleTimeString` 메서드를 사용하는 방법을 보여 줍니다.  
  
```javascript  
var date = new Date(Date.UTC(2013, 1, 1, 14, 0, 0));  
var options = { weekday: "long", year: "numeric", month: "short",  
    day: "numeric" };  
  
// Using I18N toLocaleString  
document.write(date.toLocaleTimeString("en-US"));  
document.write(date.toLocaleTimeString("ja-JP"));  
document.write(date.toLocaleTimeString("ar-SA", options));  
document.write(date.toLocaleTimeString("hi-IN", options));  
  
// Output:  
// ‎‎6‎:‎00‎:‎00‎ ‎AM ‎   
// 6‎:‎00‎:‎00‎  
// ‏الجمعة‏, ‏٢٠‏ ‏ربيع الأول‏, ‏١٤٣٤ ٠٦‎:‎٠٠‎:‎٠٠‎ ‎ص  
// ‎शुक्रवार‎, ‎01‎ ‎फरवरी‎ ‎2013 06:00:00  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
 `locales` 및 `options` 매개 변수:  
  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]  
  
## 참고 항목  
 [toTimeString 메서드\(Date\)](../../javascript/reference/totimestring-method-date-javascript.md)   
 [toLocaleDateString 메서드\(Date\)](../../javascript/reference/tolocaledatestring-method-date-javascript.md)