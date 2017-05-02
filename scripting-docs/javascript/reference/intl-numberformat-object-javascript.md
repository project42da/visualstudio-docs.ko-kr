---
title: "Intl.NumberFormat 개체(JavaScript) | Microsoft Docs"
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
  - "NumberFormat"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
ms.assetid: 820bc90f-f1e7-457a-b90d-487dfc3a736d
caps.latest.revision: 13
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 13
---
# Intl.NumberFormat 개체(JavaScript)
로캘별 숫자 형식을 제공합니다.  
  
## 구문  
  
```  
numberFormatObj = new Intl.NumberFormat([locales][, options])  
```  
  
#### 매개 변수  
 `numberFormatObj`  
 필수 요소.  `NumberFormat` 개체를 할당할 변수 이름입니다.  
  
 `locales`  
 선택 사항입니다.  하나 이상의 언어 또는 로캘 태그를 포함한 로캘 문자열의 배열입니다.  두 개 이상의 로캘 문자열을 포함하는 경우, 첫 번째 항목이 기본 설정 로캘이 되도록 우선 순위를 내림차순으로 나열합니다.  이 매개 변수를 생략하면 JavaScript 런타임 기본 로캘이 사용됩니다.  자세한 내용은 설명 부분을 참조하십시오.  
  
 `options`  
 선택 사항입니다.  숫자 서식지정 옵션을 지정하는 하나 이상의 속성을 포함하는 개체입니다.  자세한 내용은 설명 부분을 참조하십시오.  
  
## 설명  
 `locales` 매개 변수는 [BCP 47](http://tools.ietf.org/html/rfc5646) 언어 또는 "en\-US" 및 "zh\-CN"과 같은 로캘 태그를 따라야 합니다.  태그에는 언어, 지역, 국가 및 변수가 포함될 수 있습니다.  언어 태그의 예를 보려면 BCP 47의 [Appendix A](http://tools.ietf.org/html/rfc5646#appendix-A)를 참조하십시오.  `NumberFormat`의 경우 **\-u** 하위 태그와 그 다음에 \-nu를 추가하여 번호 매기기 체계 확장을 지정할 수 있습니다.  
  
 "*language*\-*region*\-u\-nu\-*numberingsystem*"  
  
 여기서 *numberingsystem*은 arab, arabext, bali, beng, deva, fullwide, gujr, guru, hanidec, khmr, knda, laoo, latn, limb, mylm, mong, mymr, orya, tamldec, telu, thai, tibt 중 하나입니다.  
  
 `options` 매개 변수는 다음 속성을 포함할 수 있습니다.  
  
|속성|설명|가능한 값|기본값|  
|--------|--------|-----------|---------|  
|`localeMatcher`|사용할 로캘 일치 알고리즘을 지정합니다.|"조회", "최적"|"최적"|  
|`style`|숫자 형식 스타일을 지정합니다.|"10진수", "백분율", "통화"|"decimal"|  
|`currency`|ISO 4217 통화 값을 영문자 코드로 지정합니다.  `style`이 "통화"로 설정된 경우 이 값이 필요합니다.|ISO [통화 및 펀드 코드 목록](http://www.currency-iso.org/en/home/tables/table-a1.html)을 참조하십시오.|undefined|  
|`currencyDisplay`|통화가 ISO 4217 알파벳 통화 코드, 지역화된 통화 기호, 또는 지역화된 통화 이름으로 표시되어 있는지 여부를 지정합니다.  이 값은 `style`이 "currency"로 설정된 경우에만 사용됩니다.|"코드", "기호", "이름"|"symbol"|  
|`useGrouping`|그룹화 구분 기호를 사용할지 여부를 지정합니다.|true, false|`true`.|  
|`minimumIntegerDigits`|사용할 최소 정수 자릿수를 지정합니다.|1~21|21|  
|`minimumFractionDigits`|.  사용할 최소 소수 자릿수를 지정합니다.|0~20|0|  
|`maximumFractionDigits`|사용할 최대 소수 자릿수를 지정합니다.|이 값은 `minimumFractionDigits`에서 20 사이의 값으로 설정할 수 있습니다.|20.|  
|`minimumSignificantDigits`|표시할 최소 소수 자릿수를 지정합니다.|이 값은 1에서 21 사이의 값으로 설정할 수 있습니다.|1|  
|`maximumSignificantDigits`|표시할 최대 소수 자릿수를 지정합니다.|이 값은 `minimumSignificantDigits`에서 21 사이의 값으로 설정할 수 있습니다.|21|  
  
## 속성  
 다음 표에서는 `NumberFormat` 개체의 속성을 보여 줍니다.  
  
|||  
|-|-|  
|속성|설명|  
|[생성자](../../javascript/reference/constructor-property-intl-numberformat.md)|숫자 포맷터 개체를 만드는 함수를 지정합니다.|  
|[format](../../javascript/reference/format-property-intl-numberformat.md)|숫자 포맷터 설정을 사용해서 숫자 형식을 지정하는 함수를 반환합니다.|  
|[프로토타입\(Prototype\)](../../javascript/reference/prototype-property-intl-numberformat.md)|숫자 포맷터의 프로토타입에 대한 참조를 반환합니다.|  
  
## 메서드  
 다음 표에서는 `NumberFormat` 개체의 메서드를 보여 줍니다.  
  
|||  
|-|-|  
|방법|설명|  
|[resolvedOptions](../../javascript/reference/resolvedoptions-method-intl-numberformat.md)|숫자 포맷터 개체의 속성 및 값이 포함된 개체를 반환합니다.|  
  
## 예제  
 다음 예제는 지정된 서식 옵션을 사용하여 en\-US 로캘에 대한 `NumberFormat` 개체를 만듭니다.  
  
```javascript  
var nf = new Intl.NumberFormat(["en-US"], {  
    style: "currency",  
    currency: "CNY",  
    currencyDisplay: "symbol",  
    maximumFractionDigit: 1  
});  
  
if (console && console.log) {  
    console.log(nf.format(100)); // Returns ¥100.00  
}  
```  
  
## 예제  
 다음 예제는 여러 로캘 및 옵션을 사용한 결과를 보여 줍니다.  
  
```javascript  
var number = 123456789;  
var options1 = { style: "percent" };  
var options2 = { style: "currency", currency: "INR" };  
  
if (console && console.log) {  
    console.log(new Intl.NumberFormat("en-US").format(number));  
    // Returns 123,456,789  
    console.log(new Intl.NumberFormat("ja-JP").format(number));  
    // Returns 123,456,789  
    console.log(new Intl.NumberFormat("ar-SA", options1).format(number));  
    // Returns ١٢,٣٤٥,٦٧٨,٩٠٠ %  
    console.log(new Intl.NumberFormat("hi-IN", options2).format(number));  
    // Returns ₹ 12,34,56,789.00  
}  
```  
  
## 요구 사항  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]  
  
## 참고 항목  
 [toLocaleString\(Number\)](../../javascript/reference/tolocalestring-number.md)   
 [Intl.Collator 개체](../../javascript/reference/intl-collator-object-javascript.md)   
 [Intl.DateTimeFormat 개체](../../javascript/reference/intl-datetimeformat-object-javascript.md)