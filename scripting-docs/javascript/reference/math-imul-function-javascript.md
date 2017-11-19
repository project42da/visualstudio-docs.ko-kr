---
title: "Math.imul 함수 (JavaScript) | Microsoft Docs"
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
ms.assetid: dce5e11c-36b9-4c39-84d3-6cd494dd1cbf
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 57820d0926d574c75924f4eef6265ef7fa0766da
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="mathimul-function-javascript"></a>Math.imul 함수(JavaScript)
32비트 부호 있는 정수로 처리되는 두 숫자의 곱을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
Math.imul(x, y);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `x`  
 필수 요소. 첫 번째 숫자입니다.  
  
 `y`  
 필수 요소. 두 번째 숫자입니다.  
  
## <a name="remarks"></a>설명  
 이 함수는 Emscripten 및 Mandreel 같이 JavaScript와 같은 방식으로 정수 곱을 구현하지 않는 컴파일러에 사용됩니다.  
  
## <a name="example"></a>예제  
 다음 코드 예제에서는 `Math.imul`을  사용하여 숫자를 곱하는 방법을 보여 줍니다.  
  
```JavaScript  
var result1 = Math.imul(2, 5);  
// result1 == 10  
  
var result2 = Math.imul(Math.pow(2, 32) - 1, Math.pow(2, 32) - 2);  
// result2 == 2   
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]