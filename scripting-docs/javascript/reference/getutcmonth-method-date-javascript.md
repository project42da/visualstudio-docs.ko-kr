---
title: "getUTCMonth 메서드 (Date) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: getUTCMonth
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- dates, UTC
- UTC dates, returning
- Month method
- getUTCMonth method
ms.assetid: eabae139-4da0-4e4a-a4cb-608e6375fc9e
caps.latest.revision: "11"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 07e7ecdc9a9ee8a49c12fc65e4b2ba1056bd377c
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="getutcmonth-method-date-javascript"></a>getUTCMonth 메서드(Date)(JavaScript)
월의 가져옵니다는 `Date` utc (협정 세계시)를 사용 하 여 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
dateObj.getUTCMonth()   
```  
  
#### <a name="parameters"></a>매개 변수  
 필요한 `dateObj` 참조는 `Date` 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 0 (1 월) 및 11 (12 월) 사이의 정수를 반환합니다.  
  
## <a name="remarks"></a>설명  
 현지 시간에서 월을 가져오려면는 **getMonth** 메서드.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `getUTCMonth` 메서드를 사용하는 방법을 보여 줍니다.  
  
```JavaScript  
var date = new Date("2/2/2002");  
document.write(date.getUTCMonth());  
  
// Output: 1  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **적용 대상**: [Date Object](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [getMonth 메서드 (Date)](../../javascript/reference/getmonth-method-date-javascript.md)   
 [setMonth 메서드 (Date)](../../javascript/reference/setmonth-method-date-javascript.md)   
 [setUTCMonth 메서드(Date)](../../javascript/reference/setutcmonth-method-date-javascript.md)