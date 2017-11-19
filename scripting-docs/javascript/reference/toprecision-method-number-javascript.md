---
title: "toPrecision 메서드 (Number) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: toPrecision
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: toPrecision method
ms.assetid: ac13c82f-1038-447a-823f-f755bba535ca
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: eeab7642dcd88677d1b5a7102e3cf342d7ee1d29
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="toprecision-method-number-javascript"></a>toPrecision 메서드(Number)(JavaScript)
지 수 또는 고정 소수점 표기법으로 숫자의 지정 된 번호로 하거나 숫자를 나타냅니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
numObj.toPrecision([precision])  
```  
  
## <a name="parameters"></a>매개 변수  
 `numObj`  
 필수 요소. `Number` 개체입니다.  
  
 `precision`  
 선택 사항입니다. 유효 자릿수 범위는 1-21 (포함)에 있어야 합니다.  
  
## <a name="return-value"></a>반환 값  
 지 수 표기법으로 숫자에 대 한 `precision` -1 자릿수는 소수점 뒤에 반환 됩니다. 고정된 표기법으로 나타낸 숫자 `precision` 유효 자릿수가 반환 됩니다.  
  
 경우 `precision` 되었거나 제공 되지 않으면 **정의 되지 않은**, **toString** 메서드 대신 호출 됩니다.  
  
## <a name="example"></a>예제  
 다음 코드를 사용 하는 방법을 보여 줍니다 `toPrecision`합니다.  
  
```JavaScript  
var num = new Number(123);  
var prec = num.toPrecision();  
document.write(prec);  
document.write("<br/>");  
  
num = new Number(123.456);  
prec = num.toPrecision(5);  
document.write(prec);  
  
// Output:  
// 123  
// 123.46  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
 **적용 대상**: [개체 번호](../../javascript/reference/number-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [toFixed 메서드 (Number)](../../javascript/reference/tofixed-method-number-javascript.md)   
 [toExponential 메서드(Number)](../../javascript/reference/toexponential-method-number-javascript.md)