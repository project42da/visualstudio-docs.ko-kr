---
title: "Intl.NumberFormat 개체 (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: NumberFormat
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 820bc90f-f1e7-457a-b90d-487dfc3a736d
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0dcb02dbe0d7a7eef88750c440a4fbcdde3ea7ee
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="intlnumberformat-object-javascript"></a>Intl.NumberFormat 개체(JavaScript)
로캘별 숫자 서식 기능을 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
numberFormatObj = new Intl.NumberFormat([locales][, options])  
```  
  
#### <a name="parameters"></a>매개 변수  
 `numberFormatObj`  
 필수 요소. `NumberFormat` 개체를 할당할 변수 이름입니다.  
  
 `locales`  
 선택 사항입니다. 하나 이상의 언어 또는 로캘 태그를 포함한 로캘 문자열의 배열입니다. 두 개 이상의 로캘 문자열을 포함하는 경우, 첫 번째 항목이 기본 설정 로캘이 되도록 우선 순위를 내림차순으로 나열합니다. 이 매개 변수를 생략하면 JavaScript 런타임 기본 로캘이 사용됩니다. 자세한 내용은 설명 부분을 참조하세요.  
  
 `options`  
 선택 사항입니다. 숫자 서식 지정 옵션을 지정 하는 하나 이상의 속성을 포함 하는 개체입니다. 자세한 내용은 설명 단원을 참조하십시오.  
  
## <a name="remarks"></a>설명  
 `locales` 매개 변수를 따라야 [BCP 47](http://tools.ietf.org/html/rfc5646) "EN-US" 및 "ZH-CN"와 같은 언어 또는 로캘 태그입니다. 태그에는 언어, 지역, 국가 및 변수가 포함될 수 있습니다. 언어 태그의 예 참조 [부록 A](http://tools.ietf.org/html/rfc5646#appendix-A) BCP 47. 에 대 한 `NumberFormat`를 추가할 수 있습니다는 **-u** 하위 태그 뒤-누 번호 매기기 시스템 확장을 지정 하려면:  
  
 "*언어*-*지역*-u-누-*numberingsystem*"  
  
 여기서 *numberingsystem* 다음 중 하나일 수 있습니다: 아랍, arabext, bali, beng, deva, fullwide, gujr, 전문가, hanidec, khmr, knda, laoo, latn, 뿌리, mylm, mong, mymr, orya, tamldec, telu, 태국어, tibt 합니다.  
  
 `options` 매개 변수는 다음 속성을 포함할 수 있습니다.  
  
|속성|설명|가능한 값|기본값|  
|--------------|-----------------|---------------------|-------------------|  
|`localeMatcher`|사용할 로캘 일치 알고리즘을 지정합니다.|"조회", "가장 적합 한"|"best fit"|  
|`style`|숫자 서식 스타일을 지정합니다.|"10 진수", "%", "currency"|"십진수"|  
|`currency`|알파벳 코드로 ISO 4217 통화 값을 지정합니다. 경우는 `style` 설정 된 "currency"로이 값이 필요 합니다.|ISO 참조 [통화 금액 코드 목록](http://www.currency-iso.org/en/home/tables/table-a1.html)합니다.|undefined|  
|`currencyDisplay`|통화 ISO 4217 통화 알파벳 코드, 지역화 된 통화 기호 또는 지역화 된 통화 이름으로 표시할지 여부를 지정 합니다. 이 값은 경우에 사용 `style` "currency"로 설정 합니다.|"코드", "기호", "이름"|"symbol"|  
|`useGrouping`|자릿수 구분 기호를 사용할 것인지 여부를 지정 합니다.|true, false|`true`.|  
|`minimumIntegerDigits`|사용 하는 정수 계열 자릿수의 최소 수를 지정 합니다.|1-21입니다.|21|  
|`minimumFractionDigits`|입니다. 사용할 소수 자릿수의 최소 수를 지정 합니다.|0 ~ 20입니다.|0|  
|`maximumFractionDigits`|사용할 소수 자릿수의 최대 수를 지정 합니다.|이 값의 범위는 `minimumFractionDigits` 20입니다.|20.|  
|`minimumSignificantDigits`|표시할 소수 자릿수의 최소 수를 지정 합니다.|이 값의 범위는 1에서 21로.|1|  
|`maximumSignificantDigits`|표시할 소수 자릿수의 최대 수를 지정 합니다.|이 값의 범위는 `minimumSignificantDigits` 21로 합니다.|21|  
  
## <a name="properties"></a>속성  
 다음 표에서는 `NumberFormat` 개체의 속성을 보여 줍니다.  
  
|||  
|-|-|  
|속성|설명|  
|[생성자](../../javascript/reference/constructor-property-intl-numberformat.md)|숫자 포맷터 개체를 만드는 함수를 지정 합니다.|  
|[format](../../javascript/reference/format-property-intl-numberformat.md)|숫자 포맷터 설정을 사용 하 여 숫자 형식을 지정 하는 함수를 반환 합니다.|  
|[프로토타입](../../javascript/reference/prototype-property-intl-numberformat.md)|숫자 포맷터에 대 한 프로토타입의에 대 한 참조를 반환합니다.|  
  
## <a name="methods"></a>메서드  
 다음 표에서는 `NumberFormat` 개체의 메서드를 보여 줍니다.  
  
|||  
|-|-|  
|메서드|설명|  
|[resolvedOptions](../../javascript/reference/resolvedoptions-method-intl-numberformat.md)|속성 및 숫자 포맷터 개체의 값을 포함 하는 개체를 반환 합니다.|  
  
## <a name="example"></a>예제  
 다음 예제에서는 한 `NumberFormat` EN-US 로캘 지정된 된 서식 옵션 사용에 대 한 개체입니다.  
  
```JavaScript  
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
  
## <a name="example"></a>예제  
 다음 예에서는 몇 가지 다른 로캘 및 옵션을 사용 하 여 결과 보여 줍니다.  
  
```JavaScript  
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
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [toLocaleString (Number)](../../javascript/reference/tolocalestring-number.md)   
 [Intl.Collator 개체](../../javascript/reference/intl-collator-object-javascript.md)   
 [Intl.DateTimeFormat 개체](../../javascript/reference/intl-datetimeformat-object-javascript.md)