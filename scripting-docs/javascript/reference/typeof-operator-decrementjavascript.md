---
title: typeof 연산자 (JavaScript) | Microsoft Docs
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: language-reference
f1_keywords:
- typeof_JavaScriptKeyword
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- typeof operator
ms.assetid: ee8a1036-119f-486f-b034-b07bdba87f0c
caps.latest.revision: 11
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a9ff8c7942c773d138dd599956c41d1e583e6288
ms.sourcegitcommit: e01ccb5ca4504a327d54f33589911f5d8be9c35c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 03/15/2018
---
# <a name="typeof-operator-javascript"></a>typeof 연산자(JavaScript)
식의 데이터 형식을 식별하는 문자열을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
typeof[(]expression[)] ;  
```  
  
## <a name="remarks"></a>설명  
 *식* 인수는 형식에 대 한 정보를 찾는 식입니다.  
  
 `typeof` 연산자는 문자열 형식 정보를 반환 합니다. 7 개의 가능한 값 하는 `typeof` 반환: "number" "문자열" "부울", "개체" "작동" "undefined"을 "unknown"입니다.  
  
 괄호는에서 선택적 요소는 `typeof` 구문입니다.  

 개체는 XMLHTTPRequest에서 알 수 없는 형식으로 반환할 수 있습니다. 알 수 없는 형식으로 포함 된 javascript에서 없는 아날로그 COM 개체를 반환할 수도 있습니다.
  
## <a name="example"></a>예  
 다음 예제에서는 데이터 형식의 변수를 테스트합니다.  
  
```JavaScript  
var index = 5;  
var result = (typeof index === 'number');  
// Output: true  
  
var description = "abc";  
var result = (typeof description === 'string');  
// Output: true  
```  
  
## <a name="example"></a>예  
 다음 예제에서는의 데이터 형식에 대 한 테스트 `undefined` 선언 및 선언 되지 않은 변수에 대 한 합니다.  
  
```JavaScript  
var declared;  
var result = (declared === undefined);  
// Output: true  
  
var result = (typeof declared === 'undefined');  
// Output: true  
  
var result = (typeof notDeclared === 'undefined')  
// Output: true  
  
var obj = {};  
var result = (typeof obj.propNotDeclared === 'undefined');  
// Output: true  
  
// An undeclared variable cannot be used in a comparison without  
// the typeof operator, so the next line generates an error.  
//  var result = (notDeclared === undefined);  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [Array.isArray 함수](../../javascript/reference/array-isarray-function-javascript.md)   
 [Object.getPrototypeOf 함수](../../javascript/reference/object-getprototypeof-function-javascript.md)   
 [undefined 상수](../../javascript/reference/undefined-constant-javascript.md)   
 [비교 연산자](../../javascript/reference/comparison-operators-javascript.md)   
 [데이터 형식](../../javascript/data-types-javascript.md)   
 [연산자 우선 순위](../../javascript/operator-subtractprecedence-javascript.md)   
 [연산자 개요(JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)