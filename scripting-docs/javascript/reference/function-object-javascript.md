---
title: "함수 개체 (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: function
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: Function object
ms.assetid: d3834767-203c-475e-848c-95c423ba15b6
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4392fd57967e6312c96af50bdff2415d0f2dcd4d
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="function-object-javascript"></a>Function 개체(JavaScript)
새 함수를 만듭니다.  
  
## <a name="syntax"></a>구문  
  
```  
function functionName([argname1  [, ...[, argnameN]]])  
{  
   body  
}  
```  
  
## <a name="syntax"></a>구문  
  
```  
  
functionName = new Function( [argname1,  [... argnameN,]] body );  
```  
  
## <a name="parameters"></a>매개 변수  
 `functionName`  
 필수 요소. 새로 만든된 함수 이름  
  
 `argname1...argnameN`  
 선택 사항입니다. 함수가 허용 하는 인수 목록입니다.  
  
 `body`  
 선택 사항입니다. 블록을 포함 하는 문자열 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 함수를 호출할 때 실행 되는 코드입니다.  
  
## <a name="remarks"></a>설명  
 함수에서 기본 데이터 형식이 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]합니다. 구문 1 값을 만들고 함수는 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 변환는 `Function` 필요한 경우 개체입니다. [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]변환 `Function` 함수를 호출할 때 함수 값으로 구문 2에 의해 생성 된 개체입니다.  
  
 구문 1은에 새 함수를 만들 수는 표준 방법 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]합니다. 2 구문은 함수 개체를 명시적으로 만드는 데 사용 되는 대체 양식입니다.  
  
 예를 들어, 전달 된 두 개의 인수를 추가 하는 함수를 선언 하려면 두 가지 방법 중 하나로 수행할 수 있습니다.  
  
## <a name="example-1"></a>예제 1  
  
```JavaScript  
function add(x, y)  
{  
   return(x + y);  
}  
```  
  
## <a name="example-2"></a>예제 2  
  
```  
var add = function(x, y) {  
     return(x+y);  
}  
```  
  
 두 경우 모두 함수를 호출 하는 줄의 코드로 다음과 유사한:  
  
```JavaScript  
add(2, 3);  
```  
  
> [!NOTE]
>  함수를 호출 하는 경우 포함 하는 항상 괄호와 모든 필수 인수 있는지 확인 합니다. 괄호 없이 함수를 호출 하면 함수 자체는 함수의 반환 값 대신 반환 됩니다.  
  
## <a name="properties"></a>속성  
 [0... n 속성](../../javascript/reference/0-dot-dot-dot-n-properties-arguments-javascript.md) &#124;[ 인수 속성](../../javascript/reference/arguments-property-function-javascript.md) &#124; [callee 속성](../../javascript/reference/callee-property-arguments-javascript.md) &#124; [호출자 속성](../../javascript/reference/caller-property-function-javascript.md) &#124; [생성자 속성](../../javascript/reference/constructor-property-object-javascript.md) &#124; [length 속성 (Function)](../../javascript/reference/length-property-function-javascript.md) &#124; [prototype 속성](../../javascript/reference/prototype-property-object-javascript.md)  
  
## <a name="methods"></a>메서드  
 [apply 메서드](../../javascript/reference/apply-method-function-javascript.md) &#124; [bind 메서드](../../javascript/reference/bind-method-function-javascript.md) &#124; [메서드를 호출](../../javascript/reference/call-method-function-javascript.md) &#124; [toString 메서드](../../javascript/reference/tostring-method-object-javascript.md) &#124; [valueOf 메서드](../../javascript/reference/valueof-method-object-javascript.md)  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [function 문](../../javascript/reference/function-statement-javascript.md)   
 [new 연산자](../../javascript/reference/new-operator-decrementjavascript.md)   
 [var 문](../../javascript/reference/var-statement-javascript.md)