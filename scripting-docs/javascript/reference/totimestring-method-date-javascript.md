---
title: "toTimeString 메서드 (Date) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: toTimeString
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: toTimeString method
ms.assetid: a4a8c0f2-55a9-4e84-94c3-f0a547fb04b5
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4d9af1f688fee0c066158d8504e00f22af9b3a21
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="totimestring-method-date-javascript"></a>toTimeString 메서드(Date)(JavaScript)
문자열 값으로 시간을 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
objDate. toTimeString( )  
```  
  
## <a name="remarks"></a>설명  
 필요한 `objDate` 참조는 `Date` 개체입니다.  
  
 `toTimeString` 메서드가 현재 표준 시간대의 시간을 포함 하는 문자열 값을 반환 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 UTC 1970 년 1 월 1 일 자정 이후의 시간을 2000 밀리초로 설정 하 고 쓰여집니다 합니다.  
  
```JavaScript  
var aDate = new Date();  
     aDate.setTime(2000);  
     document.write(aDate.toTimeString());  
  
// Output depends on the time in the current time zone.  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [toDateString 메서드 (Date)](../../javascript/reference/todatestring-method-date-javascript.md)   
 [toLocaleTimeString 메서드(Date)](../../javascript/reference/tolocaletimestring-method-date-javascript.md)