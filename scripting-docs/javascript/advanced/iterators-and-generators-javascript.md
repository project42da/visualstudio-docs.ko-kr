---
title: "반복기 및 생성기(JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 68ef5b2f-0349-492b-b557-73ff2a2f90cf
caps.latest.revision: "14"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 85c27969609a38b87b15c727e9c8aef89ee77032
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="iterators-and-generators-javascript"></a>반복기 및 생성기(JavaScript)
반복기는 목록처럼 컨테이너 개체를 트래버스하는 데 사용되는 개체입니다. JavaScript에서 반복기 개체는 고유한 기본 제공 개체가 아니라 `next` 메서드를 구현하여 컨테이너 개체의 다음 항목에 액세스하는 개체입니다.  
  
 [!INCLUDE[jsv12text](../../javascript/includes/jsv12text-md.md)]에서는 고유한 사용자 지정 반복기를 만들 수 있습니다. 그러나 일반적으로 반복기 생성을 훨씬 간소화하는 생성기를 사용하는 것이 더 용이합니다. 생성기는 반복기 팩터리인 함수 형식입니다. 생성기 함수를 사용하여 사용자 지정 반복기를 만들려면 [생성기](#Generators)를 참조하세요.  
  
> [!CAUTION]
>  생성기는 [!INCLUDE[jsv12textExp](../../javascript/includes/jsv12textexp-md.md)]에서 지원됩니다.  
  
## <a name="iterators"></a>반복기  
 JavaScript 반복기 구현에는 특정 인터페이스를 준수하는 두 개 또는 세 개의 개체가 포함됩니다.  
  
-   Iterable 인터페이스  
  
-   Iterator 인터페이스  
  
-   IteratorResult 인터페이스  
  
 이러한 인터페이스를 사용하여 사용자 지정 반복기를 만들 수 있습니다. 이렇게 하면 `for…of` 문을 사용하여 반복 가능한 개체를 트래버스할 수 있습니다.  
  
### <a name="iterable-interface"></a>Iterable 인터페이스  
 Iterable 인터페이스는 반복 가능한 개체(반복기를 가져올 수 있는 개체)에 필요한 인터페이스입니다. 예를 들어 `for (let e of C)`의 `C`는 Iterable 인터페이스를 구현해야 합니다.  
  
 반복 가능한 개체는 반복기를 반환하는 Symbol.iterator 메서드를 제공해야 합니다.  
  
```JavaScript  
obj[Symbol.iterator] = function() { return iterObj; }  
```  
  
 이 속성은 인수가 없는 경우를 허용하고 `Iterator` 인터페이스를 준수하는 개체(`iterObject`)를 반환하는 함수여야 합니다.  
  
 이제 배열을 포함하여 많은 기본 제공 형식이 반복 가능합니다. `for…of` 루프는 반복 가능한 개체를 사용합니다. 그러나 기본 제공되는 반복 가능한 개체 중 일부는 반복기가 아닙니다. 예를 들어 Array 개체 자체는 반복기가 아니라 반복 가능한 개체지만 ArrayIterator는 반복 가능한 개체이기도 합니다.  
  
### <a name="iterator-interface"></a>Iterator 인터페이스  
 Symbol.iterator 메서드에서 반환된 개체는 `next` 메서드를 구현해야 합니다. `next` 메서드의 구문은 다음과 같습니다.  
  
```JavaScript  
iterObj.next() = function() { return iterResultObj; };  
```  
  
 `next` 메서드는 값을 반환하는 함수입니다. 함수는 `IteratorResult` 인터페이스를 준수하는 개체(`iterResultObj`)를 반환합니다. 반복기의 `next` 메서드에 대한 이전 호출에서 `done` 속성이 true인 `IteratorResult` 개체가 반환된 경우 반복이 종료되고 `next` 메서드가 다시 호출되지 않습니다.  
  
 스크립트가 작업을 마쳤을 때 반복기가 제대로 삭제되도록 반복기에 `return` 메서드가 포함될 수도 있습니다.  
  
### <a name="iteratorresult-interface"></a>IteratorResult 인터페이스  
 IteratorResult 인터페이스는 반복기에 대한 `next` 메서드의 결과에 필요한 인터페이스입니다. `next`에서 반환된 개체는 `done` 및 `value` 속성을 제공해야 합니다.  
  
```JavaScript  
var iterResultObj = { done: true|false, value: value }  
```  
  
 `done` 속성은 반복기의 `next` 메서드 호출 상태를 true 또는 false로 반환합니다. 반복기의 끝에 도달한 경우 `done`에서 true를 반환합니다. 끝에 도달하지 못한 경우 `done`에서 false를 반환하며 값을 사용할 수 있습니다. `done` 속성(고유한 속성 또는 상속된 속성)이 없는 경우 `done`의 결과가 false로 처리됩니다.  
  
 `done`이 false이면 `value` 속성이 현재 반복 요소 값을 반환합니다. `done`이 true이면 반환 값이 제공된 경우 반복기의 반환 값입니다. 반복기에 반환 값이 없는 경우 `value`가 정의되지 않습니다. 이 경우 명시적 value 속성을 상속하지 않을 경우 준수 개체에 `value` 속성이 없을 수 있습니다.  
  
<a name="Generators"></a>   
## <a name="generators"></a>생성기  
 사용자 지정 반복기를 쉽게 만들고 사용하려면 하나 이상의 `yield` 식과 함께 함수* 구문을 사용하여 생성기 함수를 만듭니다. 생성기 함수는 생성기 함수 본문을 실행할 수 있도록 하는 반복기(즉, 생성기)를 반환합니다. 함수는 다음 `yield` 또는 `return` 문까지 실행됩니다.  
  
 반복기의 `next` 메서드를 호출하여 생성기 함수에서 다음 값을 반환합니다.  
  
 다음 예제에서는 문자열 개체에 대한 반복기를 반환하는 생성기를 보여 줍니다.  
  
```JavaScript  
function* stringIter() {  
    var str = "bobsyouruncle";  
    var idx = 0;  
    while(idx < str.length)  
        yield str[idx++];  
}  
  
var si = stringIter();  
  
console.log(si.next().value);  
console.log(si.next().value);  
console.log(si.next().value);  
  
// Output:  
// b  
// o  
// b  
  
```  
  
 생성기에서 yield 피연산자 식은 `next` 호출을 종료하고 두 속성 `done`(`done=false`) 및 `value`(`value=operand`)가 있는 `IteratorResult` 개체를 반환합니다. `operand`는 선택적이며, 비워 두면 해당 값이 정의되지 않습니다.  
  
 생성기에서 `return` 문은 value 속성에 대한 선택적 피연산자 결과와 함께 `done=true`인 `IteratorResult`를 반환하여 생성기를 종료합니다.  
  
 `yield` 대신 `yield*` 식을 사용하여 다른 생성기나 배열 또는 문자열과 같은 다른 반복 가능한 개체에 위임할 수도 있습니다.  
  
 앞의 예제에 다음 코드를 추가하면 `yield*`가 `stringIter` 생성기에 위임합니다.  
  
```JavaScript  
function* strIter() {  
    yield "jo";  
    yield* stringIter();  
}  
  
var si2 = strIter();  
  
console.log(si2.next().value);  
console.log(si2.next().value);  
console.log(si2.next().value);  
console.log(si2.next().value);  
  
// Output:  
// jo  
// b  
// o  
// b  
```  
  
 `next`에 인수를 전달하고 인수를 통해 생성기의 상태를 수정하여 고급 생성기를 만들 수도 있습니다. `next`는 이전에 실행한 `yield` 식의 결과 값이 됩니다. 다음 예제에서는 `next` 메서드에 값 100을 전달할 때 생성기의 내부 인덱스 값을 다시 설정합니다.  
  
```  
function* strIter() {  
    var str = "jobob";  
    var idx = 0;  
    while(idx , str.length) {  
        var modify = yield str[idx++];  
        if(modify == 100) {  
            idx = 0;  
        }  
    }
}
  
var si3 = strIter();  
  
console.log(si3.next().value);  
console.log(si3.next().value);  
console.log(si3.next().value);  
console.log(si3.next(100).value);  
  
// Output:  
// j  
// o  
// b  
// j  
  
```  
  
 다른 고급 생성기는 생성기의 `throw` 메서드를 호출할 수도 있습니다. 생성기 일시 중지된 지점(다음 `yield` 문 앞)에서 오류가 발생합니다.
