---
title: "setUTCDate 메서드 (Date) (JavaScript) | Microsoft Docs"
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
- setUTCDate
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- dates, UTC
- dates, setting
- UTC dates, setting
- setUTCDate method
ms.assetid: e6c3b876-70fe-4103-b197-6c84c078ce10
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5631a36c8b1c4f1ee50dcadb39f0f21ae5aa28e3
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="setutcdate-method-date-javascript"></a>setUTCDate 메서드(Date)(JavaScript)
날짜의 월을 설정 하는 `Date` utc (협정 세계시)를 사용 하 여 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
dateObj.setUTCDate(numDate)   
```  
  
## <a name="parameters"></a>매개 변수  
 `dateObj`  
 필수 요소. 모든 `Date` 개체입니다.  
  
 *numDate*  
 필수 요소. 해당 월의 일에는 숫자 값입니다.  
  
## <a name="remarks"></a>설명  
 현지 시간을 사용 하 여 월의 일을 설정 하려면는 `setDate` 메서드.  
  
 경우의 값 *numDate* 에 저장 된 달의 일 수보다 큽니다는 **날짜** 개체 또는 음수 값은 날짜 날짜가 설정 되 *numDate* 빼기 저장 된 달의 일 수입니다. 예를 들어, 저장 된 날짜가 1996 년 1 월 5 및 **setUTCDate(32)** 라고, 1996 년 2 월 1을 변경 하는 날짜입니다. 음수는 동작이 서로 유사 합니다.  
  
 **setUTCFullYear** 연도, 월 및 월의 날짜를 설정 하려면 메서드를 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `setUTCDate` 메서드를 사용하는 방법을 보여 줍니다.  
  
```JavaScript  
function SetUTCDateDemo(newdayofmonth){  
   var d = new Date();           // Create Date object.  
   d.setUTCDate(newdayofmonth);  // Set UTC day of month.  
   var s = "Current setting is ";  
   s += d.toUTCString();   
   return(s);                    // Return new setting.  
}  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **적용 대상**: [Date Object](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [getDate 메서드 (Date)](../../javascript/reference/getdate-method-date-javascript.md)   
 [getUTCDate 메서드 (Date)](../../javascript/reference/getutcdate-method-date-javascript.md)   
 [setDate 메서드(Date)](../../javascript/reference/setdate-method-date-javascript.md)