---
title: "charCodeAt 메서드 (String) (JavaScript) | Microsoft Docs"
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
- charCodeAt
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- charCodeAt method
ms.assetid: 5b0290a7-ee4d-4738-a909-c02ef64a2f1a
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8e7b8e62dfd29aa42d9816d0c5e27cc90440751a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="charcodeat-method-string-javascript"></a>charCodeAt 메서드(String)(JavaScript)
지정된 된 위치에 있는 문자의 유니코드 값을 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
strObj. charCodeAt(index)  
```  
  
## <a name="parameters"></a>매개 변수  
 `strObj`  
 필수 요소. 모든 `String` 개체 또는 문자열 리터럴입니다.  
  
 `index`  
 필수 요소. 원하는 문자의 0부터 시작 하는 인덱스입니다. 지정된 된 인덱스에 문자가 없으면 `NaN` 반환 됩니다.  
  
## <a name="remarks"></a>설명  
  
## <a name="example"></a>예제  
 다음 예제에서는 `charCodeAt` 메서드를 사용하는 방법을 보여 줍니다.  
  
```JavaScript  
var str = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";   
document.write(str.charCodeAt(str.length - 1));  
  
// Output: 90   
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [String.fromCharCode 함수](../../javascript/reference/string-fromcharcode-function-javascript.md)