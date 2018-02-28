---
title: "Intl.Collator 개체 (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- Collator
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: acbb9461-f956-4b5b-ae5f-6a47815ae15c
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b9a41507face20285124257be95197ef5ea53ef6
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="intlcollator-object-javascript"></a>Intl.Collator 개체(JavaScript)
로캘별 문자열 비교 기능을 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
collatorObj = new Intl.Collator([locales][, options])  
```  
  
#### <a name="parameters"></a>매개 변수  
 `collatorObj`  
 필수 요소. `Collator` 개체를 할당할 변수 이름입니다.  
  
 `locales`  
 선택 사항입니다. 하나 이상의 언어 또는 로캘 태그를 포함한 로캘 문자열의 배열입니다. 두 개 이상의 로캘 문자열을 포함하는 경우, 첫 번째 항목이 기본 설정 로캘이 되도록 우선 순위를 내림차순으로 나열합니다. 이 매개 변수를 생략하면 JavaScript 런타임 기본 로캘이 사용됩니다. 자세한 내용은 설명 부분을 참조하세요.  
  
 `options`  
 선택 사항입니다. 비교 옵션을 지정하는 하나 이상의 속성이 포함된 개체입니다. 자세한 내용은 설명 단원을 참조하십시오.  
  
## <a name="remarks"></a>설명  
 `locales` 매개 변수를 따라야 [BCP 47](http://tools.ietf.org/html/rfc5646) "EN-US" 및 "Hans-ZH-CN"와 같은 언어 또는 로캘 태그입니다. 태그에는 언어, 지역, 국가 및 변수가 포함될 수 있습니다. 목록이 언어에 대 한 참조는 [IANA 언어 하위 태그 레지스트리](http://go.microsoft.com/fwlink/p/?linkid=227303)합니다. 언어 태그의 예 참조 [부록 A](http://tools.ietf.org/html/rfc5646#appendix-A) BCP 47. 에 대 한 `Collator`, 다음 유니코드 확장명 중 하나 이상을 지정할 경우 로캘 문자열에서-u 확장명을 포함할 수 있습니다.  
  
-   variant 데이터 정렬 (로캘별)을 지정 하려면-co: "*언어*-*지역*-u-공변성*값*"입니다.  
  
-   숫자 비교를 지정 하려면-kn: "*언어*-*지역*-u-kn-true &#124; false"입니다.  
  
-   -대문자 또는 소문자 문자를 먼저 정렬 여부를 지정 하려면 kf: "*언어*-*지역*-u kf 위의 &#124; 하위 &#124; false"). 이 확장은 현재 지원 되지 않습니다.  
  
 숫자 비교를 지정 하려면-kn 확장 로캘 문자열에 설정 하거나 사용할 수 있습니다는 `numeric` 속성에는 `options` 매개 변수입니다. 사용 중인 경우는 `numeric` 속성-kn 값 적용 되지 것입니다.  
  
 `options` 매개 변수는 다음 속성을 포함할 수 있습니다.  
  
-   `localeMatcher`. 사용할 로캘 일치 알고리즘을 지정합니다. 가능한 값은 "조회" 및 "가장 적합 한"입니다. 기본값은 "자동 맞춤"입니다.  
  
-   `usage`. 비교의 목표 검색 정렬 여부를 지정 합니다. 가능한 값은 "sort" 및 "검색" 합니다. 기본값은 "정렬"입니다.  
  
-   `sensitivity`. 병합기의 민감도 지정합니다. 가능한 값은 "기본", "악센트 기호", "대/소문자" 및 "variant" 됩니다. 기본값은 `undefined`입니다.  
  
-   `ignorePunctuation`. 비교에 사용 된 문장 부호는 무시 하는지 여부를 지정 합니다. 가능한 값은 "true" 및 "false"입니다. 기본값은 `false`입니다.  
  
-   `numeric`. 숫자 정렬 사용 되는지 여부를 지정 합니다. 가능한 값은 "true" 및 "false"입니다. 기본값은 `false`입니다.  
  
-   `caseFirst`. 현재 지원되지 않습니다.  
  
## <a name="properties"></a>속성  
 다음 표에서는 `Collator` 개체의 속성을 보여 줍니다.  
  
|||  
|-|-|  
|속성|설명|  
|[compare](../../javascript/reference/compare-property-intl-collator.md)|병합 장치 정렬 순서를 사용 하 여 두 문자열을 비교 하는 함수를 반환 합니다.|  
|[생성자](../../javascript/reference/constructor-property-intl-collator.md)|병합 하는 장치를 만드는 함수를 지정 합니다.|  
|[프로토타입](../../javascript/reference/prototype-property-intl-collator.md)|병합 하는 장치에 대 한 프로토타입의에 대 한 참조를 반환합니다.|  
  
## <a name="methods"></a>메서드  
 다음 표에서는 `Collator` 개체의 메서드를 보여 줍니다.  
  
|||  
|-|-|  
|메서드|설명|  
|[resolvedOptions](../../javascript/reference/resolvedoptions-method-intl-collator.md)|속성 및는 병합기의 값을 포함 하는 개체를 반환 합니다.|  
  
## <a name="example"></a>예제  
 다음 예제에서는 한 `Collator` 개체를 비교를 수행 합니다.  
  
```JavaScript  
var co = new Intl.Collator(["de-DE"]);  
co.compare("a", "b"); // Returns -1  
  
```  
  
## <a name="example"></a>예제  
 다음 예제에서는 `Collator` 배열을 정렬 하는 개체입니다. 이 예제에서는 로캘 관련 차이점을 보여 줍니다.  
  
```JavaScript  
var co1 = new Intl.Collator(["de-DE-u-co-phonebk"]);  
var co2 = new Intl.Collator(["de-DE"]);  
var co3 = new Intl.Collator(["en-US"]);  
  
var arr = ["ä", "ad", "af", "a"];  
  
if (console && console.log) {  
    console.log(arr.sort(co1.compare));  // Returns a,ad,ä,af  
    console.log(arr.sort(co2.compare));  // Returns a,ä,ad,af  
    console.log(arr.sort(co3.compare));  // Returns a,ä,ad,af  
}  
```  
  
## <a name="example"></a>예제  
 다음 예제에서는 한 `Collator` 는 문자열을 검색 하려면 개체를 비교 옵션을 지정 합니다.  
  
```JavaScript  
// String to search  
var arr = ["ä", "ad", "af", "a"];  
// String searched for  
var s = "af";  
  
var co = new Intl.Collator("de-DE", { usage: "search" });  
var matches = arr.filter(function (i) {  
    return co.compare(i, s) === 0;  
});  
  
if (console && console.log) {  
    console.log(matches);  // Returns af  
}  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [localeCompare 메서드 (String)](../../javascript/reference/localecompare-method-string-javascript.md)   
 [Intl.DateTimeFormat 개체](../../javascript/reference/intl-datetimeformat-object-javascript.md)   
 [Intl.NumberFormat 개체](../../javascript/reference/intl-numberformat-object-javascript.md)