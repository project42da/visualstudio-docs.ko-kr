---
title: "normalize 메서드 (String) (JavaScript) | Microsoft Docs"
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
ms.assetid: d50077c1-b5fa-4e7a-9c9d-dc66cfc423ac
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: aece38339ea1ce8924f404938b2d35d07504d539
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="normalize-method-string-javascript"></a>normalize 메서드(String)(JavaScript)
지정된 문자열의 유니코드 정규화 형식을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
stringObj.normalize([form]);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `stringObj`  
 필수 요소. 테스트할 문자열 개체입니다.  
  
 `form`  
 선택적 요소. 유니코드 정규화 형식 값입니다.  
  
## <a name="return-value"></a>반환 값  
 지정된 문자열의 유니코드 정규화 형식입니다.  
  
## <a name="exceptions"></a>예외  
 `form`이 지원되지 않는 값인 경우`RangeError`가 발생합니다.  
  
## <a name="remarks"></a>설명  
 `stringObj`가 문자열이 아닌 경우 메서드가 문자열의 유니코드 정규화 형식 반환을 시도하기 전에 문자열로 변환됩니다.  
  
 `form`해야 됩니다 "NFC", "NFD", "NFKC" 또는 "NFKD" 유니코드 정규화 형식 값에 해당 하에 지정 된 값 [Unicode Standard Annex #15](http://www.unicode.org/reports/tr15/)합니다. `form`의 기본값은 “NFC”입니다.  
  
## <a name="example"></a>예제  
 다음 코드 예제에서는 `normalize` 메서드의 사용 방법을 보여 줍니다.  
  
```JavaScript  
// ANGSTORM SIGN and LATIN CAPITAL A WITH RING ABOVE is canonically equivalent  
"\u212b".normalize("NFC") === "\u00c5";  
  
// Decomposed, ANGSTOM SIGN is LATIN CAPITAL A followed by COMBINING RING ABOVE  
"\u212b".normalize("NFD") === "\u0041\u030a"  
  
// Normalization Form C will combine the result back into the precombined character  
"\u0041\u030a".normalize("NFC") === "\u00c5"  
  
// LATIN SMALL LIGATURE FI is compatibility equivalent with LATIN SMALL LETTER F followed by  
// LATIN SMALL LETTER I.  
"\ufb01".normalize("NFKD") === "fi";  
  
// Same mapping in NFKC  
"\ufb01".normalize("NFKC") === "fi";  
  
// NFKC will not recombine compatibility characters.  
"fi".normalize("NFKC") === "fi";  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]