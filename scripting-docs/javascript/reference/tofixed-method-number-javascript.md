---
title: "toFixed 메서드 (Number) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: toFixed
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: toFixed method
ms.assetid: b5f03400-865e-4ab2-818c-f734c0f6d6f0
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: dd51dd67632f4e6417fee72fd19575025423bbf1
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="tofixed-method-number-javascript"></a>toFixed 메서드(Number)(JavaScript)
고정 소수점 표기법으로 숫자를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
numObj.toFixed([fractionDigits])  
```  
  
## <a name="parameters"></a>매개 변수  
 `numObj`  
 필요한 A `Number` 개체입니다.  
  
 `fractionDigits`  
 선택 사항입니다. 소수점 뒤에 자릿수의 수입니다. 0-20 범위에 있어야 합니다.  
  
## <a name="return-value"></a>반환 값  
 고정 소수점 표기법으로 숫자의 문자열 표현을 반환 포함 된 `fractionDigits` 소수점 뒤에 자릿수입니다.  
  
 경우 `fractionDigits` 제공 되지 않으면 또는 **정의 되지 않은**, 기본값은 0입니다.  
  
## <a name="example"></a>예제  
 다음 코드를 사용 하는 방법을 보여 줍니다 `toFixed`합니다.  
  
```JavaScript  
var num = new Number(123);  
var fix = num.toFixed();  
document.write(fix);  
document.write("<br/>");  
  
num = new Number(123.456);  
fix = num.toFixed(5);  
document.write(fix);  
  
// Output:  
// 123  
123.45600  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
 **적용 대상**: [개체 번호](../../javascript/reference/number-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [toExponential 메서드 (Number)](../../javascript/reference/toexponential-method-number-javascript.md)   
 [toPrecision 메서드(Number)](../../javascript/reference/toprecision-method-number-javascript.md)