---
title: "setUTCMilliseconds 메서드 (Date) (JavaScript) | Microsoft Docs"
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
- setUTCMilliseconds
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- milliseconds
- dates, UTC
- UTC times, setting
- setUTCMilliseconds method
ms.assetid: ed8e4486-d4b2-4b73-836b-dd1d3bb991a0
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 279d00b256b3b0763e2f15f549fdc6ee81c20254
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="setutcmilliseconds-method-date-javascript"></a>setUTCMilliseconds 메서드(Date)(JavaScript)
밀리초 값을 설정는 `Date` utc (협정 세계시)를 사용 하 여 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
dateObj.setUTCMilliseconds(numMilli)   
```  
  
## <a name="parameters"></a>매개 변수  
 `dateObj`  
 필수 요소. 모든 `Date` 개체입니다.  
  
 `numMilli`  
 필수 요소. 밀리초 값에 해당 하는 숫자 값입니다.  
  
## <a name="remarks"></a>설명  
 현지 시간을 사용 하는 시간 (밀리초)을 설정 하려면는 `setMilliseconds` 메서드.  
  
 경우의 값 `numMilli` 999 보다 크면 또는 음수 값은 초 (및 분, 시간, 등, 필요한 경우) 저장 된 수가 증가 한 시간입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `setUTCMilliseconds` 메서드를 사용하는 방법을 보여 줍니다.  
  
```JavaScript  
function SetUTCMSecDemo(nmsec){     
// Create Date object.  
   var d = new Date();             
// Set UTC milliseconds.  
   d.setUTCMilliseconds(nmsec);    
  
   var s = "Current setting is ";  
   s += d.toUTCString();  
   s += " and " + d.getUTCMilliseconds();  
   s += " milliseconds"  
   return(s);  
}  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **적용 대상**: [Date Object](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [getMilliseconds 메서드 (Date)](../../javascript/reference/getmilliseconds-method-date-javascript.md)   
 [getUTCMilliseconds 메서드 (Date)](../../javascript/reference/getutcmilliseconds-method-date-javascript.md)   
 [setMilliseconds 메서드(Date)](../../javascript/reference/setmilliseconds-method-date-javascript.md)