---
title: "getFullYear 메서드 (Date) (JavaScript) | Microsoft Docs"
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
- getFullYear
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- dates, returning year
- Date object
- getFullYear method
ms.assetid: f9ec1262-02e9-4791-90b5-48f33b1dc4bc
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 211d6c86435e39eb75b9b1ce3415738541ca07db
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="getfullyear-method-date-javascript"></a>getFullYear 메서드(Date)(JavaScript)
현지 시간을 사용 하 여 연도를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
dateObj.getFullYear()   
```  
  
#### <a name="parameters"></a>매개 변수  
 필요한 `dateObj` 참조는 `Date` 개체입니다.  
  
## <a name="return-value"></a>반환 값  
 네 자리 숫자로 된 연도입니다. 예를 들어 1976 년 1976으로 반환 됩니다. 두 자리로 지정 된 최근 년의 `Date` 생성자 또는 `setFullYear` "5/14/12"를 제공 하므로 20 세기의 것으로 가정 됩니다 `getFullYear` "1912"를 반환 합니다.  
  
## <a name="remarks"></a>설명  
 Utc (협정 세계시)를 사용 하 여 연도 가져오려면는 `getUTCFullYear` 메서드.  
  
## <a name="example"></a>예제  
 다음 예제에서는 **getFullYear** 메서드.  
  
```JavaScript  
var date = new Date("1/1/01");  
document.write(date.getFullYear());  
  
// Output: 1901  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **적용 대상**: [Date Object](../../javascript/reference/date-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [getUTCFullYear 메서드 (Date)](../../javascript/reference/getutcfullyear-method-date-javascript.md)   
 [setFullYear 메서드 (Date)](../../javascript/reference/setfullyear-method-date-javascript.md)   
 [setUTCFullYear 메서드(Date)](../../javascript/reference/setutcfullyear-method-date-javascript.md)