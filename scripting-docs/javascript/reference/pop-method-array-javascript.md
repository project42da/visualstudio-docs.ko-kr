---
title: "pop 메서드 (Array) (JavaScript) | Microsoft Docs"
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
- pop
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Pop method
ms.assetid: 4fae7f98-29f1-4041-ba43-601f2e5145ec
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f7635ddcc1b3d336f5e3de66e62714bd93a06158
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="pop-method-array-javascript"></a>pop 메서드(Array)(JavaScript)
배열의 마지막 요소를 제거하여 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
arrayObj.pop( )  
```  
  
## <a name="remarks"></a>설명  
 [푸시](../../javascript/reference/push-method-array-javascript.md) 및 `pop` 메서드를 사용 (LIFO) 데이터를 저장할 아웃 먼저 마지막으로 원칙을 사용 하 여 스택을 시뮬레이션할 수 있습니다.  
  
 필요한 `arrayObj` 참조가 `Array` 개체입니다.  
  
 배열이 비어 있는 경우 `undefined` 반환 됩니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `pop` 메서드를 사용하는 방법을 보여 줍니다.  
  
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
  
// Output: 9 8 7 6 5  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [push 메서드(Array)](../../javascript/reference/push-method-array-javascript.md)