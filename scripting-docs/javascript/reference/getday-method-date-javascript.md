---
title: "getDay 메서드 (Date) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: getDay
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- GetDay method
- Date object
- dates, returning day of the week
ms.assetid: 27be7168-3dce-41c9-ae69-6280b7984c2e
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1749eca5aceee76947a0162f22700f32525fdec0
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="getday-method-date-javascript"></a>getDay 메서드(Date)(JavaScript)
현지 시간을 사용 하 여 해당 주의 일 수를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
dateObj. getDay()   
```  
  
#### <a name="parameters"></a>매개 변수  
 필요한 `dateObj` 참조는 `Date` 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 해당 주의 일을 나타내는 0부터 6 사이의 정수 (일요일은 0, 토요일은 6).  
  
## <a name="remarks"></a>설명  
 Utc (협정 세계시)를 사용 하 여 일을 사용은 `getUTCDay` 메서드.  
  
 다음 예제에서는 `getDay` 메서드를 사용하는 방법을 보여 줍니다.  
  
```JavaScript  
var date = new Date("Saturday, February 9, 2008");  
day = date.getDay();  
document.write(day);  
  
// Output: 6  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **적용 대상**: [Date Object](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [getUTCDay 메서드(Date)](../../javascript/reference/getutcday-method-date-javascript.md)