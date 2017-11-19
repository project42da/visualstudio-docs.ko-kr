---
title: "bind 메서드 (Function) (JavaScript) | Microsoft Docs"
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
helpviewer_keywords:
- parameters [JavaScript], bind method
- arguments [JavaScript], bind method
- bind method [JavaScript]
- this keyword [JavaScript], bind method
ms.assetid: 28946f47-b758-48cf-b508-610a0f2f6e19
caps.latest.revision: "21"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: dd7fc752df9bd41f8625ac2cb484486dfd19558d
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="bind-method-function-javascript"></a>bind 메서드(Function)(JavaScript)
지정된 함수에 대해 원본 함수와 동일한 본문을 갖는 바인딩된 함수를 만듭니다. 바운드 함수에서 `this` 개체는 개체에 전달된 것으로 확인됩니다. 바인딩된 함수에는 지정된 초기 매개 변수가 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
function.bind(thisArg[,arg1[,arg2[,argN]]])  
```  
  
#### <a name="parameters"></a>매개 변수  
 `function`  
 필수 요소. 함수 개체입니다.  
  
 `thisArg`  
 필수 요소. `this` 키워드가 새 함수 내에서 참조할 수 있는 개체입니다.  
  
 `arg1`[,`arg2`[,`argN`]]]  
 선택 사항입니다. 새 함수에 전달될 인수 목록입니다.  
  
## <a name="return-value"></a>반환 값  
 `function` 개체 및 초기 인수를 제외하고 `thisArg` 함수와 동일한 새 함수입니다.  
  
## <a name="exceptions"></a>예외  
 지정된 `function`이 함수가 아닌 경우 `TypeError` 예외가 throw됩니다.  
  
## <a name="example"></a>예제  
 다음 코드에서는 `bind` 메서드를 사용하는 방법을 보여 줍니다.  
  
```JavaScript  
// Define the original function.  
var checkNumericRange = function (value) {  
    if (typeof value !== 'number')  
        return false;  
    else  
        return value >= this.minimum && value <= this.maximum;  
}  
  
// The range object will become the this value in the callback function.  
var range = { minimum: 10, maximum: 20 };  
  
// Bind the checkNumericRange function.  
var boundCheckNumericRange = checkNumericRange.bind(range);  
  
// Use the new function to check whether 12 is in the numeric range.  
var result = boundCheckNumericRange (12);  
document.write(result);  
  
// Output: true  
```  
  
## <a name="example"></a>예제  
 다음 예제에서 `thisArg` 개체는 원본 메서드를 포함하는 개체와 다릅니다.  
  
```JavaScript  
// Create an object that contains the original function.  
var originalObject = {  
    minimum: 50,  
    maximum: 100,  
    checkNumericRange: function (value) {  
        if (typeof value !== 'number')  
            return false;  
        else  
            return value >= this.minimum && value <= this.maximum;  
    }  
}  
  
// Check whether 10 is in the numeric range.  
var result = originalObject.checkNumericRange(10);  
document.write(result + " ");  
// Output: false  
  
// The range object supplies the range for the bound function.  
var range = { minimum: 10, maximum: 20 };  
  
// Create a new version of the checkNumericRange function that uses range.  
var boundObjectWithRange = originalObject.checkNumericRange.bind(range);  
  
// Check whether 10 is in the numeric range.  
var result = boundObjectWithRange(10);  
document.write(result);  
// Output: true  
```  
  
## <a name="example"></a>예제  
 다음 코드에서는 `arg1[,arg2[,argN]]]` 인수를 사용하는 방법을 보여줍니다. 바인딩된 함수는 `bind` 메서드에 지정된 매개 변수를 첫 번째 및 두 번째 매개 변수로 사용합니다. 바인딩된 함수를 호출할 때 지정된 모든 매개 변수는 세 번째, 네 번째 등의 매개 변수로 사용됩니다.  
  
```JavaScript  
// Define the original function with four parameters.  
var displayArgs = function (val1, val2, val3, val4) {  
    document.write(val1 + " " + val2 + " " + val3 + " " + val4);  
}  
  
var emptyObject = {};  
  
// Create a new function that uses the 12 and "a" parameters  
// as the first and second parameters.  
var displayArgs2 = displayArgs.bind(emptyObject, 12, "a");  
  
// Call the new function. The "b" and "c" parameters are used  
// as the third and fourth parameters.  
displayArgs2("b", "c");  
// Output: 12 a b c   
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv9](../../javascript/includes/jsv9-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [함수 개체](../../javascript/reference/function-object-javascript.md)   
 [filter 메서드 (Array)](../../javascript/reference/filter-method-array-javascript.md)   
 [Bind 메서드 사용](../../javascript/advanced/using-the-bind-method-javascript.md)   
 [Hilo JavaScript 샘플 응용 프로그램 (Windows 스토어)](http://hilojs.codeplex.com/SourceControl/latest)