---
title: "localeCompare 메서드 (String) (JavaScript) | Microsoft Docs"
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
- localeCompare
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- localeCompare method
ms.assetid: 66914079-12dd-4393-a84c-c05f58231c36
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 056a440d26c4ebf48bd762968fa32ea1efdfb443
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="localecompare-method-string-javascript"></a>localeCompare 메서드(String)(JavaScript)
두 문자열의 현재 로캘이 동일한 지 여부를 결정 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
stringVar.localeCompare(stringExp[, locales][, options])   
```  
  
## <a name="parameters"></a>매개 변수  
 `stringVar`  
 필수 요소. 비교할 첫째 문자열입니다.  
  
 `stringExp`  
 필수 요소. 비교할 둘째 문자열입니다.  
  
 `locales`  
 선택 사항입니다. 하나 이상의 언어 또는 로캘 태그를 포함한 로캘 문자열의 배열입니다. 두 개 이상의 로캘 문자열을 포함하는 경우, 첫 번째 항목이 기본 설정 로캘이 되도록 우선 순위를 내림차순으로 나열합니다. 이 매개 변수를 생략하면 JavaScript 런타임 기본 로캘이 사용됩니다. 이 매개 변수를 따라야 [BCP 47](http://tools.ietf.org/html/rfc5646) 표준; 참조는 [Intl.Collator 개체](../../javascript/reference/intl-collator-object-javascript.md) 대 한 자세한 내용은 합니다.  
  
 `options`  
 선택 사항입니다. 비교 옵션을 지정하는 하나 이상의 속성이 포함된 개체입니다. 참조는 [Intl.Collator 개체](../../javascript/reference/intl-collator-object-javascript.md) 대 한 자세한 내용은 합니다.  
  
## <a name="remarks"></a>설명  
 비교 문자열에 대해 하나만 지정할 수 있습니다 `String` 개체 또는 문자열 리터럴입니다.  
  
 Internet Explorer 11에서 시작 `localeCompare` 사용 하 여는 `Intl.Collator` 개체 내부적으로 비교를 확인에 대 한 지원을 추가 하는 `locales` 및 `options` 매개 변수입니다. 이러한 매개 변수에 대 한 자세한 내용은 참조 [Intl.Collator](../../javascript/reference/intl-collator-object-javascript.md) 및 [Intl.Collator.compare](../../javascript/reference/compare-property-intl-collator.md)합니다.  
  
> [!IMPORTANT]
>  `locales` 및 `options` 매개 변수는 일부 문서 모드 및 브라우저 버전에서는 지원되지 않습니다. 자세한 내용은 요구 사항 섹션을 참조하세요.  
  
 `localeCompare` 로캘 구분 문자열 비교를 수행 하는 메서드 `stringVar` 및 `stringExp` 시스템 기본 로캘의 정렬 순서에 따라 결과 다음 중 하나를 반환 합니다.  
  
-   -없으면 1 `stringVar` 보다 앞에 정렬 `stringExp`합니다.  
  
-   + 이면 1 `stringVar` 문자열 뒤에 정렬 `stringExp`합니다.  
  
-   0 (영) 두 문자열은 동일 합니다.  
  
## <a name="example"></a>예제  
 다음 코드를 사용 하는 방법을 보여 줍니다 `localeCompare`합니다.  
  
```JavaScript  
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
  
## <a name="example"></a>예제  
 다음 코드를 사용 하는 방법을 보여 줍니다 `localeCompare` 독일어 (독일) 로캘을 사용 합니다.  
  
```JavaScript  
var str1 = "a";  
var str2 = "b";  
  
document.write(str1.localeCompare(str2, "de-DE"));  
  
// Output  
// - 1  
```  
  
## <a name="example"></a>예제  
 다음 예제에서는 사용 하는 방법을 보여 줍니다. `localeCompare` 독일어 (독일) 로캘로와 독일어 전화 번호부 정렬 순서를 지정 하는 로캘 관련 확장 합니다. 이 예제에서는 로캘 관련 차이점을 보여 줍니다.  
  
```JavaScript  
var arr = ["ä", "ad", "af", "a"];  
  
document.write(arr[0].localeCompare(arr[1], "de-DE-u-co-phonebk"));  // Returns 1  
document.write (arr[0].localeCompare(arr[2], "de-DE-u-co-phonebk"));  // Returns -1  
document.write (arr[0].localeCompare(arr[3], "de-DE-u-co-phonebk"));  // Returns 1  
  
document.write (arr[0].localeCompare(arr[1], "de-DE"));  // Returns -1  
document.write (arr[0].localeCompare(arr[2], "de-DE"));  // Returns -1  
document.write (arr[0].localeCompare(arr[3], "de-DE"));  // Returns 1  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
 `locales` 및 `options` 매개 변수:  
  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [toLocaleString 메서드(Object)](../../javascript/reference/tolocalestring-method-object-javascript.md)