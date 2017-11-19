---
title: "getUTCDay 메서드 (Date) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: getUTCDay
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Date object
- dates, UTC
- UTC dates, returning
- getUTCDay method
ms.assetid: 2fceb5b0-6f77-4919-82c3-0877fd55bacb
caps.latest.revision: "14"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6ee9953a7abf548ef15cc124e09b914af360ca23
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="getutcday-method-date-javascript"></a>getUTCDay 메서드(Date)(JavaScript)
Utc (협정 세계시)를 사용 하 여 주 중 일 수를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
dateObj.getUTCDay()   
```  
  
#### <a name="parameters"></a>매개 변수  
 필요한 `dateObj` 참조는 `Date` 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 0 (일요일) 및 해당 주의 일을 나타내는 6 (토요일) 사이의 정수를 반환 합니다.  
  
## <a name="remarks"></a>설명  
 현지 시간을 사용 하 여 요일을 가져오려면는 `getDate` 메서드.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `getUTCDay` 메서드를 사용하는 방법을 보여 줍니다.  
  
```JavaScript  
var date = new Date("2/6/2001");  
var day = date.getUTCDay();  
document.write(day);  
  
// Output: 2  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **적용 대상**: [Date Object](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [getDay 메서드(Date)](../../javascript/reference/getday-method-date-javascript.md)