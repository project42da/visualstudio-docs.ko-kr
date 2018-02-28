---
title: "getUTCMilliseconds 메서드 (Date) (JavaScript) | Microsoft Docs"
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
- getUTCMilliseconds
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- milliseconds
- UTC times, returning
- getUTCMilliseconds method
ms.assetid: 7491d387-7b6a-40df-89e5-55c64795ef70
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3fb7cf202c8511bec00c10dc5b8c23bd198d8700
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="getutcmilliseconds-method-date-javascript"></a>getUTCMilliseconds 메서드(Date)(JavaScript)
시간 (밀리초)를 가져옵니다는 `Date` utc (협정 세계시)를 사용 하 여 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
dateObj.getUTCMilliseconds()   
```  
  
#### <a name="parameters"></a>매개 변수  
 필요한 `dateObj` 참조는 `Date` 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 0-999에서의 범위는 밀리초 값을 반환 합니다.  
  
## <a name="remarks"></a>설명  
 현지 시간으로 밀리초 수를 가져오려면는 `getMilliseconds` 메서드.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `getUTCMilliseconds` 메서드를 사용하는 방법을 보여 줍니다.  
  
```JavaScript  
var date = new Date("1/1/2001");  
document.write(date.getUTCMilliseconds());  
document.write("<br/>");  
  
date.setMilliseconds(34);  
document.writedate.getUTCMilliseconds());  
  
// Output:  
// 0   
// 34   
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **적용 대상**: [Date Object](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [getMilliseconds 메서드 (Date)](../../javascript/reference/getmilliseconds-method-date-javascript.md)   
 [setMilliseconds 메서드 (Date)](../../javascript/reference/setmilliseconds-method-date-javascript.md)   
 [setUTCMilliseconds 메서드(Date)](../../javascript/reference/setutcmilliseconds-method-date-javascript.md)