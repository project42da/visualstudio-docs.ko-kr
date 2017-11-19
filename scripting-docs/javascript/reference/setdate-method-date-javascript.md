---
title: "setDate 메서드 (Date) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: setDate
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- setDate method
- dates, setting
ms.assetid: a84b9b01-a6d0-489f-8a13-e7af9e9630b2
caps.latest.revision: "16"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8d74340287b3a7348419d302f79775eb610c6983
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="setdate-method-date-javascript"></a>setDate 메서드(Date)(JavaScript)
숫자 일 월 값을 설정 하는 `Date` 현지 시간을 사용 하 여 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
dateObj.setDate(numDate)   
```  
  
## <a name="parameters"></a>매개 변수  
 `dateObj`  
 필수 요소. 모든 `Date` 개체입니다.  
  
 `numDate`  
 필수 요소. 해당 월의 일에는 숫자 값입니다.  
  
## <a name="remarks"></a>설명  
 Utc (협정 세계시)를 사용 하 여 일 월 값을 설정 하려면는 `setUTCDate` 메서드.  
  
 하는 경우의 값 `numDate` 이상 월 및/또는 연도를 통해 날짜 롤업 월의 일 수보다 큽니다. 예를 들어, 저장 된 날짜가, 1996 년 1 월 5 이면 및 `setDate(32)` 라고, 1996 년 2 월 1을 변경 하는 날짜입니다. 경우 `numDate` 은 음수 값으로는 이전 월 및 연도 날짜 롤백합니다. 예를 들어, 저장 된 날짜가, 1996 년 1 월 5 이면 및 `setDate(-32)` 라고, 1995 년 11 월 29 일에 날짜가 변경 합니다.  
  
 [setFullYear 메서드 (Date)](../../javascript/reference/setfullyear-method-date-javascript.md) 는 연도, 월 및 월의 날짜를 설정 하는 데 사용할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `setDate` 메서드를 사용하는 방법을 보여 줍니다.  
  
```JavaScript  
var date = new Date("12/15/1990");  
date.setDate(30);  
document.write(date);  
  
// Output (for the PST time zone): Sun Dec 30 00:00:00 PST 1990  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **적용 대상**: [Date Object](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [getDate 메서드 (Date)](../../javascript/reference/getdate-method-date-javascript.md)   
 [setFullYear 메서드 (Date)](../../javascript/reference/setfullyear-method-date-javascript.md)   
 [setMonth 메서드 (Date)](../../javascript/reference/setmonth-method-date-javascript.md)   
 [setUTCDate 메서드(Date)](../../javascript/reference/setutcdate-method-date-javascript.md)