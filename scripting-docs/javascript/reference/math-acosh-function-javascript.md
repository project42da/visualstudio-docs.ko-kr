---
title: "Math.acosh 함수 (JavaScript) | Microsoft Docs"
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
ms.assetid: 881dd2a0-36a5-403b-a3dc-523d8e1e1317
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1fd75140dfcf3d9ac703c2aeadf68bea4da9e0dc
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="mathacosh-function-javascript"></a>Math.acosh 함수(JavaScript)
숫자의 쌍곡 아크코사인(또는 쌍곡선 역코사인)을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
Math.acosh(number)  
```  
  
#### <a name="parameters"></a>매개 변수  
 필수 `number` 인수는 숫자 식입니다.  
  
## <a name="return-value"></a>반환 값  
 `number` 인수의 쌍곡선 역코사인을 라디안 단위로 계산합니다.  
  
## <a name="example"></a>예제  
 다음 코드에서는 `acosh` 함수를 사용하는 방법을 보여 줍니다.  
  
```JavaScript  
var v1 = Math.acosh(3);  
vary v2 = Math.acosh(-1);  
  
document.write(v1);  
document.write("</br>");  
document.write(v2);  
  
// Output:  
// 1.762747174039086  
// NaN  
  
```  
  
## <a name="remarks"></a>설명  
 **적용 대상**: [Math 개체](../../javascript/reference/math-object-javascript.md)  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [Math.acos 함수](../../javascript/reference/math-acos-function-javascript.md)   
 [Math.asin 함수](../../javascript/reference/math-asin-function-javascript.md)   
 [Math.atan 함수](../../javascript/reference/math-atan-function-javascript.md)   
 [Math.cos 함수](../../javascript/reference/math-cos-function-javascript.md)   
 [Math.sin 함수](../../javascript/reference/math-sin-function-javascript.md)   
 [Math.tan 함수](../../javascript/reference/math-tan-function-javascript.md)   
 [Math 개체](../../javascript/reference/math-object-javascript.md)