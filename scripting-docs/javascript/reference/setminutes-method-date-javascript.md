---
title: "setMinutes 메서드 (Date) (JavaScript) | Microsoft Docs"
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
- setMinutes
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- minutes
- setMinutes method
ms.assetid: 34c959cd-cd29-4cee-8e04-9061cf6d42f3
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1ce40cb3ebf769cdd8f668e246e272833780434d
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="setminutes-method-date-javascript"></a>setMinutes 메서드(Date)(JavaScript)
분 값을 설정는 **날짜** 현지 시간을 사용 하 여 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
dateObj.setMinutes(numMinutes[, numSeconds[, numMilli]])   
```  
  
## <a name="parameters"></a>매개 변수  
 `dateObj`  
 필수 요소. 모든 `Date` 개체입니다.  
  
 `numMinutes`  
 필수 요소. 분 값에 해당 하는 숫자 값입니다. 다음 인수 중 하나를 사용 하는 경우에 제공 되어야 합니다.  
  
 *numSeconds*  
 선택적 요소. 초 값에 해당 하는 숫자 값입니다. 경우에 제공 해야 합니다는 `numMilli` 인수를 사용 합니다.  
  
 `numMilli`  
 선택적 요소. 밀리초 값에 해당 하는 숫자 값입니다.  
  
## <a name="remarks"></a>설명  
 모든 **설정** 해당에서 반환 된 값을 사용 하는 선택적 인수를 갖는 메서드 **가져오기** 메서드를 선택적 인수를 지정 하지 않으면 합니다. 예를 들어 경우는 *numSeconds* 지정 되지 않은 인수 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 에서 반환 된 값을 사용 하 여는 `getSeconds` 메서드.  
  
 Utc (협정 세계시)를 사용 하 여 분 값을 설정 하려면는 `setUTCMinutes` 메서드.  
  
 인수 값의 범위 보다 크면 음수, 저장 된 다른 값도 수정 됩니다. 예를 들어 저장 된 날짜가 ", 1996 년 1 월 5 00시: 00" 및 **setMinutes(90)** 은 호출 날짜로 변경 됩니다 "1996 년 1 월 5, 01시 30분: 00입니다." 음수는 동작이 서로 유사 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `setMinutes` 메서드를 사용하는 방법을 보여 줍니다.  
  
```JavaScript  
function SetMinutesDemo(nmin, nsec){  
   var d, s;                     // Declare variables.  
   d = new Date();               // Create Date object.  
   d.setMinutes(nmin, nsec);     // Set minutes.  
   s = "Current setting is " + d.toLocaleString()   
   return(s);                    // Return new setting.  
}  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **적용 대상**: [Date Object](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [getMinutes 메서드 (Date)](../../javascript/reference/getminutes-method-date-javascript.md)   
 [getUTCMinutes 메서드 (Date)](../../javascript/reference/getutcminutes-method-date-javascript.md)   
 [setUTCMinutes 메서드(Date)](../../javascript/reference/setutcminutes-method-date-javascript.md)