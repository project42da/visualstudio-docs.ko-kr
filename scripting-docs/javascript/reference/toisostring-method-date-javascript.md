---
title: "toISOString 메서드 (Date) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- toISOString method [JavaScript]
ms.assetid: 58577d8f-3ae8-4887-8687-26233ea79ff6
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 31559e1bc44849573ec7dc903411ce98b0a4440d
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="toisostring-method-date-javascript"></a>toISOString 메서드(Date)(JavaScript)
ISO 형식으로 날짜를 문자열 값으로 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```JavaScript  
  
objDate.toISOString()  
```  
  
## <a name="return-value"></a>반환 값  
 국제 조직에서 표준화 (ISO) 형식 날짜의 문자열 표현입니다.  
  
## <a name="exceptions"></a>예외  
 경우 `objDate` 유효한 날짜를 포함 하지 않는 한 `RangeError` 예외가 throw 됩니다.  
  
## <a name="remarks"></a>설명  
 ISO 형식은 ISO 8601 서식의 단순화 된 버전입니다. 자세한 내용은 참조 [날짜 및 시간 문자열](../../javascript/date-and-time-strings-javascript.md)합니다.  
  
 표준 시간대는 항상 UTC, 출력에 접미사 Z로 표시 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `toISOString` 메서드를 사용하는 방법을 보여 줍니다.  
  
```JavaScript  
var dt = new Date("30 July 2010 15:05 UTC");  
document.write(dt.toISOString());  
document.write("<br />");  
document.write(dt.toUTCString());  
  
// Output:  
//  2010-07-30T15:05:00.000Z  
//  Fri, 30 Jul 2010 15:05:00 UTC  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv9](../../javascript/includes/jsv9-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [Date 개체](../../javascript/reference/date-object-javascript.md)   
 [날짜 및 시간 문자열](../../javascript/date-and-time-strings-javascript.md)