---
title: "getUTCDate 메서드 (Date) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: getUTCDate
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Date object
- dates, UTC
- UTC dates, returning
- getUTCDate method
ms.assetid: 9e4c763f-c94c-44c9-9684-cb632d75b62e
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e4c38244e989027139329ae6aab762fd9fbabb3a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="getutcdate-method-date-javascript"></a>getUTCDate 메서드(Date)(JavaScript)
하루 중-월간, utc (협정 세계시)를 사용 하 여 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
dateObj.getUTCDate()   
```  
  
#### <a name="parameters"></a>매개 변수  
 필요한 `dateObj` 참조는 `Date` 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 1에서 월을 나타내는 날짜-의-the-31 사이의 정수를 반환 합니다.  
  
## <a name="remarks"></a>설명  
 현지 시간을 사용 하 여 월의 일을 사용은 `getDate` 메서드.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `getUTCDate` 메서드를 사용하는 방법을 보여 줍니다.  
  
```JavaScript  
var date = new Date("1/23/2001");  
document.write(date.getUTCDate());  
  
// Output: 23  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **적용 대상**: [Date Object](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [getDate 메서드 (Date)](../../javascript/reference/getdate-method-date-javascript.md)   
 [setDate 메서드 (Date)](../../javascript/reference/setdate-method-date-javascript.md)   
 [setUTCDate 메서드(Date)](../../javascript/reference/setutcdate-method-date-javascript.md)