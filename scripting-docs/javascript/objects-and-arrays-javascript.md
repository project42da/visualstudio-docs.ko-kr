---
title: "Object 및 Array(JavaScript) | Microsoft Docs"
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
helpviewer_keywords:
- arrays [JavaScript]
- arrays [JavaScript], objects
ms.assetid: f5106284-1240-4f47-8c3b-5a45e227e5e1
caps.latest.revision: "15"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 6776701ba108ae0ecefc2331c2b12272e0c1be19
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="objects-and-arrays-javascript"></a>Object 및 Array(JavaScript)
[!INCLUDE[javascript](../javascript/includes/javascript-md.md)] 개체는 속성과 메서드의 컬렉션입니다. 메서드는 개체의 한 멤버인 함수입니다. 속성은 개체의 멤버이며 배열이나 개체 형식의 값 또는 값 집합입니다. [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]에서는 네 가지 종류의 개체를 지원합니다.  
  
-   `Array` 및 `String` 같은 내장 개체입니다.  
  
-   만드는 개체입니다.  
  
-   `window` 및 `document` 같은 호스트 개체입니다.  
  
-   ActiveX 개체  
  
## <a name="expando-properties-and-methods"></a>Expando 속성 및 메서드  
 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]의 모든 개체는 런타임에 추가 및 제거할 수 있는 expando 속성과 메서드를 지원합니다. 이 속성과 메서드는 아무 이름이나 지정할 수 있으며 숫자로 식별할 수 있습니다. 속성 또는 메서드 이름이 간단한 식별자인 경우 다음 코드의 `myObj.name`, `myObj.age` 및 `myObj.getAge`와 같이 개체 이름 뒤에 마침표를 쓰면 됩니다.  
  
```JavaScript  
var myObj = new Object();  
myObj.name = "Fred";  
myObj.age = 42;  
  
myObj.getAge =   
    function () {  
        return this.age;  
    };  
  
document.write(myObj.name);  
document.write("<br/>");  
document.write(myObj.age);  
document.write("<br/>");  
document.write(myObj.getAge());  
  
// Output:  
// Fred  
// 42  
// 42  
  
```  
  
 속성 또는 메서드 이름이 간단한 식별자가 아니거나 스크립트를 작성할 때 알려져 있지 않은 경우 대괄호 안에 식을 사용하여 속성을 인덱싱할 수 있습니다. [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]에 있는 모든 expando 속성의 이름은 문자열로 변환되어 개체에 추가됩니다.  
  
```JavaScript  
var myObj = new Object();  
  
// Add two expando properties that cannot be written in the  
// object.property syntax.  
// The first contains invalid characters (spaces), so must be  
// written inside square brackets.  
myObj["not a valid identifier"] = "This is the property value";  
  
// The second expando name is a number, so it also must  
// be placed inside square brackets  
myObj[100] = "100";  
```  
  
 정의에서 개체를 만드는 방법에 대한 자세한 내용은 [개체 만들기](../javascript/creating-objects-javascript.md)를 참조하세요.  
  
## <a name="arrays-as-objects"></a>개체 형식 배열  
 배열은 단순히 개체의 특수한 한 종류일 뿐이므로 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]에서 개체와 배열은 거의 동일하게 처리됩니다. 두 개체와 배열에는 속성과 메서드가 모두 있을 수 있습니다.  
  
 배열에는 `length` 속성이 있지만 개체에는 없습니다. 인덱스의 길이보다 큰 배열의 요소에 값을 할당하면(예: `myArray[100] = "hello"`) `length` 속성이 새 길이에 자동으로 더해집니다. 마찬가지로 `length` 속성을 더 작게 만드는 경우 인덱스가 배열의 범위를 벗어나는 요소는 삭제됩니다.  
  
```JavaScript  
// An array with three elements  
var myArray = new Array(3);  
  
// Add some data  
myArray[0] = "Hello";  
myArray[1] = 42;  
myArray[2] = new Date(2000, 1, 1);  
  
document.write("original length is: " + myArray.length);  
document.write("<br/>");  
// Add some expando properties  
myArray.expando = "JavaScript!";  
myArray["another Expando"] = "Windows";  
  
// This will still display 3, since the two expando properties  
// don't affect the length.  
document.write("new length is : " + myArray.length);  
  
// Output:  
// original length is: 3  
// new length is : 3  
  
```  
  
 배열은 멤버를 반복하고 조작하는 메서드를 제공합니다. 다음 예제에서는 배열로 저장된 개체들의 속성을 얻는 방법을 보여 줍니다.  
  
```JavaScript  
var myArray = new Array(3);  
  
// Add some data  
for(var i = 1; i <= 3; i++) {  
    myArray[i] = new Date(2000 + i, 1, 1);  
}  
  
myArray.forEach(function (item) {  
    document.write(item.getFullYear());  
});  
  
// Output:  
// 2001  
// 2002  
// 2003  
```  
  
## <a name="multi-dimensional-arrays"></a>다차원 배열  
 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)]는 다차원 배열을 직접 지원하지 않지만 다른 배열의 요소 내부에 배열을 저장하여 다차원 배열의 동작을 가져올 수 있습니다. 다른 배열을 비롯한 모든 종류의 데이터를 배열 요소 내부에 저장할 수 있습니다. 예를 들어, 다음 코드는 5까지의 숫자에 대해 곱셈표를 작성합니다.  
  
```JavaScript  
// The size of the table.  
var iMaxNum = 5;  
// Loop counters.  
var i, j;  
  
// Set the length of the array to iMaxNum + 1.   
// The first array index is zero, not 1.  
var MultiplicationTable = new Array(iMaxNum + 1);  
  
// Loop for each major number (each row in the table)  
for (i = 1; i <= iMaxNum; i++)  
{  
    // Create the columns in the table  
    MultiplicationTable[i] = new Array(iMaxNum + 1);  
  
    // Fill the row with the results of the multiplication  
    for (j = 1; j <= iMaxNum; j++)  
    {  
        MultiplicationTable[i][j] = i * j;  
    }  
}  
  
document.write(MultiplicationTable[3][4]);  
document.write("<br/>");   
document.write(MultiplicationTable[5][2]);  
document.write("<br/>");  
document.write(MultiplicationTable[1][4]);  
  
// Output:  
// 12  
// 10  
// 4  
  
```