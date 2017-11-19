---
title: "setUTCHours 메서드 (Date) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: setUTCHours
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- dates, UTC
- UTC times, setting
- setUTCHours method
ms.assetid: 257e36fd-fb06-4a4d-8634-d66a020a1511
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 9fe83735028f86d38ef270beac6c44dfa4caae7f
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="setutchours-method-date-javascript"></a>setUTCHours 메서드(Date)(JavaScript)
시간 값을 설정는 `Date` utc (협정 세계시)를 사용 하 여 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
dateObj.setUTCHours(numHours[, numMin[, numSec[, numMilli]]])   
```  
  
## <a name="parameters"></a>매개 변수  
 `dateObj`  
 필수 요소. 모든 `Date` 개체입니다.  
  
 `numHours`  
 필수 요소. 시간 값에 숫자 값입니다.  
  
 `numMin`  
 선택 사항입니다. 분 값에 해당 하는 숫자 값입니다. 경우 꼭 필요한 `numSec` 또는 `numMilli` 사용 됩니다.  
  
 `numSec`  
 선택 사항입니다. 초 값에 해당 하는 숫자 값입니다. 경우에 제공 해야 `numMilli` 인수를 사용 합니다.  
  
 `numMilli`  
 선택 사항입니다. 밀리초 값에 해당 하는 숫자 값입니다.  
  
## <a name="remarks"></a>설명  
 모든 **설정** 해당에서 반환 된 값을 사용 하는 선택적 인수를 갖는 메서드 **가져오기** 메서드를 선택적 인수를 지정 하지 않으면 합니다. 예를 들어 경우는 `numMin` 인수를 지정 하지 않으면 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 에서 반환 된 값을 사용 하 여는 `getUTCMinutes` 메서드.  
  
 현지 시간을 사용 하 여 시간 값을 설정 하려면는 `setHours` 메서드.  
  
 인수 값의 범위 보다 클 음수인 경우 저장 된 다른 값도 수정 됩니다. 예를 들어, 저장 된 날짜가 "1 월 5, 1996 00:00:00.00" 및 **setUTCHours(30)** 은 호출 날짜도 변경 된 "1996 년 1 월 월 6 일, 06:00:00.00."  
  
## <a name="example"></a>예제  
 다음 예제에서는 `setUTCHours` 메서드를 사용하는 방법을 보여 줍니다.  
  
```JavaScript  
function SetUTCHoursDemo(nhr, nmin, nsec){     
   var d, s;                        // Declare variables.  
   d = new Date();                  // Create Date object.  
   d.setUTCHours(nhr, nmin, nsec);  // Set UTC hours, minutes, seconds.  
   s = "Current setting is " + d.toUTCString()   
   return(s);                       // Return new setting.  
}  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **적용 대상**: [Date Object](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [getHours 메서드 (Date)](../../javascript/reference/gethours-method-date-javascript.md)   
 [getUTCHours 메서드 (Date)](../../javascript/reference/getutchours-method-date-javascript.md)   
 [setHours 메서드(Date)](../../javascript/reference/sethours-method-date-javascript.md)