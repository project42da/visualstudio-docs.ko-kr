---
title: "charAt 메서드 (String) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: charAt
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- String object, returning characters
- charAt method
- characters, returning part of
ms.assetid: 63173e15-17f6-47c5-8f94-98ef1eb04c1a
caps.latest.revision: "14"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 201d85fec4ba184f0842c7401d986650b9ee078c
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="charat-method-string-javascript"></a>charAt 메서드(String)(JavaScript)
지정한 인덱스에 해당하는 문자를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
strObj. charAt(index)  
```  
  
## <a name="parameters"></a>매개 변수  
 `strObj`  
 필수 요소. 모든 `String` 개체 또는 문자열 리터럴입니다.  
  
 `index`  
 필수 요소. 원하는 문자의 0부터 시작 하는 인덱스입니다.  
  
## <a name="remarks"></a>설명  
 `charAt` 메서드 반환 값을 지정 된 문자를 `index`합니다. 문자열의 첫 번째 문자는 인덱스 0에, 두 번째는 1 이며 붙습니다. 값 `index` 되 반환 되는 범위를 벗어났습니다. 빈 문자열입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `charAt` 메서드:  
  
```JavaScript  
var str = "ABCDEFGHIJKLMNOPQRSTUVWXYZ";  
document.write(str.charAt(str.length - 1));  
  
// Output: Z  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **적용 대상**: [문자열 개체](../../javascript/reference/string-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [String 개체](../../javascript/reference/string-object-javascript.md)