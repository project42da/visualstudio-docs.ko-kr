---
title: "setTime 메서드 (Date) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: setTime
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- SetTime method
- time method
ms.assetid: 86584748-7219-495b-bf56-e27f5782778c
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e66b1fbf5d668330eb727e8bfc50ee9d11a28be3
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="settime-method-date-javascript"></a>setTime 메서드(Date)(JavaScript)
날짜 및 시간 값을 설정의 `Date` 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
dateObj.setTime(milliseconds)   
```  
  
## <a name="parameters"></a>매개 변수  
 `dateObj`  
 필수 요소. 모든 `Date` 개체입니다.  
  
 *시간 (밀리초)*  
 필수 요소. GMT 1970 년 1 월 1 일 자정 이후 경과 된 시간 (밀리초)의 수를 나타내는 숫자 값입니다.  
  
## <a name="remarks"></a>설명  
 경우 *밀리초* 는 1970 이전의 날짜 나타냅니다 음수입니다. 사용 가능한 날짜 범위는 1970 년 약 285616 년 됩니다.  
  
 날짜와 시간으로 설정 된 `setTime` 메서드는 표준 시간대와 무관 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `setTime` 메서드를 사용하는 방법을 보여 줍니다.  
  
```JavaScript  
function SetTimeTest(newtime){  
   var d, s;                  //Declare variables.  
   d = new Date();            //Create Date object.  
   d.setTime(newtime);        //Set time.  
   s = "Current setting is ";  
   s += d.toUTCString();  
   return(s);                 //Return new setting.  
}  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **적용 대상**: [Date Object](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [getTime 메서드(Date)](../../javascript/reference/gettime-method-date-javascript.md)