---
title: "compare 속성(Intl.Collator) | Microsoft Docs"
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
ms.assetid: 59f274dc-6e52-4344-8d5c-b9f0000b66e0
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# compare 속성(Intl.Collator)
병합기의 정렬 순서를 사용해서 두 문자열을 비교하는 함수를 반환합니다.  
  
## 구문  
  
```javascript  
collatorObj.compare  
```  
  
#### 매개 변수  
 `collatorObj`  
 필수 요소.  비교에 사용할 `Collator` 개체의 이름입니다.  
  
## 설명  
 `compare` 속성에서 반환되는 함수에는 `x`와`y`라는 두 인수가 있고, `Collator` 개체에 지정된 옵션을 사용하여 `x`와 `y`의 로캘별 비교 결과를 반환합니다.  
  
 비교의 결과는 다음과 같습니다.  
  
-   `x`가 `y`보다 앞에 정렬되는 경우 \-1입니다.  
  
-   `x`가 `y`와 정렬 순서가 같을 경우 0\(영\)입니다.  
  
-   `x`가 `y`보다 뒤에 정렬되는 경우 1입니다.  
  
## 예제  
 다음 예제는 `Collator` 개체를 만들고 비교를 수행합니다.  
  
```javascript  
var co = new Intl.Collator(["de-DE-u-co-phonebk"]);  
  
if (console && console.log) {  
    console.log(co.compare("a", "b")); // Returns -1  
}  
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
 다음 예제는 `Collator` 개체를 사용하여 문자열을 검색합니다.  
  
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
 [Intl.Collator 개체](../../javascript/reference/intl-collator-object-javascript.md)