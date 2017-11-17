---
title: "compare 속성 (Intl.Collator) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 59f274dc-6e52-4344-8d5c-b9f0000b66e0
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5bfd222ac8d2c94efe279177e7f4d8ffdf850f44
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="compare-property-intlcollator"></a>compare 속성(Intl.Collator)
병합 장치 정렬 순서를 사용 하 여 두 문자열을 비교 하는 함수를 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```JavaScript  
collatorObj.compare  
```  
  
#### <a name="parameters"></a>매개 변수  
 `collatorObj`  
 필수 요소. 이름에서 `Collator` 비교에 사용할 개체입니다.  
  
## <a name="remarks"></a>설명  
 반환 하는 함수는 `compare` 속성은 두 개의 인수를 사용 `x` 및 `y`, 로캘 관련 비교의 결과 반환 하 고 `x` 및 `y` 에 지정 된 옵션을 사용 하 여는 `Collator` 개체입니다.  
  
 비교의 결과가 됩니다.  
  
-   -없으면 1 `x` 앞 `y` 정렬 순서에서.  
  
-   0 이면 0 `x` 같으면 `y` 정렬 순서에서.  
  
-   이면 1 `x` 후 `y` 정렬 순서에서.  
  
## <a name="example"></a>예제  
 다음 예제에서는 한 `Collator` 개체를 비교를 수행 합니다.  
  
```JavaScript  
var co = new Intl.Collator(["de-DE-u-co-phonebk"]);  
  
if (console && console.log) {  
    console.log(co.compare("a", "b")); // Returns -1  
}  
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
 다음 예제에서는 한 `Collator` 문자열을 검색 하는 개체입니다.  
  
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
 [Intl.Collator 개체](../../javascript/reference/intl-collator-object-javascript.md)