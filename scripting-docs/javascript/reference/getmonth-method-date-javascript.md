---
title: "getMonth 메서드 (Date) (JavaScript) | Microsoft Docs"
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
- getMonth
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Date object
- dates, month value
- Month method
- GetMonth method
ms.assetid: c20dd8ba-1d78-42f1-8717-ed3dfd2362dd
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: eeffd7ffc7bee5fa63607e342a9a9dced7088d35
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="getmonth-method-date-javascript"></a>getMonth 메서드(Date)(JavaScript)
현지 시간을 사용 하 여 월을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
dateObj.getMonth()   
```  
  
#### <a name="parameters"></a>매개 변수  
 필요한 `dateObj` 참조는 `Date` 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 `getMonth` 메서드 0 (1 월) 및 11 (12 월) 사이의 정수를 반환 합니다. 에 대 한는 `Date` "1996 년 1 월 5,"를 사용 하 여 생성 `getMonth` 0을 반환 합니다.  
  
## <a name="remarks"></a>설명  
 Utc (협정 세계시)를 사용 하 여 월 값을 사용은 `getUTCMonth` 메서드.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `getMonth` 메서드를 사용하는 방법을 보여 줍니다.  
  
```JavaScript  
var date = new Date("1/1/2001");  
document.write(date.getMonth());  
  
// Output: 0  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **적용 대상**: [Date Object](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [getUTCMonth 메서드 (Date)](../../javascript/reference/getutcmonth-method-date-javascript.md)   
 [setMonth 메서드 (Date)](../../javascript/reference/setmonth-method-date-javascript.md)   
 [setUTCMonth 메서드(Date)](../../javascript/reference/setutcmonth-method-date-javascript.md)