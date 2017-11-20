---
title: toLocaleString (Date) | Microsoft Docs
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
ms.assetid: 3472d7bd-b255-4804-8407-c4a1e419a5a3
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b6dc7b1f38f7e57d1c10f7197bb73b13b3545380
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="tolocalestring-date"></a>toLocaleString(Date)
현재 또는 지정 된 로캘을 사용 하 여 문자열로 날짜를 변환 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
dateObj.toLocaleString([locales][, options])   
```  
  
#### <a name="parameters"></a>매개 변수  
 `dateObj`  
 필수 요소. `Date` 변환할 개체입니다.  
  
 `locales`  
 선택적 요소. 하나 이상의 언어 또는 로캘 태그를 포함한 로캘 문자열의 배열입니다. 두 개 이상의 로캘 문자열을 포함하는 경우, 첫 번째 항목이 기본 설정 로캘이 되도록 우선 순위를 내림차순으로 나열합니다. 이 매개 변수를 생략하면 JavaScript 런타임 기본 로캘이 사용됩니다.  
  
 `options`  
 선택적 요소. 비교 옵션을 지정하는 하나 이상의 속성이 포함된 개체입니다.  
  
## <a name="remarks"></a>설명  
 Internet Explorer 11부터 `toLocaleString` 사용 하 여 `Intl.DateTimeFormat` 확인 비교에 대 한 지원을 추가 하는 내부적으로 `locales` 및 `options` 매개 변수입니다. 이러한 매개 변수에 대 한 자세한 내용은 참조 [Intl.DateTimeFormat](../../javascript/reference/intl-datetimeformat-object-javascript.md)합니다.  
  
> [!IMPORTANT]
>  `locales` 및 `options` 매개 변수는 일부 문서 모드 및 브라우저 버전에서는 지원되지 않습니다. 자세한 내용은 요구 사항 섹션을 참조하세요.  
  
 `toLocaleString`을 Internet Explorer 10 표준 문서 모드, 이전 문서 모드, 쿼크 모드에서 사용하는 경우  
  
-   반환 된 `String` 현재 로캘의 기본 형식으로 작성 된 날짜를 포함 하는 개체입니다.  
  
-   1999 서 기 1601 사이의 날짜, 사용자의 제어판의 국가별 설정 형식이 사용 됩니다.  
  
> [!NOTE]
>  생략 하면는 `locales` 매개 변수를 사용 하 여 `toLocaleString` ; 사용자에 게 결과 표시할에 사용 하 여 스크립트 내에서 값을 계산 하는 컴퓨터 별로 반환 된 결과 때문에 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `toLocaleString` 메서드를 사용하는 방법을 보여 줍니다.  
  
```JavaScript  
function toLocaleStrDemo(){     
   var d, s;                      //Declare variables.  
   d = new Date();                //Create Date object.  
   s = "Current setting is ";  
   s += d.toLocaleString();       //Convert to current locale.  
   return(s);                     //Return converted date  
}  
```  
  
## <a name="example"></a>예제  
 다음 예제에서는 지정된 로캘 및 비교 옵션과 함께 `toLocaleString` 메서드를 사용하는 방법을 보여 줍니다.  
  
```JavaScript  
var date = new Date(Date.UTC(2013, 1, 1, 14, 0, 0));  
var options = { weekday: "long", year: "numeric", month: "short",  
    day: "numeric" };  
  
// Using I18N toLocaleString  
document.write(date.toLocaleString("en-US"));  
document.write(date.toLocaleString("ja-JP"));  
document.write(date.toLocaleString("ar-SA", options));  
document.write(date.toLocaleString("hi-IN", options));  
  
// Output:  
// ‎2‎/‎1‎/‎2013‎ ‎6‎:‎00‎:‎00‎ ‎AM  
// ‎2013‎年‎2‎月‎1‎日‎ ‎6‎:‎00‎:‎00  
// ‏الجمعة‏, ‏٢٠‏ ‏ربيع الأول‏, ‏١٤٣٤  
// ‎शुक्रवार‎, ‎01‎ ‎फरवरी‎ ‎2013  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 `locales` 및 `options` 매개 변수:  
  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [toLocaleDateString 메서드(Date)](../../javascript/reference/tolocaledatestring-method-date-javascript.md)