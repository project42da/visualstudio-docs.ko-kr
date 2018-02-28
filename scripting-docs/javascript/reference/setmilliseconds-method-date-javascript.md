---
title: "setMilliseconds 메서드 (Date) (JavaScript) | Microsoft Docs"
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
- setMilliseconds
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- milliseconds
- setMilliseconds method
ms.assetid: 6c398961-130e-4f60-802f-6c30e1ef4de4
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f0cd339e1352511312ef9a9abf9a7ff02955c986
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="setmilliseconds-method-date-javascript"></a>setMilliseconds 메서드(Date)(JavaScript)
밀리초 값을 설정는 `Date` 현지 시간을 사용 하 여 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
dateObj.  
setMilliseconds(  
numMilli  
)   
```  
  
## <a name="parameters"></a>매개 변수  
 `dateObj`  
 필수 요소. 모든 `Date` 개체입니다.  
  
 `numMilli`  
 필수 요소. 밀리초 값에 해당 하는 숫자 값입니다.  
  
## <a name="remarks"></a>설명  
 Utc (협정 세계시)를 사용 하 여 밀리초 값을 설정 하려면는 `setUTCMilliseconds` 메서드.  
  
 하는 경우의 값 `numMilli` 999 보다 큽니다 음수, 또는 초 (및 분, 시간 및 기타 필요한) 수가 저장된 증가 한 시간입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `setMilliseconds` 메서드를 사용하는 방법을 보여 줍니다.  
  
```JavaScript  
function SetMSecDemo(nmsec){  
   var d, s;                    // Declare variables.  
   d = new Date();              // Create Date object.  
   d.setMilliseconds(nmsec);    // Set milliseconds.  
   s = "Current setting is ";  
   s += d.toLocaleString();  
   s += " and " + d.getMilliseconds();  
   s += " milliseconds";  
   return(s);                   // Return new date setting.  
}  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **적용 대상**: [Date Object](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [getMilliseconds 메서드 (Date)](../../javascript/reference/getmilliseconds-method-date-javascript.md)   
 [getUTCMilliseconds 메서드 (Date)](../../javascript/reference/getutcmilliseconds-method-date-javascript.md)   
 [setUTCMilliseconds 메서드(Date)](../../javascript/reference/setutcmilliseconds-method-date-javascript.md)