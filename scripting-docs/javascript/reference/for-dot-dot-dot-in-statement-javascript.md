---
title: ">for.. 문 (JavaScript)에서 | Microsoft Docs"
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
- iteration statements, for...in statement
- loop structures, for...in statements
ms.assetid: 1b51a0ce-89f7-4a69-88ed-017b47dc398f
caps.latest.revision: "20"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: a9c3ce78def6ab91256ff724a4acc87b7cf19ba2
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="forin-statement-javascript"></a>for...in 문(JavaScript)
개체의 각 속성 또는 배열의 각 요소에 대 한 하나 이상의 문을 실행합니다.  
  
## <a name="syntax"></a>구문  
  
```  
for (variable in [object | array]) {  
    statements   
}  
```  
  
## <a name="parameters"></a>매개 변수  
 `variable`  
 필수 요소. 모든 속성 이름이 될 수 있는 변수 `object` 또는의 모든 요소 인덱스는 `array`합니다.  
  
 `object`, `array`  
 선택 사항입니다. 반복 하는 배열 또는 개체입니다.  
  
 `statements`  
 선택 사항입니다. 각 속성에 대해 실행할 하나 이상의 문을 `object` 의 각 요소 또는 `array`합니다. 복합 문일 수 있습니다.  
  
## <a name="remarks"></a>설명  
 루프의 값의 각 반복의 시작 부분에서 `variable` 의 다음 속성 이름 `object` 또는의 다음 요소 인덱스 `array`합니다. 사용할 수 있습니다 `variable` 의 속성을 참조 하는 루프 내의 문 중 하나에서 `object` 의 요소 또는 `array`합니다.  
  
 개체의 속성 확정적 방식으로 할당 되지 않습니다. 속성의 이름에 의해서만 해당 인덱스로 특정 속성을 지정할 수 없습니다.  
  
 배열을 통해 반복 하는 0, 1, 2, 즉 요소 순서에서 수행 됩니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `for...in` 결합형 배열로 사용 되는 개체를 사용 하 여 문을 합니다.  
  
```JavaScript  
// Initialize object.  
a = {"a" : "Athens" , "b" : "Belgrade", "c" : "Cairo"}  
  
// Iterate over the properties.  
var s = ""  
for (var key in a) {  
    s += key + ": " + a[key];  
    s += "<br />";  
    }  
document.write (s);  
  
// Output:  
// a: Athens  
// b: Belgrade  
// c: Cairo  
```  
  
## <a name="example"></a>예제  
 이 예제에서는 `for ... in` 을 반복 하는 문에 `Array` expando 속성을 가진 개체를 합니다.  
  
```JavaScript  
// Initialize the array.  
var arr = new Array("zero","one","two");  
  
// Add a few expando properties to the array.  
arr["orange"] = "fruit";  
arr["carrot"] = "vegetable";  
  
// Iterate over the properties and elements.  
var s = "";  
for (var key in arr) {  
    s += key + ": " + arr[key];  
    s += "<br />";  
}  
  
document.write (s);  
  
// Output:  
//   0: zero  
//   1: one  
//   2: two  
//   orange: fruit  
//   carrot: vegetable  
```  
  
> [!NOTE]
>  사용 된 `Enumerator` 컬렉션의 멤버에 대해 반복 하는 개체입니다.  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv5](../../javascript/reference/includes/jsv5-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [for 문](../../javascript/reference/for-statement-javascript.md)   
 [while 문](../../javascript/reference/while-statement-javascript.md)