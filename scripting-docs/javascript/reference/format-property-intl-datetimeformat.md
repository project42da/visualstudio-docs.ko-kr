---
title: "format 속성 (Intl.DateTimeFormat) | Microsoft Docs"
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
ms.assetid: 487930fe-a948-446f-902d-06bb0d7685d5
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2e94fcd797a63944d0162dceadf773cf9b15f943
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="format-property-intldatetimeformat"></a>format 속성(Intl.DateTimeFormat)
지정 된 날짜/시간 포맷터 설정을 사용 하 여 로캘별 날짜 형식을 지정 하는 함수를 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
dateTimeFormatObj.format  
```  
  
#### <a name="parameters"></a>매개 변수  
 `dateTimeFormatObj`  
 필수 요소. 이름에서 `DateTimeFormat` 포맷터로 사용할 개체입니다.  
  
## <a name="remarks"></a>설명  
 함수에서 반환 되는 `format` 는 하나의 인수를 사용 하는 속성 `date`에 지정 된 옵션을 사용 하 여 지역화 된 날짜를 나타내는 문자열을 반환 하 고는 `DateTimeFormat` 개체입니다. `date` 반환 함수의 매개 변수는 숫자, 날짜 문자열 이어야 합니다. 또는 `Date` 개체입니다. 경우 `date` 를 지정 하지 않은 함수를 사용 하 여 [Date.now](../../javascript/reference/date-now-function-javascript.md) 기본 입력된 값으로.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `DateTimeFormat` 개체를 다시 포맷 하 고 독일어로 날짜 "2007 년 12 월 1 일" 필드를 지역화 합니다.  
  
```JavaScript  
var dtFormat = new Intl.DateTimeFormat(["de"], {  
    year: "numeric",  
    month: "long",  
    day: "2-digit",  
    hour: "numeric"  
});  
  
if (console && console.log) {  
    console.log(dtFormat.format(new Date("Dec 1, 2007")));  
    // Returns 01. Dezember 2007 00:00  
}  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [Intl.DateTimeFormat 개체](../../javascript/reference/intl-datetimeformat-object-javascript.md)