---
title: "toString 메서드 (Error) | Microsoft Docs"
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
ms.assetid: 5d6d9712-c06d-4b31-9bc9-e46f6bb5cd38
caps.latest.revision: "2"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d774ff8c0f5338f4178b2262bf8ac8cadc074453
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="tostring-method-error"></a>toString 메서드(Error)
오류의 문자열 표현을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
error.toString()  
```  
  
## <a name="parameters"></a>매개 변수  
 `date`  
 필수 요소. 나타내는 문자열로 서 오류가 발생 했습니다.  
  
## <a name="return-value"></a>반환 값  
 반환 "오류:" 오류 메시지와 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `toString` 메서드 오류가 발생 합니다.  
  
```JavaScript  
var myError = new Error();  
myError.message = "My Error";  
var errorString = myError.toString();  
document.write(errorString);  
  
// Output: Error: My Error  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]