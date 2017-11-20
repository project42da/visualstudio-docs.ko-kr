---
title: "toUTCString 메서드 (Date) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: toUTCString
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- UTC dates, converting to strings
- toUTCString method
ms.assetid: eb0983ed-7884-42fa-a2cc-de92b3111207
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0bd5efc43152c1af2dd467b73dce235e8fe52f29
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="toutcstring-method-date-javascript"></a>toUTCString 메서드(Date)(JavaScript)
Utc (협정 세계시)를 사용 하 여 문자열로 변환 된 날짜를 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
dateObj.toUTCString()   
```  
  
## <a name="remarks"></a>설명  
 필요한 `dateObj` 참조는 임의의 `Date` 개체입니다.  
  
 `toUTCString` 메서드가 반환 되는 `String` UTC 규칙을 사용 하 여 편리 하 고 서식을 날짜를 포함 하는 개체 읽기 쉬운 형식입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `toUTCString` 메서드를 사용하는 방법을 보여 줍니다.  
  
```JavaScript  
function toUTCStrDemo(){  
   var d, s;                   //Declare variables.  
   d = new Date();             //Create Date object.  
   s = "Current setting is ";  
   s += d.toUTCString();       //Convert to UTC string.  
   return(s);                  //Return UTC string.  
}  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **적용 대상**: [Date Object](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [toGMTString 메서드(Date)](../../javascript/reference/togmtstring-method-date-javascript.md)