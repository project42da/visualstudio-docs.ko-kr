---
title: "call 메서드 (Function) (JavaScript) | Microsoft Docs"
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
- call
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- call method
ms.assetid: fa356dec-48e6-4f75-8bf3-c1814a76818f
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2ef871f85459ad875a747ae79c7c054b30a82e55
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="call-method-function-javascript"></a>call 메서드(Function)(JavaScript)
현재 개체에 대 한 다른 개체를 대체 하는 개체의 메서드를 호출 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
call([thisObj[, arg1[, arg2[,  [, argN]]]]])  
```  
  
## <a name="parameters"></a>매개 변수  
 `thisObj`  
 선택 사항입니다. 현재 개체와 사용할 개체입니다.  
  
 `arg1, arg2, , argN`  
 선택 사항입니다. 메서드에 전달 될 인수 목록입니다.  
  
## <a name="remarks"></a>설명  
 `call` 메서드를 호출 하는 다른 개체를 대신 하 여 메서드를 사용 합니다. 변경할 수 있습니다는 `this` 개체에서 지정한 새 개체를 원래 컨텍스트에서 함수의 `thisObj`합니다.  
  
 경우 `thisObj` 제공 되지 않으면는 `global` 되 `thisObj`합니다.  
  
## <a name="example"></a>예제  
 다음 코드에서는 `call` 메서드를 사용하는 방법을 보여 줍니다.  
  
```JavaScript  
function callMe(arg1, arg2){  
    var s = "";  
  
    s += "this value: " + this;  
    s += "<br />";  
    for (i in callMe.arguments) {  
        s += "arguments: " + callMe.arguments[i];  
        s += "<br />";  
    }  
    return s;  
}  
  
document.write("Original function: <br/>");  
document.write(callMe(1, 2));  
document.write("<br/>");  
  
document.write("Function called with call: <br/>");  
document.write(callMe.call(3, 4, 5));  
  
// Output:   
// Original function:   
// this value: [object Window]  
// arguments: 1  
// arguments: 2  
  
// Function called with call:   
// this value: 3  
// arguments: 4  
// arguments: 5  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [함수 개체](../../javascript/reference/function-object-javascript.md)   
 [apply 메서드(Function)](../../javascript/reference/apply-method-function-javascript.md)