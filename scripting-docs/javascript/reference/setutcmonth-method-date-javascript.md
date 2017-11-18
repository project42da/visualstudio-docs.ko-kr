---
title: "setUTCMonth 메서드 (Date) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: setUTCMonth
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- dates, UTC
- setUTCMonth method
- Month method
- UTC dates, setting
ms.assetid: cdac5f64-c4fd-44cc-ba3a-9a8dd3dd3fad
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 02cb69026b66e3f307a8709ab3f5b23d9518643a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="setutcmonth-method-date-javascript"></a>setUTCMonth 메서드(Date)(JavaScript)
월 값을 설정 합니다.는 `Date` utc (협정 세계시)를 사용 하 여 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
dateObj.setUTCMonth(numMonth[, dateVal])   
```  
  
## <a name="parameters"></a>매개 변수  
 `dateObj`  
 필수 요소. 모든 `Date` 개체입니다.  
  
 `numMonth`  
 필수 요소. 월에 해당 하는 숫자 값입니다. 1 월에 대 한 값은 0 이며 및 다른 달 값 연속적으로 수행 합니다.  
  
 `dateVal`  
 선택 사항입니다. 월의 일을 나타내는 숫자 값입니다. 제공 되지 않은 경우에 대 한 호출에서 값의 `getUTCDate` 메서드를 사용 합니다.  
  
## <a name="remarks"></a>설명  
 현지 시간을 사용 하 여 월 값을 설정 하려면는 `setMonth` 메서드.  
  
 하는 경우의 값 `numMonth` 11 보다 크면 (1 월은 0 임), 음수, 또는 적절 하 게 저장된 된 연도 증가 하거나 감소 합니다. 예를 들어, 저장 된 날짜가 "1 월 5, 1996 00:00:00.00" 및 **setUTCMonth(14)** 은 호출 날짜도 변경 된 "1997 년 3 월 5 일 00:00:00.00."  
  
 **setUTCFullYear** 연도, 월 및 월의 날짜를 설정 하려면 메서드를 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `setUTCMonth` 메서드를 사용하는 방법을 보여 줍니다.  
  
```JavaScript  
function SetUTCMonthDemo(newmonth){  
   var d, s;                       // Declare variables.  
   d = new Date();                 // Create Date object.  
   d.setUTCMonth(newmonth);        // Set UTC month.  
   s = "Current setting is ";  
   s += d.toUTCString();   
   return(s);                      // Return new setting.  
}  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **적용 대상**: [Date Object](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [getMonth 메서드 (Date)](../../javascript/reference/getmonth-method-date-javascript.md)   
 [getUTCMonth 메서드 (Date)](../../javascript/reference/getutcmonth-method-date-javascript.md)   
 [setMonth 메서드(Date)](../../javascript/reference/setmonth-method-date-javascript.md)