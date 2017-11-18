---
title: "valueOf 메서드 (Date) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 39a1f96e-14b0-4db2-b53d-cdfd67cbb208
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 87c5e6ea3c3e28d866f7cabf92dc97b81703b5b1
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="valueof-method-date"></a>valueOf 메서드(Date)
UTC 1970 년 1 월 1 일 자정 이후의 시간 (밀리초)에 저장 된 시간 값을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
date.valueOf()  
```  
  
#### <a name="parameters"></a>매개 변수  
 `date` 개체는 날짜의 모든 인스턴스입니다.  
  
## <a name="return-value"></a>반환 값  
 UTC 1970 년 1 월 1 일 자정 이후의 시간 (밀리초)에 저장 된 시간 값입니다. 이 동일한 값과 `getTime`합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `valueOf` 날짜와 메서드.  
  
```JavaScript  
var myDate = new Date();  
myDate.setFullYear(2100, 5, 5);  
if (myDate.getTime() == myDate.valueOf())  
    document.write("values are the same");  
else  
    document.write("values are different");  
  
// Output: values are the same  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]