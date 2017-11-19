---
title: "getTimezoneOffset 메서드 (Date) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: getTimeZoneOffset
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- getTimezoneOffset method
- time zones [Visual Studio]
ms.assetid: 58ee22b0-4688-45bd-a337-cc23119b09ce
caps.latest.revision: "16"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e49a3c8b7060e6097300f8aaf99b2ef869833018
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="gettimezoneoffset-method-date-javascript"></a>getTimezoneOffset 메서드(Date)(JavaScript)
로컬 컴퓨터에 시간과 utc (협정 세계시) 사이의 차이 (분)를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
dateObj.getTimezoneOffset()   
```  
  
#### <a name="parameters"></a>매개 변수  
 필요한 `dateObj` 참조는 `Date` 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 현재 컴퓨터의 시간 간격 (분)의 수를 반환 (클라이언트 컴퓨터 또는 서버 시스템의 서버 스크립트에서이 메서드는 경우) 및 UTC입니다. 이 현재 컴퓨터의 현지 시간 뒤에 있는 경우 (예: 태평양 일광 절약 시간)를 나타내고 음수는 현재 컴퓨터의 현지 시간 (예: 일본) UTC 보다 늦은 이면 양수입니다. 년 12 월 1 일 클라이언트가 Los Angeles에 뉴욕에 있는 서버 연결 경우 `getTimezoneOffset` 서버에서 실행 하는 경우 클라이언트 또는 300에서 실행 하는 경우 480을 반환 합니다.  
  
## <a name="remarks"></a>설명  
  
## <a name="example"></a>예제  
 다음 예제에서는 `getTimezoneOffset` 메서드를 사용하는 방법을 보여 줍니다.  
  
```JavaScript  
var date =  new Date();  
var minutes = date.getTimezoneOffset();  
  
if (minutes < 0)  
    document.write(minutes / 60 + " hours after UTC");  
else  
    document.write(minutes / 60 + " hours before UTC");  
  
// Output (for example, where local time is PST):   
7 hours before UTC  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **적용 대상**: [Date Object](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [getTime 메서드(Date)](../../javascript/reference/gettime-method-date-javascript.md)