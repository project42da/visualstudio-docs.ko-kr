---
title: "getUTCMinutes 메서드 (Date) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: getUTCMinutes
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- minutes
- UTC times, returning
- getUTCMinutes method
ms.assetid: b6d92543-b285-4e46-8f47-bba36e53fabd
caps.latest.revision: "11"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fe691d3b52d18340eeeff81a91c049a262277c54
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="getutcminutes-method-date-javascript"></a>getUTCMinutes 메서드(Date)(JavaScript)
시간 (분)를 가져옵니다는 `Date` utc (협정 세계시)를 사용 하 여 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
dateObj.getUTCMinutes()   
```  
  
#### <a name="parameters"></a>매개 변수  
 필요한 `dateObj` 참조는 `Date` 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 0에서 59 사이의 정수를 반환합니다. 1 분의 시간 후에 0이 반환 됩니다. 경우는 `Date` 시간을 지정 하지 않고 개체가 만들어진, UTC는 기본적으로 분 값은 0입니다. 그러나 다른 표준 시간대 다 수 있습니다.  
  
## <a name="remarks"></a>설명  
 현지 시간을 사용 하 여 저장 된 분 수를 가져오려면는 `getMinutes` 메서드.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `getUTCMinutes` 메서드를 사용하는 방법을 보여 줍니다.  
  
```JavaScript  
var date = new Date("1/1/2001");  
document.write(date.getUTCMinutes());  
document.write("<br/>");  
  
date.setMinutes(5);  
document.write(date.getUTCMinutes());  
  
// Output:   
// 0  
// 5  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **적용 대상**: [Date Object](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [getMinutes 메서드 (Date)](../../javascript/reference/getminutes-method-date-javascript.md)   
 [setMinutes 메서드 (Date)](../../javascript/reference/setminutes-method-date-javascript.md)   
 [setUTCMinutes 메서드(Date)](../../javascript/reference/setutcminutes-method-date-javascript.md)