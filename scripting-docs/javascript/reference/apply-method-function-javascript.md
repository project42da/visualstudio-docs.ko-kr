---
title: "apply 메서드 (Function) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: apply
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: Apply method
ms.assetid: b36df78e-b14b-46ca-b5cb-de752d80f40a
caps.latest.revision: "10"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5a06a37006937b07214bf5a314d5151c3b658acf
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="apply-method-function-javascript"></a>apply 메서드(Function)(JavaScript)
에 대 한 지정된 된 개체를 대체 하는 함수를 호출 하는 `this` 함수와 함수의 인수에 대 한 지정된 된 배열의의 값입니다.  
  
## <a name="syntax"></a>구문  
  
```  
apply([thisObj[,argArray]])  
```  
  
## <a name="parameters"></a>매개 변수  
 `thisObj`  
 선택 사항입니다. 로 사용할 개체는 `this` 개체입니다.  
  
 `argArray`  
 선택 사항입니다. 집합 함수에 전달할 인수입니다.  
  
## <a name="remarks"></a>설명  
 경우 `argArray` "개체가 필요 합니다." 오류가 발생 한 다음, 유효한 개체가 아닙니다.  
  
 모두 `argArray` 또는 `thisObj` 를 제공 하는 원래 `this` 으로 개체를 사용 `thisObj` 인수가 전달 됩니다.  
  
## <a name="example"></a>예제  
 다음 코드에는 적용 메서드를 사용 하는 방법을 보여 줍니다.  
  
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
  
document.write("Function called with apply: <br/>");  
document.write(callMe.apply(3, [ 4, 5 ]));  
  
// Output:   
// Original function:   
// this value: [object Window]  
// arguments: 1  
// arguments: 2  
  
// Function called with apply:   
// this value: 3  
// arguments: 4  
// arguments: 5  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [Function 개체](../../javascript/reference/function-object-javascript.md)