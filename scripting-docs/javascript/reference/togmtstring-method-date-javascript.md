---
title: "toGMTString 메서드 (Date) (JavaScript) | Microsoft Docs"
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
- toGMTString
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- toGMTString method
ms.assetid: 9dc1e722-5722-4b8c-a213-a2650f55f207
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: cef8a61e04fbb5ada6e03fa946f434327422d9d7
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="togmtstring-method-date-javascript"></a>toGMTString 메서드(Date)(JavaScript)
그리니치 의미 Time(GMT)를 사용 하 여 문자열로 변환 된 날짜를 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
dateObj.toGMTString()   
```  
  
## <a name="remarks"></a>설명  
 필요한 `dateObj` 참조는 임의의 `Date` 개체입니다.  
  
 `toGMTString` 메서드는 더 이상 제공 됩니다에 대 한 이전 버전과 호환성을 위해서만 합니다. 사용 하는 것이 좋습니다.는 `toUTCString` 메서드 대신 합니다.  
  
 `toGMTString` 메서드가 반환 되는 `String` 날짜를 포함 하는 개체 GMT 규칙을 사용 하 여 지정 합니다. 반환 값의 형식은 다음과 같습니다: "05 Jan 1996 00시: 00 GMT"  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **적용 대상**: [Date Object](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [toUTCString 메서드(Date)](../../javascript/reference/toutcstring-method-date-javascript.md)