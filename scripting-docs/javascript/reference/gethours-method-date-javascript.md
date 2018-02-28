---
title: "getHours 메서드 (Date) (JavaScript) | Microsoft Docs"
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
- getHours
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Date object
- GetHours method
- Hours method
ms.assetid: c3936496-a213-4d15-b308-d53926ed310c
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 87170f96ee6ae6b4a825436717a94749cc336ee0
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="gethours-method-date-javascript"></a>getHours메서드(Date)(JavaScript)
현지 시간을 사용 하는 날짜의 시간을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
dateObj.getHours()   
```  
  
#### <a name="parameters"></a>매개 변수  
 필요한 `dateObj` 참조는 `Date` 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 자정 이후의 시간 수를 나타내는 0에서 23 사이의 정수. 시간은 오전 1시: 00 이전 하는 경우 0이 반환 됩니다. 경우는 `Date` 시간을 지정 하지 않고 개체가 만들어진, 기본적으로 1 시간은 0입니다.  
  
## <a name="remarks"></a>설명  
 Utc (협정 세계시)를 사용 하 여 시간 값을 사용은 `getUTCHours` 메서드.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `getHours` 메서드를 사용하는 방법을 보여 줍니다.  
  
```JavaScript  
var date = new Date("1/1/2001");  
document.write(date.getHours());  
document.write("<br/>");  
  
date.setTime(50000000);  
document.write(date.getHours());  
  
// Output:  
// 0   
// 5  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **적용 대상**: [Date Object](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [getUTCHours 메서드 (Date)](../../javascript/reference/getutchours-method-date-javascript.md)   
 [setHours 메서드 (Date)](../../javascript/reference/sethours-method-date-javascript.md)   
 [setUTCHours 메서드(Date)](../../javascript/reference/setutchours-method-date-javascript.md)