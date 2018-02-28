---
title: "Date.parse 함수 (JavaScript) | Microsoft Docs"
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
- parse
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- parse function [JavaScript]
- Date.parse function [JavaScript]
ms.assetid: ed737e50-6398-4462-8779-2af3c03f8325
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0a73fda66ef24df17a5213a182c04667fc4dfabf
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="dateparse-function-javascript"></a>Date.parse 함수(JavaScript)
날짜를 포함 하는 문자열을 구문 분석 하 고 해당 날짜 사이의 1970 년 1 월 1 일 자정 (밀리초)을 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
Date.parse(dateVal)   
```  
  
## <a name="remarks"></a>설명  
 필요한 `dateVal` 인수가 날짜 또는 ActiveX 또는 다른 개체에서 검색 한 VT_DATE 값이 포함 된 문자열입니다. 날짜에 대 한 정보 부분 문자열에 대 한는 `Date.parse` 함수 구문 분석할 수 있습니다. 참조 [날짜 및 시간 문자열](../../javascript/date-and-time-strings-javascript.md)합니다.  
  
 `Date.parse` 1970 년 1 월 1 일 자정에 지정 된 날짜 사이의 시간 (밀리초)의 수를 나타내는 정수 값을 반환 하는 함수 `dateVal`합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `Date.parse` 함수를 사용하는 방법을 보여 줍니다.  
  
```JavaScript  
var dateString = "November 1, 1997 10:15 AM";  
var mSec = Date.parse(dateString);  
document.write(mSec);  
// Output: 878404500000  
```  
  
## <a name="example"></a>예제  
 다음 예제에서는 제공 된 및 1/1/1970 날짜 사이의 차이 반환 합니다.  
  
```JavaScript  
var minMilli = 1000 * 60;  
var hrMilli = minMilli * 60;  
var dyMilli = hrMilli * 24;  
  
var testDate = new Date("June 1, 1990");  
var ms = Date.parse(testDate);  
var days = Math.round(ms / dyMilli);  
  
var dateStr = "";  
dateStr += "There are " + days + " days ";  
dateStr += "between 01/01/1970 and " + testDate;  
document.write(dateStr);  
  
// Output: There are 7456 days between 01/01/1970 and Fri Jun 1 00:00:00 PDT 1990  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [getDate 메서드(Date)](../../javascript/reference/getdate-method-date-javascript.md)