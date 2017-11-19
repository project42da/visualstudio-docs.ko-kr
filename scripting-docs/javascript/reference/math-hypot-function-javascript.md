---
title: "Math.hypot 함수 (JavaScript) | Microsoft Docs"
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
ms.assetid: 31488f5a-2230-4114-911e-b6d854c7b0a0
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a66c0b082356b8dde3f51f739c130378d694f3b4
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="mathhypot-function-javascript"></a>Math.hypot 함수(JavaScript)
인수 제곱합의 제곱근을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
Math.hypot ( value1[, value2[, ...values] );  
```  
  
#### <a name="parameters"></a>매개 변수  
 `value1`  
 필수 요소. 첫 번째 숫자입니다.  
  
 `value2`  
 선택 사항입니다. 두 번째 숫자입니다.  
  
 `values`  
 선택 사항입니다. 하나 이상의 숫자입니다.  
  
## <a name="remarks"></a>설명  
 인수 중 하나가 NaN이면 함수에서 NaN을 반환합니다. 인수가 제공되지 않으면 함수에서 0을 반환합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `Math.hypot` 함수를 사용하는 예를 보여 줍니다.  
  
```JavaScript  
Math.hypot(3, 4);  
// Returns 5  
  
Math.hypot(3, "4");  
// Returns 5  
  
Math.hypot(3, "four");  
// Returns NaN   
  
Math.hypot(3, 4, 10);  
// Returns 11.180339887498949  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]