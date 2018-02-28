---
title: "String.fromCharCode 함수 (JavaScript) | Microsoft Docs"
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
- fromCharCode
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- fromCharCodeAt method
- characters, from Unicode
ms.assetid: f64120c1-23a7-48ca-8d1c-db3e8856cab4
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: dbcd9062d7da0b73647c1d9eb6cc207af23c3532
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="stringfromcharcode-function-javascript"></a>String.fromCharCode 함수(JavaScript)
여러 유니코드 문자 값에서 문자열을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
String.fromCharCode([code1[, code2[, ...[, codeN]]]])   
```  
  
## <a name="parameters"></a>매개 변수  
 `String`  
 필수 요소. `String` 개체  
  
 `code1`, . 입니다. 입니다. , `codeN`  
 선택 사항입니다. 일련의 유니코드 문자 값을 문자열로 변환 합니다. 인수를 제공 하는 경우 결과 빈 문자열입니다.  
  
## <a name="remarks"></a>설명  
 이 기능을 호출의 `String` 개체 대신 문자열 인스턴스입니다.  
  
 다음 예제에서는이 메서드를 사용 하는 방법을 보여 줍니다.  
  
```JavaScript  
var test = String.fromCharCode(112, 108, 97, 105, 110);  
document.write(test);  
  
// Output: plain  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [charCodeAt 메서드(String)](../../javascript/reference/charcodeat-method-string-javascript.md)