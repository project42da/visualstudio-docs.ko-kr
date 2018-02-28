---
title: "setUTCMinutes 메서드 (Date) (JavaScript) | Microsoft Docs"
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
- setUTCMinutes
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- minutes
- dates, UTC
- UTC times, setting
- setUTCMinutes method
ms.assetid: 2415e788-6d28-46dd-a103-0931a1fd1446
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 37df1bcefa358f2c9076a3da877bd642d19178b0
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="setutcminutes-method-date-javascript"></a>setUTCMinutes 메서드(Date)(JavaScript)
분 값을 설정는 `Date` utc (협정 세계시)를 사용 하 여 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
dateObj.setUTCMinutes(numMinutes[, numSeconds[, numMilli]])   
```  
  
## <a name="parameters"></a>매개 변수  
 `dateObj`  
 필수 요소. 모든 `Date` 개체입니다.  
  
 `numMinutes`  
 필수 요소. 분 값에 해당 하는 숫자 값입니다. 다음 인수 중 하나를 사용 하는 경우에 제공 되어야 합니다.  
  
 *numSeconds*  
 선택 사항입니다. 초 값에 해당 하는 숫자 값입니다. 경우에 제공 해야 `numMilli` 사용 됩니다.  
  
 `numMilli`  
 선택 사항입니다. 밀리초 값에 해당 하는 숫자 값입니다.  
  
## <a name="remarks"></a>설명  
 모든 **설정** 해당에서 반환 된 값을 사용 하는 선택적 인수를 갖는 메서드 **가져오기** 메서드를 선택적 인수를 지정 하지 않으면 합니다. 예를 들어 경우는 *numSeconds* 인수를 지정 하지 않으면 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 에서 반환 된 값을 사용 하 여는 `getUTCSeconds` 메서드.  
  
 현지 시간을 사용 하 여 분 값을 수정 하려면 사용 하 여는 `setMinutes` 메서드.  
  
 인수 값의 범위 보다 클 음수인 경우 저장 된 다른 값도 수정 됩니다. 예를 들어, 저장 된 날짜가 "1 월 5, 1996 00:00:00.00" 및 **setUTCMinutes(70)** 은 호출 날짜도 변경 된 "1 월 5, 1996 01:10:00.00."  
  
 **setUTCHours** 시간, 분, 초 및 밀리초를 설정 하려면 메서드를 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `setUTCMinutes` 메서드:  
  
```JavaScript  
function SetUTCMinutesDemo(nmin, nsec){  
   var d, s;                    // Declare variables.  
   d = new Date();              // Create Date object.  
   d.setUTCMinutes(nmin,nsec);  // Set UTC minutes.  
   s = "Current setting is " + d.toUTCString()   
   return(s);                   // Return new setting.  
}  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **적용 대상**: [Date Object](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [getMinutes 메서드 (Date)](../../javascript/reference/getminutes-method-date-javascript.md)   
 [getUTCMinutes 메서드 (Date)](../../javascript/reference/getutcminutes-method-date-javascript.md)   
 [setMinutes 메서드(Date)](../../javascript/reference/setminutes-method-date-javascript.md)