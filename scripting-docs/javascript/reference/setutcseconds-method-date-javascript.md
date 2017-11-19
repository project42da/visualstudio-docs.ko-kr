---
title: "setUTCSeconds 메서드 (Date) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: setUTCSeconds
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- dates, UTC
- setUTCSeconds method
- UTC times, setting
- seconds method
ms.assetid: e035e282-b39d-4d1d-8771-c17542fd6493
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f3df010cd84332d8957f1c08c41c4543dec36e4a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="setutcseconds-method-date-javascript"></a>setUTCSeconds 메서드(Date)(JavaScript)
초 값을 설정 합니다.는 `Date` utc (협정 세계시)를 사용 하 여 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
dateObj.setUTCSeconds(numSeconds[, numMilli])   
```  
  
## <a name="parameters"></a>매개 변수  
 `dateObj`  
 필수 요소. 모든 `Date` 개체입니다.  
  
 *numSeconds*  
 필수 요소. 초 값에 해당 하는 숫자 값입니다.  
  
 `numMilli`  
 선택 사항입니다. 밀리초 값에 해당 하는 숫자 값입니다.  
  
## <a name="remarks"></a>설명  
 모든 **설정** 해당에서 반환 된 값을 사용 하는 선택적 인수를 갖는 메서드 **가져오기** 메서드를 선택적 인수를 지정 하지 않으면 합니다. 예를 들어 경우는 `numMilli` 인수를 지정 하지 않으면 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 에서 반환 된 값을 사용 하 여는 `getUTCMilliseconds` 메서드.  
  
 초 현지 시간을 사용 하 여 값을 설정 하려면 사용 된 `setSeconds` 메서드.  
  
 인수 값의 범위 보다 크면 음수, 저장 된 다른 값도 수정 됩니다. 예를 들어, 저장 된 날짜가 "1 월 5, 1996 00:00:00.00" 및 **setSeconds(150)** 은 호출 날짜도 변경 된 "1 월 5, 1996 00:02:30.00."  
  
 **setUTCHours** 시간, 분, 초 및 밀리초를 설정 하려면 메서드를 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `setUTCSeconds` 메서드를 사용하는 방법을 보여 줍니다.  
  
```JavaScript  
function SetUTCSecondsDemo(nsec){  
// Create Date object.  
    var d = new Date();       
// Set UTC seconds.  
    d.setUTCSeconds(nsec);    
    var s = "Current setting is ";  
    s += d.toUTCString();  
// Return new setting.  
    return(s);                
}  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **적용 대상**: [Date Object](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [getSeconds 메서드 (Date)](../../javascript/reference/getseconds-method-date-javascript.md)   
 [getUTCSeconds 메서드 (Date)](../../javascript/reference/getutcseconds-method-date-javascript.md)   
 [setSeconds 메서드(Date)](../../javascript/reference/setseconds-method-date-javascript.md)