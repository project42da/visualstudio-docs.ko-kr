---
title: "Object.assign 함수 (Object) (JavaScript) | Microsoft Docs"
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
ms.assetid: 2dd6b312-dcd3-414e-8d53-088c6341c46d
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: c156369299e58eac556d43a87476de2ce09173e1
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="objectassign-function-object-javascript"></a>Object.assign 함수(Object)(JavaScript)
하나 이상의 소스 개체에서 대상 개체로 값을 복사합니다.  
  
## <a name="syntax"></a>구문  
  
```  
Object.assign(target, ...sources );  
```  
  
#### <a name="parameters"></a>매개 변수  
 `target`  
 필수 요소. 열거 가능한 속성이 복사되는 대상 개체입니다.  
  
 `...sources`  
 필수 요소. 열거 가능한 속성이 복사되는 하나 이상의 소스 개체입니다.  
  
## <a name="exceptions"></a>예외  
 복사 작업을 종료하는 할당 오류가 있는 경우 이 함수에서 `TypeError`가 발생합니다. 대상 속성을 쓸 수 없는 경우 `TypeError`가 발생합니다.  
  
## <a name="remarks"></a>설명  
 이 함수는 대상 개체를 반환합니다. 만 *열거 가능한 자체* 대상 개체에 소스 개체에서 속성을 복사 합니다. 이 함수를 사용하여 개체를 병합하거나 복제할 수 있습니다.  
  
 `null` 또는 `undefined` 소스는 빈 개체처럼 처리되며 대상 개체에 아무 영향도 주지 않습니다.  
  
## <a name="example"></a>예제  
 다음 코드 예제에서는 `Object.assign`을 사용하여 개체를 병합하는 방법을 보여 줍니다.  
  
```JavaScript  
var first = { name: "Bob" };  
var last = { lastName: "Smith" };  
  
var person = Object.assign(first, last);  
console.log(person);  
  
// Output:  
// { name: "Bob", lastName: "Smith" }   
```  
  
## <a name="example"></a>예제  
 다음 예제에서는 `Object.assign`을 사용하여 개체를 복제하는 방법을 보여 줍니다.  
  
```JavaScript  
var obj = { person: "Bob Smith"};  
var clone = Object.assign({}, obj);  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]