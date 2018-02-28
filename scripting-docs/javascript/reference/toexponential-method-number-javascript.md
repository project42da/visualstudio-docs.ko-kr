---
title: "toExponential 메서드 (Number) (JavaScript) | Microsoft Docs"
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
- toExponential
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- toExponential method
ms.assetid: 7c4a6d84-3c1f-4cc4-a67d-7753e5d4ed66
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fff2f2bc0c443fa9308c8d01dcea42a3cec9ff04
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="toexponential-method-number-javascript"></a>toExponential 메서드(Number)(JavaScript)
지 수 표기법으로 숫자를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
numObj. toExponential([fractionDigits])  
```  
  
## <a name="parameters"></a>매개 변수  
 `numObj`  
 필수 요소. A **번호** 개체입니다.  
  
 `fractionDigits`  
 선택 사항입니다. 소수점 뒤에 자릿수의 수입니다. 0-20 범위에 있어야 합니다.  
  
## <a name="return-value"></a>반환 값  
 지 수 표기법으로 숫자의 문자열 표현을 반환합니다. 문자열 한 자릿수는 소수점 앞 포함 되 고 있을 수 `fractionDigits` 그 뒤의 자릿수입니다.  
  
 경우 `fractionDigits` 제공 되지 않으면는 `toExponential` 메서드 많은 숫자를 고유 하 게 수를 지정 하는 데 필요한 반환 합니다.  
  
## <a name="example"></a>예제  
  
```JavaScript  
var num = new Number(123);  
var exp = num.toExponential();  
document.write(exp);  
document.write("<br/>");  
  
num = new Number(123.456);  
exp = num.toExponential(5);  
document.write(exp);  
  
// Output:   
// 1.23e+2  
// 1.23456e+2  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
 **적용 대상**: [개체 번호](../../javascript/reference/number-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [toFixed 메서드 (Number)](../../javascript/reference/tofixed-method-number-javascript.md)   
 [toPrecision 메서드(Number)](../../javascript/reference/toprecision-method-number-javascript.md)