---
title: "toLocaleString 메서드 (Object) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: toLocaleString
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: toLocaleString method
ms.assetid: 0901afcb-126b-4ed7-bd6a-2301d50e2326
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 3f88e1c702cd8a7d702630ae90ef840c4af88f30
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="tolocalestring-method-object-javascript"></a>toLocaleString 메서드(Object)(JavaScript)
현재 로캘을 사용 하 여 문자열로 변환 된 날짜를 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
dateObj.toLocaleString()   
```  
  
## <a name="remarks"></a>설명  
 필요한 `dateObj` 는 임의의 `Date` 개체입니다.  
  
 `toLocaleString` 메서드가 반환 되는 `String` 현재 로캘의 기본 형식으로 작성 된 날짜를 포함 하는 개체입니다.  
  
-   1999 서 기 1601 사이의 날짜, 사용자의 패널 국가별 설정 형식이 사용 됩니다.  
  
-   기본 형식이 범위를 벗어난 날짜에 대 한는 **toString** 메서드를 사용 합니다.  
  
 예를 들어 미국에에서 `toLocaleString` 반환 "01/05/96 00시: 00" 1 월 5에 대 한 합니다. 반환 유럽에서 "05/01/96 00시: 00" 같은 날짜에 대 한 유럽 규칙으로 배치 월 이전 합니다.  
  
> [!NOTE]
>  `toLocaleString`만을 사용해; 사용자에 게 결과 표시 합니다. 것 해야에 사용 되지 기준으로 스크립트 내에서 계산 반환 된 컴퓨터 관련 됩니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `toLocaleString` 메서드를 사용하는 방법을 보여 줍니다.  
  
```JavaScript  
function toLocaleStrDemo(){     
   var d, s;                      //Declare variables.  
   d = new Date();                //Create Date object.  
   s = "Current setting is ";  
   s += d.toLocaleString();       //Convert to current locale.  
   return(s);                     //Return converted date  
}  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **적용 대상**: [배열 개체](../../javascript/reference/array-object-javascript.md)&#124; [개체 날짜](../../javascript/reference/date-object-javascript.md)&#124; [개체 번호](../../javascript/reference/number-object-javascript.md)&#124; [개체 개체](../../javascript/reference/object-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [toLocaleDateString 메서드(Date)](../../javascript/reference/tolocaledatestring-method-date-javascript.md)