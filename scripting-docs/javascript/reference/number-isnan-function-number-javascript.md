---
title: "Number.isNaN 함수 (Number) (JavaScript) | Microsoft Docs"
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
ms.assetid: 2d9813d6-ec9c-433b-b060-8e3c3ff62ca4
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7c11abe2dd2fc70431800d31f4c44279a88cd75d
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="numberisnan-function-number-javascript"></a>Number.isNaN 함수(Number)(JavaScript)
값이 예약된 값 `NaN`(숫자 아님)인지 여부를 나타내는 부울 값을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
Number.isNaN(numValue)   
```  
  
#### <a name="parameters"></a>매개 변수  
 `numValue`  
 필수 요소. `NaN`에 대해 테스트할 값입니다.  
  
## <a name="return-value"></a>반환 값  
 `Number` 형식으로 변환된 값이 `NaN`이면 `true`이고, 그렇지 않으면 `false`입니다.  
  
## <a name="remarks"></a>설명  
 일반적으로 이 메서드를 사용하여 `parseInt` 및 `parseFloat` 메서드의 반환 값을 테스트합니다.  
  
 `Number.isNaN`은 전역 `isNaN` 함수와 관련된 문제를 해결합니다. `Number.isNaN`은 `NaN`과 비교한 후에만 해당 인수를 Number 형식으로 변환합니다. 따라서 전달된 인수가 `NaN`과 정확히 동일한 값인 경우에만 `true`를 반환합니다. 전역 `isNaN` 함수는 비교 전에 해당 인수를 Number 형식으로 변환하기 때문에 숫자가 아닌 값이 `true`를 반환하고 `Number.isNaN`에 대해 `true`가 반환되지 않을 수 있습니다.  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]  
  
 **적용 대상**: [개체 번호](../../javascript/reference/number-object-javascript.md)  
  
## <a name="example"></a>예제  
  
```JavaScript  
// Returns true.  
Number.isNaN(NaN);  
Number.isNaN(Number.NaN);  
Number.isNaN(0 / 0);  
  
// Returns false.  
Number.isNaN(100);  
// Returns false.  
// Strings are converted to numbers and return false.  
Number.isNaN("100");  
Number.isNaN("ABC");  
Number.isNaN("10C");  
Number.isNaN("abc123");  
  
```