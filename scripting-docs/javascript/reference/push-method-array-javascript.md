---
title: "push 메서드 (Array) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: push
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: Push method
ms.assetid: fa6e5799-dabe-4b3d-bd1f-0afc68c77134
caps.latest.revision: "15"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ddb49f310eaff51fe9e9ba584281fdf07bc2e818
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="push-method-array-javascript"></a>push 메서드(Array)(JavaScript)
배열에 새 요소를 추가하고 배열의 새 길이를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
arrayObj.push([item1 [item2 [. . . [itemN ]]]])  
```  
  
## <a name="parameters"></a>매개 변수  
 `arrayObj`  
 필수 요소. `Array` 개체입니다.  
  
 `item, item2,. . ., itemN`  
 선택 사항입니다. 새 요소는 `Array`합니다.  
  
## <a name="remarks"></a>설명  
 `push` 및 `pop` 메서드를 사용 하면 스택 아웃 먼저,에서 마지막을 시뮬레이션할 수 있습니다.  
  
 `push` 메서드는 요소는 순서 대로 추가 합니다. 인수 중 하나가 배열인 경우 단일 요소로 추가 됩니다. 사용 된 `concat` 메서드를 둘 이상의 배열에서 요소를 결합 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `push` 메서드를 사용하는 방법을 보여 줍니다.  
  
```JavaScript  
var number;  
var my_array = new Array();  
  
my_array.push (5, 6, 7);  
my_array.push (8, 9);  
  
number = my_array.pop();  
while (number != undefined)  
   {  
   document.write (number + " ");  
   number = my_array.pop();  
   }  
  
// Output:  
// 9 8 7 6 5  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [concat 메서드 (Array)](../../javascript/reference/concat-method-array-javascript.md)   
 [pop 메서드(Array)](../../javascript/reference/pop-method-array-javascript.md)