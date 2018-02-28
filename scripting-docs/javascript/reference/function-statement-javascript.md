---
title: "함수 문 (JavaScript) | Microsoft Docs"
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
- function_JavaScriptKeyword
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- new operator
- declaring functions, syntax
- function statement
- declaring functions
ms.assetid: cc9cfd43-1305-41c8-ad67-545d20f4fafe
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e5fac3647e9374a9c909a420b73b86354cac69b6
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="function-statement-javascript"></a>function 문(JavaScript)
새 함수를 선언합니다.  
  
## <a name="syntax"></a>구문  
  
```  
function functionname ([arg1 [, arg2 [,...[, argN]]]]) {  
    statements  
}   
```  
  
## <a name="parameters"></a>매개 변수  
 `functionname`  
 필수 요소. 함수의 이름.  
  
 `arg1...argN`  
 선택 사항입니다. 함수가 인식하는 선택적, 쉼표로 구분된 인수 목록입니다.  
  
 `statements`  
 선택 사항입니다. 하나 이상의[!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 문.  
  
## <a name="remarks"></a>설명  
 사용 하 여는 `function` 문을 나중에 사용할 함수를 선언 합니다. 에 포함 된 코드 `statements` 스크립트의 다른 곳에서 함수를 호출할 때까지 실행 되지 않습니다.  
  
 [반환](../../javascript/reference/return-statement-javascript.md) 문을 사용 하는 함수에서 값을 반환 합니다. 사용할 필요가 없습니다는 `return` 문; 프로그램은 함수의 끝에 도달 하면를 반환 합니다. 없는 경우 `return` 함수에서 문이 실행 될 경우는 `return` 문에 식, 함수 반환 값 `undefined`합니다.  
  
> [!NOTE]
>  함수를 호출 하는 경우 괄호와 모든 필수 인수를 포함 해야 합니다. 괄호 없이 함수를 호출 하는 함수의 결과가 아니라 함수에 대 한 참조를 반환 합니다.  
  
## <a name="example"></a>예제  
 다음 예제는 `function` 문의 사용 예를 보여줍니다.  
  
```JavaScript  
function myfunction (arg1, arg2) {  
    var r = arg1 * arg2;  
    return(r);  
}  
```  
  
## <a name="example"></a>예제  
 함수를 변수에 할당할 수 있습니다. 이런 내용은 다음 예에서 설명되어 있습니다.  
  
```JavaScript  
function AddFive(x) {  
    return x + 5;  
}  
  
function AddTen(x) {  
    return x + 10;  
}  
  
var condition = false;  
  
var MyFunc;  
if (condition) {  
    MyFunc = AddFive;  
}  
else {  
    MyFunc = AddTen;  
}  
  
var result = MyFunc(123);  
// Output: 133  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [new 연산자](../../javascript/reference/new-operator-decrementjavascript.md)