---
title: "setFullYear 메서드 (Date) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: setFullYear
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Year method
- setFullYear method
- dates, setting
ms.assetid: 635e4f5a-0210-4c01-8152-b0da4146f6ff
caps.latest.revision: "16"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1e5e20a8486d1aefeab9b244c5f1e9d1b1e60c3f
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="setfullyear-method-date-javascript"></a>setFullYear 메서드(Date)(JavaScript)
설정의 연도 `Date` 현지 시간을 사용 하 여 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
dateObj.setFullYear(numYear[, numMonth[, numDate]])   
```  
  
## <a name="parameters"></a>매개 변수  
 `dateObj`  
 필수 요소. 모든 `Date` 개체입니다.  
  
 `numYear`  
 필수 요소. 연도 대 한 숫자 값입니다.  
  
 `numMonth`  
 선택 사항입니다. 월 (1 월 11 년 12 월에 대 한 0)에 대 한 0부터 시작 숫자 값입니다. 지정 하지 않은 경우 `numDate` 지정 됩니다.  
  
 `numDate`  
 선택 사항입니다. 월의 일에 대 한 숫자 값입니다.  
  
## <a name="remarks"></a>설명  
 모든 **설정** 해당에서 반환 된 값을 사용 하는 선택적 인수를 갖는 메서드 **가져오기** 메서드를 선택적 인수를 지정 하지 않습니다. 예를 들어 경우는 `numMonth` 인수는 선택 사항 이지만 지정 되지 않은 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 에서 반환 된 값을 사용 하 여는 **getMonth** 메서드.  
  
 또한 인수 값 달력 범위 보다 크거나 같으면이 음수, 앞으로 또는 뒤로 적절 하 게 날짜 롤업 합니다.  
  
 Utc (협정 세계시)를 사용 하 여 연도 설정 하려면는 `setUTCFullYear` 메서드.  
  
 Date 개체에서 지 원하는 연도 범위는 1970 전후 285616 년 약 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `setFullYear` 메서드:  
  
```JavaScript  
var date1 = new Date("1/1/2001");  
date1.setFullYear(2007);  
  
var date2 = new Date("1/1/2001");  
date2.setFullYear(2008, 10, 3);   
  
document.write (date1.toLocaleString());  
document.write ("<br />");  
document.write (date2.toLocaleString());  
  
// Output:  
// Monday, January 01, 2007 12:00:00 AM  
// Monday, November 03, 2008 12:00:00 AM  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **적용 대상**: [Date Object](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [getFullYear 메서드 (Date)](../../javascript/reference/getfullyear-method-date-javascript.md)   
 [getUTCFullYear 메서드 (Date)](../../javascript/reference/getutcfullyear-method-date-javascript.md)   
 [setUTCFullYear 메서드(Date)](../../javascript/reference/setutcfullyear-method-date-javascript.md)