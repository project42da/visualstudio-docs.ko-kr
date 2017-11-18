---
title: "Intl.DateTimeFormat 개체 (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: DateTimeFormat
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: cc555ac2-f31c-4239-a612-b84c08e3a37f
caps.latest.revision: "14"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9c50d6d7d939ebe05ce3ff9b434111413803ea40
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="intldatetimeformat-object-javascript"></a>Intl.DateTimeFormat 개체(JavaScript)
로캘별 날짜 및 시간 서식 기능을 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
dateTimeFormatObj = new Intl.DateTimeFormat([locales][, options])  
```  
  
#### <a name="parameters"></a>매개 변수  
 `dateTimeFormatObj`  
 필수 요소. `DateTimeFormat` 개체를 할당할 변수 이름입니다.  
  
 `locales`  
 선택 사항입니다. 하나 이상의 언어 또는 로캘 태그를 포함한 로캘 문자열의 배열입니다. 두 개 이상의 로캘 문자열을 포함하는 경우, 첫 번째 항목이 기본 설정 로캘이 되도록 우선 순위를 내림차순으로 나열합니다. 이 매개 변수를 생략하면 JavaScript 런타임 기본 로캘이 사용됩니다. 자세한 내용은 설명 부분을 참조하세요.  
  
 `options`  
 선택 사항입니다. 날짜와 시간에 대한 형식 지정 옵션을 지정하는 하나 이상의 속성을 포함하는 개체입니다. 자세한 내용은 설명 단원을 참조하십시오.  
  
## <a name="remarks"></a>설명  
 `locales` 매개 변수를 따라야 [BCP 47](http://tools.ietf.org/html/rfc5646) "EN-US" 및 "ZH-CN"와 같은 언어 또는 로캘 태그입니다. 태그에는 언어, 지역, 국가 및 변수가 포함될 수 있습니다. 언어 태그의 예 참조 [부록 A](http://tools.ietf.org/html/rfc5646#appendix-A) BCP 47. 에 대 한 `DateTimeFormat`를 추가할 수 있습니다는 **-u** 다음 유니코드 확장명 중 하나 이상을 포함할 경우 로캘 문자열에 하위 태그:  
  
-   -번호 매기기 시스템 확장을 지정 하려면 다음: *언어*-*지역*-u-누-*numberingsystem*  
  
     여기서 *numberingsystem* 다음 중 하나일 수 있습니다: 아랍, arabext, bali, beng, deva, fullwide, gujr, 전문가, hanidec, khmr, knda, laoo, latn, 뿌리, mylm, mong, mymr, orya, tamldec, telu, 태국어, tibt 합니다.  
  
-   일정을 지정 하려면-ca: *언어*-*지역*-u-ca-*달력*  
  
     여기서 *달력* 다음 중 하나일 수 있습니다: 불교, 중국어, gregory 이슬람, islamicc, 일본어입니다.  
  
 `options` 매개 변수는 다음 속성을 포함할 수 있습니다.  
  
|속성|설명|가능한 값|기본값|  
|--------------|-----------------|---------------------|-------------------|  
|`localeMatcher`|사용할 로캘 일치 알고리즘을 지정합니다.|"lookup","best fit"|"best fit"|  
|`formatMatcher`|사용할 형식 일치 알고리즘을 지정합니다.|"basic", "best fit"|"best fit"|  
|`hour12`|12시간 형식의 시간을 사용할지 여부를 지정합니다.|`true`(12시간 형식), `false`(24시간 형식)||  
|`timeZone`|표준 시간대를 지정합니다. 최소한 "UTC"는 항상 지원됩니다.|"UTC"와 같은 표준 시간대 값입니다.|"UTC"|  
|`weekday`|요일의 형식을 지정합니다.|"narrow", "short", "long".|undefined|  
|`era`|연대의 형식을 지정합니다.|"narrow", "short", "long"|undefined|  
|`year`|연도의 형식을 지정합니다.|"2-digit", "numeric"|undefined 또는 "numeric"|  
|`month`|월의 형식을 지정합니다.|"2-digit", "numeric", "narrow", "short", "long"|undefined 또는 "numeric"|  
|`day`|요일 형식을 지정합니다.|"2-digit", "numeric"|undefined 또는 "numeric"|  
|`hour`|시간의 형식을 지정합니다.|"2-digit", "numeric"|undefined|  
|`minute`|분의 형식을 지정합니다.|"2-digit", "numeric"|undefined|  
|`second`|초의 형식을 지정합니다.|"2-digit", "numeric"|undefined|  
|`timeZoneName`|표준 시간대의 형식을 지정합니다. 현재 이 속성이 지원되지 않는 경우|"short", "long".|현재 이 속성이 지원되지 않는 경우|  
  
 `weekday`, `era`, `year`, `month`, `day`, `hour`, `minute` 및 `second`의 기본값은 `undefined`입니다. 이러한 속성을 설정하지 않으면 "numeric" 형식이 `year`, `month` 및 `day`에 사용됩니다.  
  
 각 로캘은 최소한 다음 형식을 지원해야 합니다.  
  
-   요일, 연도, 월, 일, 시, 분, 초  
  
-   요일, 연도, 월, 일  
  
-   연도, 월, 일  
  
-   연도, 월  
  
-   월, 일  
  
-   시, 분, 초  
  
-   시, 분  
  
## <a name="properties"></a>속성  
 다음 표에서는 `DateTimeFormat` 개체의 속성을 보여 줍니다.  
  
|||  
|-|-|  
|속성|설명|  
|[생성자](../../javascript/reference/constructor-property-intl-datetimeformat.md)|날짜/시간 포맷터 개체를 만드는 함수를 지정합니다.|  
|[format](../../javascript/reference/format-property-intl-datetimeformat.md)|날짜/시간 포맷터 설정을 사용하여 로캘별 날짜 형식을 지정하는 함수를 반환합니다.|  
|[프로토타입](../../javascript/reference/prototype-property-intl-datetimeformat.md)|날짜/시간 포맷터의 프로토타입에 대한 참조를 반환합니다.|  
  
## <a name="methods"></a>메서드  
 다음 표에서는 `DateTimeFormat` 개체의 메서드를 보여 줍니다.  
  
|||  
|-|-|  
|메서드|설명|  
|[resolvedOptions](../../javascript/reference/resolvedoptions-method-intl-datetimeformat.md)|날짜/시간 포맷터 개체의 속성 및 값이 포함된 개체를 반환합니다.|  
  
## <a name="example"></a>예제  
 다음 예제에서는 여러 로캘을 사용하여 날짜 개체를 `DateTimeFormat`으로 전달하는 결과를 보여 줍니다.  
  
```JavaScript  
var date = new Date(Date.UTC(2013, 1, 1, 14, 0, 0));  
var options = { weekday: "long", year: "numeric", month: "short",  
    day: "numeric" };  
  
if (console && console.log) {  
    console.log(new Intl.DateTimeFormat("en-US").format(date));  
    // Returns ‎2‎/‎1‎/‎2013  
    console.log(new Intl.DateTimeFormat("ja-JP").format(date));  
    // Returns ‎2013‎年‎2‎月‎1‎日  
    console.log(new Intl.DateTimeFormat("ar-SA", options).format(date));  
    // Returns ‏الجمعة‏, ‏٢٠‏ ‏ربيع الأول‏, ‏١٤٣٤  
    console.log(new Intl.DateTimeFormat("hi-IN", options).format(date));  
    // Returns ‎शुक्रवार‎, ‎01‎ ‎फरवरी‎ ‎2013  
}  
```  
  
## <a name="example"></a>예제  
 다음 예제에서는 아랍어(사우디아라비아) 로캘, 이슬람력 및 라틴 번호 지정 시스템을 사용하는 긴 형식으로 현재 요일을 지정하는 `DateTimeFormat` 개체를 만듭니다.  
  
```JavaScript  
var dtf = new Intl.DateTimeFormat(["ar-SA-u-ca-islamic-nu-latn"], {  
    weekday: "long",  
    year: "numeric",  
    day: "numeric",  
    month: "long"  
});   
  
If (console && console.log) {  
    console.log(dtf.format(new Date()));  
    // Returns ‏الجمعة‏, ‏19‏ ‏رمضان‏, ‏1434  
}  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [toLocaleString (Date)](../../javascript/reference/tolocalestring-date.md)   
 [toLocaleDateString 메서드 (Date)](../../javascript/reference/tolocaledatestring-method-date-javascript.md)   
 [toLocaleTimeString 메서드 (Date)](../../javascript/reference/tolocaletimestring-method-date-javascript.md)   
 [Intl.Collator 개체](../../javascript/reference/intl-collator-object-javascript.md)   
 [Intl.NumberFormat 개체](../../javascript/reference/intl-numberformat-object-javascript.md)