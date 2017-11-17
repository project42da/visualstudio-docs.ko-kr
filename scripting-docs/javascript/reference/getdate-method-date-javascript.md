---
title: "getDate 메서드 (Date) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: getDate
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Date object
- dates, returning day of the month
- getDate method
ms.assetid: 67e7f07c-dd46-4b42-82d6-e53e4bd33703
caps.latest.revision: "20"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: bfb3a8ad3ba433dc776f0831d1eac4787b8aea90
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="getdate-method-date-javascript"></a>getDate 메서드(Date)(JavaScript)
하루 중-월간, 현지 시간을 사용 하 여 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
dateObj.getDate()   
```  
  
#### <a name="parameters"></a>매개 변수  
 필요한 `dateObj` 참조는 `Date` 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 월을 나타내는 날짜-의-는-1에서 31 사이의 정수입니다.  
  
## <a name="remarks"></a>설명  
 하루 중-월간 유니버설 UTC (Coordinated Time)를 사용 하 여를 가져오려면는 `getUTCDate` 메서드.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `getDate` 메서드를 사용하는 방법을 보여 줍니다.  
  
```JavaScript  
var date = new Date("Jan 01, 2001");  
var str = "Today's date is: ";  
   str += (date.getMonth() + 1) + "/";  
   str += date.getDate() + "/";  
   str += date.getFullYear();  
document.write(str);  
  
// Output: Today's date is: 1/1/2001  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **적용 대상**: [Date Object](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [getUTCDate 메서드 (Date)](../../javascript/reference/getutcdate-method-date-javascript.md)   
 [setDate 메서드 (Date)](../../javascript/reference/setdate-method-date-javascript.md)   
 [setUTCDate 메서드(Date)](../../javascript/reference/setutcdate-method-date-javascript.md)