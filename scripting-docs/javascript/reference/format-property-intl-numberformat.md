---
title: "format 속성 (Intl.NumberFormat) | Microsoft Docs"
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
ms.assetid: 68c3223a-023c-4fa0-aa99-d049a7a0e26a
caps.latest.revision: "5"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: be40f8e94220ad7504dd3b9736e71b3416bb3d2a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="format-property-intlnumberformat"></a>format 속성(Intl.NumberFormat)
지정 된 숫자 포맷터 설정을 사용 하 여 로캘별 숫자 형식을 지정 하는 함수를 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
numberFormatObj.format  
```  
  
#### <a name="parameters"></a>매개 변수  
 `numberFormatObj`  
 필수 요소. 이름에서 `NumberFormat` 포맷터로 사용할 개체입니다.  
  
## <a name="remarks"></a>설명  
 함수에서 반환 되는 `format` 는 하나의 인수를 사용 하는 속성 `value`에 지정 된 옵션을 사용 하 여 지역화 된 수를 나타내는 문자열을 반환 하 고는 `NumberFormat` 개체입니다. 경우 `value` 를 제공 하지 않으면 함수 반환 `NaN` (숫자가 아님).  
  
## <a name="example"></a>예제  
 다음 예제에서는 `NumberFormat` 지역화 된 번호를 만들 개체입니다.  
  
```JavaScript  
var nf = new Intl.NumberFormat(["en-US"], {  
    style: "currency",  
    currency: "CNY",  
    currencyDisplay: "symbol",  
    maximumFractionDigit: 1  
})  
  
if (console && console.log) {  
    console.log(nf.format(100)); // "¥100.00"  
}  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [Intl.NumberFormat 개체](../../javascript/reference/intl-numberformat-object-javascript.md)