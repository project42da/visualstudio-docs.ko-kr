---
title: Number.isSafeInteger (Number) (JavaScript) | Microsoft Docs
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
ms.assetid: c7ef6ce8-fe71-4e53-be44-4dd440aef21d
caps.latest.revision: "2"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: eebc2147bc5043341be7e883548af825922036f9
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="numberissafeinteger-number-javascript"></a>Number.isSafeInteger(Number)(JavaScript)
숫자가 JavaScript에서 안전하게 표현될 수 있는지를 나타내는 부울 값을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
Number.isSafeInteger(numValue)   
```  
  
## <a name="return-value"></a>반환 값  
 숫자가 `Number.MIN_SAFE_INTEGER`와 `Number.MAX_SAFE_INTEGER`(포함) 사이에 있으면 `true`이고, 그렇지 않으면 `false`입니다.  
  
## <a name="remarks"></a>설명  
 JavaScript에서 안전한 정수는 반올림이 적용되기 전의 IEEE-754 배정밀도 숫자인 정수입니다.  
  
## <a name="example"></a>예제  
  
```JavaScript  
// Returns true  
Number.isSafeInteger(-100)  
Number.isSafeInteger(9007199254740991)  
  
// Returns false  
Number.isSafeInteger(Number.NaN)  
Number.isSafeInteger(Infinity)  
Number.isSafeInteger("100")  
Number.isSafeInteger(9007199254740992);  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]  
  
 **적용 대상**: [개체 번호](../../javascript/reference/number-object-javascript.md)