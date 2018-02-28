---
title: "getUTCFullYear 메서드 (Date) (JavaScript) | Microsoft Docs"
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
- getUTCFullYear
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- getUTCFullYear method
- Date object
- UTCFullYear method
- dates, UTC
- UTC dates, returning
- Full Year method
- UTC dates, getting
ms.assetid: f11e5363-ef8a-48dd-9d56-4ee7290c7c48
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c8268631a96eed1f61ef4ba908b78680c8522096
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="getutcfullyear-method-date-javascript"></a>getUTCFullYear 메서드(Date)(JavaScript)
Utc (협정 세계시)를 사용 하 여 연도를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
dateObj.getUTCFullYear()   
```  
  
#### <a name="parameters"></a>매개 변수  
 필요한 `dateObj` 참조는 `Date` 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 네 자리 숫자로 된 연도 반환합니다. 두 자리로 지정 된 최근 년의 `Date` 생성자 또는 `setFullYear` "5/14/12"를 제공 하므로 20 세기의 것으로 가정 됩니다 `getUTCFullYear` "1912"를 반환 합니다.  
  
## <a name="remarks"></a>설명  
 현지 시간을 사용 하 여 연도 가져오려면는 `getFullYear` 메서드.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `getUTCFullYear` 메서드를 사용하는 방법을 보여 줍니다.  
  
```JavaScript  
var date = new Date("1/9/36");  
document.write(date.getUTCFullYear());  
  
// Output: 1936  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **적용 대상**: [Date Object](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [getFullYear 메서드 (Date)](../../javascript/reference/getfullyear-method-date-javascript.md)   
 [setFullYear 메서드 (Date)](../../javascript/reference/setfullyear-method-date-javascript.md)   
 [setUTCFullYear 메서드(Date)](../../javascript/reference/setutcfullyear-method-date-javascript.md)