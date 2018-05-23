---
title: '>for.. 문 (JavaScript)의 | Microsoft Docs'
ms.custom: ''
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: ''
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 7872b0b2-5701-4d72-9b52-ed13991542cc
caps.latest.revision: 4
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2373d319347f927304c32cb47856405a1d69a6b2
ms.sourcegitcommit: b400528a83bea06d208d95c77282631ae4a93091
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/23/2018
---
# <a name="forof-statement-javascript"></a>for...of 문(JavaScript)
반복 가능한 개체에서 가져온 반복기의 각 값에 대해 하나 이상의 문을 실행합니다.  
  
## <a name="syntax"></a>구문  
  
```  
for (variable of object) {  
    statements   
}  
```  
  
## <a name="parameters"></a>매개 변수  
 `variable`  
 필수. `object`의 임의 속성 값일 수 있는 변수입니다.  
  
 `object`  
 필수. 와 같은 반복 가능한 개체는 `Array`, `Map`, `Set`, 또는 구현 하는 개체는 [반복기 인터페이스](../../javascript/advanced/iterators-and-generators-javascript.md)합니다.  
  
 `statements`  
 선택 사항입니다. `object`의 각 값에 대해 실행할 하나 이상의 문입니다. 복합 문일 수 있습니다.  
  
## <a name="remarks"></a>설명  
 루프의 각 반복을 시작할 때 `variable`의 값은 `object`의 다음 속성 값이 됩니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 배열에서 `for...of` 문을 사용하는 방법을 보여 줍니다.  
  
```JavaScript  
let arr = [ "fred", "tom", "bob" ];  
  
for (let i of arr) {  
    console.log(i);  
}  
  
// Output:  
// fred  
// tom  
// bob  
  
```  
  
## <a name="example"></a>예제  
 다음 예제에서는 `Map` 개체에서 `for...of` 문을 사용하는 방법을 보여 줍니다.  
  
```JavaScript  
var m = new Map();  
m.set(1, "black");  
m.set(2, "red");  
  
for (var n of m) {  
  console.log(n);  
}  
  
// Output:  
// 1,black  
// 2,red  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [>for.. 문에서](../../javascript/reference/for-dot-dot-dot-in-statement-javascript.md)   
 [for 문](../../javascript/reference/for-statement-javascript.md)   
 [while 문](../../javascript/reference/while-statement-javascript.md)