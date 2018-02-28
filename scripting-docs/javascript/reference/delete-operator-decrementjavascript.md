---
title: "delete 연산자 (JavaScript) | Microsoft Docs"
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
- delete_JavaScriptKeyword
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- array elements, deleting
- properties, deleting
- delete operator
ms.assetid: 55c6487e-96ea-455b-a7ed-dc35c41ac2f3
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ee3def1977c0b29ee14ebf836f2d9ebb51d5a5ef
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="delete-operator-javascript"></a>delete 연산자(JavaScript)
개체에서 속성을 삭제하거나 배열에서 요소를 제거합니다.  
  
## <a name="syntax"></a>구문  
  
```  
delete expression  
```  
  
## <a name="remarks"></a>설명  
 `expression` 인수는 유효한 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 속성 이름 또는 배열 요소에 있는 식의 결과입니다.  
  
 하는 경우의 결과 `expression` 은 개체에 지정 된 속성이 `expression` 있는 경우, 개체에서 삭제 될 수 없습니다 `false` 반환 됩니다.  
  
 다른 모든 경우에 `true` 반환 됩니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 배열에서 요소를 제거 하는 방법을 보여 줍니다.  
  
```JavaScript  
// Create an array.  
var ar = new Array (10, 11, 12, 13, 14);  
  
// Remove an element from the array.  
delete ar[1];  
  
// Print the results.  
document.write ("element 1: " + ar[1]);  
document.write ("<br />");  
document.write ("array: " + ar);  
// Output:  
//  element 1: undefined  
//  array: 10,,12,13,14  
```  
  
## <a name="example"></a>예제  
 다음 예제에서는 개체에서 속성을 삭제 하는 방법을 보여 줍니다.  
  
```JavaScript  
// Create an object and add expando properties.  
var myObj = new Object();  
myObj.name = "Fred";  
myObj.count = 42;  
  
// Delete the properties from the object.  
delete myObj.name;  
delete myObj["count"];  
  
// Print the results.  
document.write ("name: " + myObj.name);  
document.write ("<br />");  
document.write ("count: " + myObj.count);  
// Output:  
//  name: undefined  
//  count: undefined  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [연산자 우선 순위](../../javascript/operator-subtractprecedence-javascript.md)   
 [연산자 개요(JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)