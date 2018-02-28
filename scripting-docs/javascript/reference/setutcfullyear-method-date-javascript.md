---
title: "setUTCFullYear 메서드 (Date) (JavaScript) | Microsoft Docs"
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
- setUTCFullYear
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- dates, UTC
- setUTCFullYear method
- UTC dates, setting
ms.assetid: e6c51b49-0149-4f9a-aa74-c73c0306f98e
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2dda8b75dd8bc8dac87ea383546f392b064c1d63
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="setutcfullyear-method-date-javascript"></a>setUTCFullYear 메서드(Date)(JavaScript)
연도 값을 설정 합니다.는 `Date` utc (협정 세계시)를 사용 하 여 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
dateObj.setUTCFullYear(numYear[, numMonth[, numDate]])   
```  
  
## <a name="parameters"></a>매개 변수  
 `dateObj`  
 필수 요소. 모든 `Date` 개체입니다.  
  
 `numYear`  
 필수 요소. 연도 숫자 값입니다.  
  
 `numMonth`  
 선택 사항입니다. 월에 해당 하는 숫자 값입니다. 1 월에 대 한 값은 0 이며 및 다른 달 값 연속적으로 수행 합니다. 경우에 제공 해야 *numDate* 제공 됩니다.  
  
 *numDate*  
 선택 사항입니다. 해당 월의 일에는 숫자 값입니다.  
  
## <a name="remarks"></a>설명  
 모든 **설정** 해당에서 반환 된 값을 사용 하는 선택적 인수를 갖는 메서드 **가져오기** 메서드를 선택적 인수를 지정 하지 않으면 합니다. 예를 들어 경우는 `numMonth` 인수를 지정 하지 않으면 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 에서 반환 된 값을 사용 하 여는 `getUTCMonth` 메서드.  
  
 또한 인수 값이 크면 하는 범위 또는 음수인 숫자, 기타 저장 된 값도 수정 됩니다.  
  
 현지 시간을 사용 하 여 연도 설정 하려면는 `setFullYear` 메서드.  
  
 지 원하는 연도 범위는 `Date` 개체는 어느 쪽이 1970 약 285616 년입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `setUTCFullYear` 메서드를 사용하는 방법을 보여 줍니다.  
  
```JavaScript  
var dtFirst = new Date();  
dtFirst.setUTCFullYear(2007);  
  
var dtSecond = new Date();  
// 10 is the value for November.   
dtSecond.setUTCFullYear(2008, 10, 3);   
  
document.write (dtFirst.toUTCString());  
document.write ("<br />");  
document.write (dtSecond.toUTCString());  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **적용 대상**: [Date Object](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [getFullYear 메서드 (Date)](../../javascript/reference/getfullyear-method-date-javascript.md)   
 [getUTCFullYear 메서드 (Date)](../../javascript/reference/getutcfullyear-method-date-javascript.md)   
 [setFullYear 메서드(Date)](../../javascript/reference/setfullyear-method-date-javascript.md)