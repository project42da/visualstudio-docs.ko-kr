---
title: "getMilliseconds 메서드 (Date) (JavaScript) | Microsoft Docs"
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
- getMilliseconds
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- milliseconds
- getMilliseconds method
ms.assetid: 1b512146-1e8a-44a4-89da-6cc5338d15cb
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 33e5fc54dffbe06e47f0978e6cef94b1f650c90f
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="getmilliseconds-method-date-javascript"></a>getMilliseconds 메서드(Date)(JavaScript)
현지 시간을 사용 하 여 날짜의 시간 (밀리초)을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
dateObj.getMilliseconds()   
```  
  
#### <a name="parameters"></a>매개 변수  
 필요한 `dateObj` 참조는 `Date` 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 날짜의 시간 (밀리초)을 반환합니다. 값의 범위는 0부터 999입니다. 밀리초를 지정 하지 않고 날짜를 생성 하는 경우 반환 되는 값은 0입니다.  
  
## <a name="remarks"></a>설명  
 기간 (밀리초) utc (협정 세계시)로 가져오려면는 `getUTCMilliseconds` 메서드.  
  
## <a name="example"></a>예제  
 사용 하는 방법을 보여 주는 다음 예제는 **getMilliseconds** 메서드.  
  
```JavaScript  
var date = new Date("1/1/2001");  
document.write(date.getMilliseconds());  
document.write("<br/>");  
  
date.setMilliseconds(5);  
document.write(date.getMilliseconds());  
// Output:   
// 0  
// 5  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **적용 대상**: [Date Object](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [getUTCMilliseconds 메서드 (Date)](../../javascript/reference/getutcmilliseconds-method-date-javascript.md)   
 [setMilliseconds 메서드 (Date)](../../javascript/reference/setmilliseconds-method-date-javascript.md)   
 [setUTCMilliseconds 메서드(Date)](../../javascript/reference/setutcmilliseconds-method-date-javascript.md)