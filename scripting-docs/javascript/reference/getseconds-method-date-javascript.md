---
title: "getSeconds 메서드 (Date) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: getSeconds
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- seconds method
- GetSeconds method
ms.assetid: 97b10674-af0b-4681-a846-38f972196501
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 151d720b92fb9d7068c320983a25b965078f1b2e
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="getseconds-method-date-javascript"></a>getSeconds 메서드(Date)(JavaScript)
초 가져옵니다는 `Date` 현지 시간을 사용 하 여 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
dateObj.getSeconds()   
```  
  
#### <a name="parameters"></a>매개 변수  
 필요한 `dateObj` 참조는 `Date` 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 0에서 59 사이의 정수를 반환합니다. 시간은 1 초 미만 현재 분에 0이 반환 됩니다. 경우는 `Date` 시간을 지정 하지 않고 개체가 만들어진, 기본적으로 초 값은 0입니다.  
  
## <a name="remarks"></a>설명  
 초 utc (협정 세계시)를 사용 하 여 값을 사용은 `getUTCSeconds` 메서드.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `getSeconds` 메서드를 사용하는 방법을 보여 줍니다.  
  
```JavaScript  
var date = new Date("1/1/2001");  
document.write(date.getSeconds());  
document.write("<br/>");  
  
date.setSeconds(5);  
document.write(date.getSeconds());  
  
// Output:  
// 0  
// 5  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **적용 대상**: [Date Object](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [getUTCSeconds 메서드 (Date)](../../javascript/reference/getutcseconds-method-date-javascript.md)   
 [setSeconds 메서드 (Date)](../../javascript/reference/setseconds-method-date-javascript.md)   
 [setUTCSeconds 메서드(Date)](../../javascript/reference/setutcseconds-method-date-javascript.md)