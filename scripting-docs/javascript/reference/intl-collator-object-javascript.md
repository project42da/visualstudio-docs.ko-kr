---
title: "Intl.Collator 개체(JavaScript) | Microsoft Docs"
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
  - "Collator"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
ms.assetid: acbb9461-f956-4b5b-ae5f-6a47815ae15c
caps.latest.revision: 14
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 14
---
# Intl.Collator 개체(JavaScript)
로캘별 문자열 비교를 제공합니다.  
  
## 구문  
  
```  
collatorObj = new Intl.Collator([locales][, options])  
```  
  
#### 매개 변수  
 `collatorObj`  
 필수 요소.  `Collator` 개체를 할당할 변수 이름입니다.  
  
 `locales`  
 선택 사항입니다.  하나 이상의 언어 또는 로캘 태그를 포함한 로캘 문자열의 배열입니다.  두 개 이상의 로캘 문자열을 포함하는 경우, 첫 번째 항목이 기본 설정 로캘이 되도록 우선 순위를 내림차순으로 나열합니다.  이 매개 변수를 생략하면 JavaScript 런타임 기본 로캘이 사용됩니다.  자세한 내용은 설명 부분을 참조하십시오.  
  
 `options`  
 선택 사항입니다.  비교 옵션을 지정하는 하나 이상의 속성을 포함하는 개체입니다.  자세한 내용은 설명 부분을 참조하십시오.  
  
## 설명  
 `locales` 매개 변수는 [BCP 47](http://tools.ietf.org/html/rfc5646) 언어 또는 "en\-US" 또는 "zh\-Hans\-CN"과 같은 로캘 태그를 따라야 합니다.  태그에는 언어, 지역, 국가 및 변수가 포함될 수 있습니다.  언어 목록을 보려면 [IANA 언어 하위 태그 레지스트리](http://go.microsoft.com/fwlink/p/?linkid=227303)를 참조하십시오.  언어 태그의 예를 보려면 BCP 47의 [Appendix A](http://tools.ietf.org/html/rfc5646#appendix-A)를 참조하십시오.  `Collator`의 경우 로캘 문자열에 \-u 확장을 포함시켜 다음 Unicode 확장명 중 1개 이상을 지정할 수 있습니다.  
  
-   변형 데이터 정렬을 지정하려는 경우 \-co\(로캘에 따라 다름\): "*language*\-*region*\-u\-co\-*value*".  
  
-   숫자 비교를 지정하는 \-kn: "*language*\-*region*\-u\-kn\-true&#124;false".  
  
-   첫 번째 대문자 또는 소문자를 정렬할지 여부를 지정하는 –kf: "*language*\-*region*\-u\-kf\-upper&#124;lower&#124;false"\).  이 확장은 현재 지원되지 않습니다.  
  
 숫자 비교를 지정하려면 로캘 문자열에 –kn 확장을 설정하거나 `options` 매개 변수의 `numeric` 속성을 사용합니다.  `numeric` 속성을 사용 중인 경우 –kn 값이 적용되지 않습니다.  
  
 `options` 매개 변수는 다음 속성을 포함할 수 있습니다.  
  
-   `localeMatcher`.  사용할 로캘 일치 알고리즘을 지정합니다.  가능한 값은 "조회" 및 "최적"입니다.  기본값은 "best fit"입니다.  
  
-   `usage`.  비교의 목표가 정렬인지 또는 검색인지를 지정합니다.  가능한 값은 "정렬" 및 "검색"입니다.  기본값은 "sort"입니다.  
  
-   `sensitivity`.  병합기의 민감도 지정합니다.  가능한 값은 "기본", "악센트", "사례" 및 "변형"입니다.  기본값은 `undefined`입니다.  
  
-   `ignorePunctuation`.  비교에서 문장 부호가 무시되는지 여부를 지정합니다.  가능한 값은 "true"와 "false"뿐입니다.  기본값은 `false`입니다.  
  
-   `numeric`.  숫자 정렬을 사용할지 여부를 지정합니다.  가능한 값은 "true"와 "false"뿐입니다.  기본값은 `false`입니다.  
  
-   `caseFirst`.  현재 지원되지 않습니다.  
  
## 속성  
 다음 표에서는 `Collator` 개체의 속성을 보여 줍니다.  
  
|||  
|-|-|  
|속성|설명|  
|[compare](../../javascript/reference/compare-property-intl-collator.md)|병합기의 정렬 순서를 사용해서 두 문자열을 비교하는 함수를 반환합니다.|  
|[생성자](../../javascript/reference/constructor-property-intl-collator.md)|수집기를 만드는 함수를 지정합니다.|  
|[프로토타입\(Prototype\)](../../javascript/reference/prototype-property-intl-collator.md)|병합기의 프로토타입에 대한 참조를 반환합니다.|  
  
## 메서드  
 다음 표에서는 `Collator` 개체의 메서드를 보여 줍니다.  
  
|||  
|-|-|  
|방법|설명|  
|[resolvedOptions](../../javascript/reference/resolvedoptions-method-intl-collator.md)|병합기의 속성과 값이 들어 있는 개체를 반환합니다.|  
  
## 예제  
 다음 예제는 `Collator` 개체를 만들고 비교를 수행합니다.  
  
```javascript  
var co = new Intl.Collator(["de-DE"]);  
co.compare("a", "b"); // Returns -1  
  
```  
  
## 예제  
 다음 예제는 `Collator` 개체를 이용하여 배열을 정렬합니다.  이 예제에는 로캘별 차이가 표시됩니다.  
  
```javascript  
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
  
## 예제  
 다음 예제는 `Collator` 개체를 사용하여 문자열을 검색하고 비교 옵션을 지정합니다.  
  
```javascript  
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
  
## 요구 사항  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]  
  
## 참고 항목  
 [localeCompare 메서드\(String\)](../../javascript/reference/localecompare-method-string-javascript.md)   
 [Intl.DateTimeFormat 개체](../../javascript/reference/intl-datetimeformat-object-javascript.md)   
 [Intl.NumberFormat 개체](../../javascript/reference/intl-numberformat-object-javascript.md)