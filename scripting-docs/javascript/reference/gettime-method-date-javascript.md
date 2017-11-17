---
title: "getTime 메서드 (Date) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: getTime
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- GetTime method
- time method
ms.assetid: f0da1d4e-337c-497d-9205-093defbc6d3d
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a31e542445e89a0e2f3364d36ae44f8d2d4cf9bb
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="gettime-method-date-javascript"></a>getTime 메서드(Date)(JavaScript)
밀리초에서의 시간 값을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
dateObj.getTime()   
```  
  
#### <a name="parameters"></a>매개 변수  
 필요한 `dateObj` 참조는 `Date` 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 1970 년 1 월 1 일 자정와의 시간 값 사이의 밀리초 수를 반환 합니다.는 `Date` 개체입니다. 날짜 범위는 어느 쪽이 1970 년 1 월 1 일 자정 약 285616 년입니다. 음수는 1970 이전의 날짜를 나타냅니다.  
  
## <a name="remarks"></a>설명  
 여러 가지 날짜 및 시간 계산을 수행 하는 경우 일, 시간 또는 분의 시간 (밀리초)의 수와 동일한 변수를 정의 하는 것이 좋습니다. 예:  
  
```JavaScript  
var minute = 1000 * 60;  
var hour = minute * 60;  
var day = hour * 24;  
```  
  
 참조 [시간과 날짜를 계산 (JavaScript)](../../javascript/calculating-dates-and-times-javascript.md) 사용 하는 방법에 대 한 자세한 내용은 `getTime` 메서드.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `getTime` 메서드를 사용하는 방법을 보여 줍니다.  
  
```JavaScript  
var minute = 1000 * 60;  
var hour = minute * 60;  
var day = hour * 24;  
  
date = new Date("1/1/2001");  
var time = date.getTime();  
  
document.write(Math.round(time / day) + " days from 1/1/1970 to 1/1/2001");  
  
// Output: 11323 days from 1/1/1970 to 1/1/2001  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **적용 대상**: [Date Object](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [setTime 메서드(Date)](../../javascript/reference/settime-method-date-javascript.md)