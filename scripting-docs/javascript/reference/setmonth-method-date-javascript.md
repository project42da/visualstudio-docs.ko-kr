---
title: "setMonth 메서드 (Date) (JavaScript) | Microsoft Docs"
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
- setMonth
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Month method
- setMonth method
ms.assetid: 4f5be295-d536-46c0-b3a4-ad06457efe82
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0f2672abebd327af8b0da58d46ebc183b8159711
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="setmonth-method-date-javascript"></a>setMonth 메서드(Date)(JavaScript)
월 값을 설정 합니다.는 `Date` 현지 시간을 사용 하 여 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
dateObj. setMonth(numMonth[, dateVal])   
```  
  
## <a name="parameters"></a>매개 변수  
 `dateObj`  
 필수 요소. 모든 `Date` 개체입니다.  
  
 `numMonth`  
 필수 요소. 월에 해당 하는 숫자 값입니다. 1 월에 대 한 값은 0 이며 및 다른 달 값 연속적으로 수행 합니다.  
  
 `dateVal`  
 선택 사항입니다. 월의 일을 나타내는 숫자 값입니다. 이 값이 제공 되지 않은 경우에 대 한 호출에서 값의 `getDate` 메서드를 사용 합니다.  
  
## <a name="remarks"></a>설명  
 Utc (협정 세계시)를 사용 하 여 월 값을 설정 하려면는 `setUTCMonth` 메서드.  
  
 경우의 값 `numMonth` 11 보다 크거나 (1 월이 0 임) 또는 음수 값이 저장된 된 연도 변경 됩니다. 예를 들어, 저장 된 날짜가 "1 월 5, 1996" 및 **setMonth(14)** 은 호출 날짜 "1997 년 3 월 5 일입니다."로 변경 됩니다  
  
 **setFullYear** 연도, 월 및 월의 날짜를 설정 하려면 메서드를 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `setMonth` 메서드를 사용하는 방법을 보여 줍니다.  
  
```JavaScript  
date = new Date('1/1/1990');  
date.setMonth(14);  
document.write(date);  
  
// Output: Fri Mar 1 00:00:00 PST 1991  
// Note that the time zone corresponds to the time zone on the local computer.  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **적용 대상**: [Date Object](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [getMonth 메서드 (Date)](../../javascript/reference/getmonth-method-date-javascript.md)   
 [getUTCMonth 메서드 (Date)](../../javascript/reference/getutcmonth-method-date-javascript.md)   
 [setUTCMonth 메서드(Date)](../../javascript/reference/setutcmonth-method-date-javascript.md)