---
title: "getUTCSeconds 메서드 (Date) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: getUTCSeconds
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- UTC times, returning
- seconds method
- getUTCSeconds method
ms.assetid: 2d8ea7dc-79f8-4a9b-b2ab-732db2bcd5fd
caps.latest.revision: "11"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4f398145f8e31ed633bf3215de7d5a5ef669b7ef
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="getutcseconds-method-date-javascript"></a>getUTCSeconds 메서드(Date)(JavaScript)
초 가져옵니다는 `Date` utc (협정 세계시)를 사용 하 여 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
dateObj.getUTCSeconds()   
```  
  
#### <a name="parameters"></a>매개 변수  
 필요한 `dateObj` 참조는 `Date` 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 0에서 59 사이의 정수를 반환합니다. 시간은 1 초 미만 현재 분에 0이 반환 됩니다. 경우는 `Date` 시간을 지정 하지 않고 개체가 만들어진, 기본은 UTC 시간 (초) 값은 0입니다.  
  
## <a name="remarks"></a>설명  
 현지 시간을 초 수를 가져오려면 사용은 `getSeconds` 메서드.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `getUTCSeconds` 메서드를 사용하는 방법을 보여 줍니다.  
  
```JavaScript  
var date = new Date("1/1/2001");  
document.write(date. getUTCSeconds());  
  
// Output: 0  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **적용 대상**: [Date Object](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [getSeconds 메서드 (Date)](../../javascript/reference/getseconds-method-date-javascript.md)   
 [setSeconds 메서드 (Date)](../../javascript/reference/setseconds-method-date-javascript.md)   
 [setUTCSeconds 메서드(Date)](../../javascript/reference/setutcseconds-method-date-javascript.md)