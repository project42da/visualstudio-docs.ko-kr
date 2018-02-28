---
title: "return 문 (JavaScript) | Microsoft Docs"
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
- return_JavaScriptKeyword
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- terminating execution
- return statement
- function statement
- return statement, syntax
- return statement, exiting functions in script
ms.assetid: a9130d90-11fb-43f5-a819-7e5435f74c05
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2c28f17bed2dfff021ea1aea268bb7a2eb3f3e58
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="return-statement-javascript"></a>return 문(JavaScript)
현재 함수를 종료하고 해당 함수에서 값을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
return[(][expression][)];   
```  
  
## <a name="remarks"></a>설명  
 선택적 *식* 인수는 함수에서 반환 될 값입니다. 생략 하는 경우 함수는 값을 반환 하지 않습니다.  
  
 사용 된 `return` 함수의 실행을 중지 하 고 값을 반환 하는 문을 *식*합니다. 경우 *식* 를 생략 하면 없거나 `return` 함수 내에서 문이 실행 되 고, 현재 함수를 호출 하는 식을 정의 되지 않은 값이 할당 됩니다.  
  
## <a name="example"></a>예제  
 다음 예제는 `return` 문의 사용 예를 보여줍니다.  
  
```JavaScript  
function myfunction(arg1, arg2){  
   var r;  
   r = arg1 * arg2;  
   return(r);  
}  
```  
  
## <a name="example"></a>예제  
 다음 예제에서는 `return` 함수를 반환 하는 문입니다.  
  
```JavaScript  
function doWork() {  
    return function calculate(y) { return y + 1; };  
}  
  
var func = doWork();  
var x = func(5);  
document.write(x);  
  
// Output: 6  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [function 문](../../javascript/reference/function-statement-javascript.md)