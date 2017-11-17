---
title: "Math.acos 함수 (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: acos
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- acos method
- arcosine method
ms.assetid: 828cb3c3-bdf7-4bb7-97ae-3617ce4b2d62
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 773499287e215fbc161f289954811d3ef62bcba6
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="mathacos-function-javascript"></a>Math.acos 함수(JavaScript)
숫자의 아크코사인 (또는 역 코사인)을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
Math.acos(number)  
```  
  
#### <a name="parameters"></a>매개 변수  
 필수 `number` 인수는 숫자 식입니다.  
  
## <a name="return-value"></a>반환 값  
 아크코사인은 `number` 라디안에서의 인수입니다.  
  
## <a name="example"></a>예제  
 다음 코드에서는 `acos` 함수를 사용하는 방법을 보여 줍니다.  
  
```JavaScript  
var v1 = Math.acos(-1.0);  
var v2 = Math.cos(-1.0);  
  
document.write(v1);  
document.write("<br/>");  
document.write(v2);  
  
// Output:  
// 3.141592653589793  
// 0.5403023058681398  
  
```  
  
## <a name="remarks"></a>설명  
 **적용 대상**: [Math 개체](../../javascript/reference/math-object-javascript.md)  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [Math.asin 함수](../../javascript/reference/math-asin-function-javascript.md)   
 [Math.atan 함수](../../javascript/reference/math-atan-function-javascript.md)   
 [Math.cos 함수](../../javascript/reference/math-cos-function-javascript.md)   
 [Math.sin 함수](../../javascript/reference/math-sin-function-javascript.md)   
 [Math.tan 함수](../../javascript/reference/math-tan-function-javascript.md)   
 [Math 개체](../../javascript/reference/math-object-javascript.md)