---
title: "concat 메서드 (String) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: concat
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- concat method (String)
- Concat method
ms.assetid: 5d28ebb2-d534-4179-9297-a4c821ee9f24
caps.latest.revision: "14"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 1b6419cc6404e06fc780802a30a3b4add8320881
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="concat-method-string-javascript"></a>concat 메서드(String)(JavaScript)
두 개 이상의 문자열의 연결을 포함 하는 문자열을 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
string1. concat([string2[, string3[, . . . [, stringN]]]])  
```  
  
## <a name="parameters"></a>매개 변수  
 `string1`  
 필수 요소. `String` 개체 또는 문자열 리터럴을 다른 모든 문자열을 연결을 지정 합니다.  
  
 `string2,. . ., stringN`  
 선택 사항입니다. 문자열의 끝에 추가할 `string1`합니다.  
  
## <a name="remarks"></a>설명  
 결과 `concat` 하는 것과 같습니다: `result`  =  `string1`  +  `string2`  +  `string3`  +  `stringN`합니다. 변경 된 값을 원본 또는 결과 문자열에 다른 문자열에 값 영향을 주지 않습니다. 인수 중 하나로 문자열이 면 변환한 문자열로 연결 하기 전에 `string1`합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `concat` 메서드 문자열과 함께 사용 하는 경우:  
  
```JavaScript  
var str1 = "ABCD"  
var str2 = "EFGH";  
var str3 = "1234";  
var str4 = "5678";  
document.write(str1.concat(str2, str3, str4));  
  
// Output: "ABCDEFGH12345678"  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **적용 대상**: [문자열 개체](../../javascript/reference/string-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [더하기 연산자(+)](../../javascript/reference/addition-operator-decrement-javascript.md)