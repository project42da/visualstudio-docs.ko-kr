---
title: "배열 사용(JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-javascript
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- arrays [JavaScript]
- arrays [JavaScript], objects
ms.assetid: 785c5acd-b8b3-4152-af9a-dd42ecdd75ba
caps.latest.revision: 13
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.translationtype: HT
ms.sourcegitcommit: 47057e9611b824c17077b9127f8d2f8b192d6eb8
ms.openlocfilehash: 4c5218a8353a796128d8b672ecc781665c6bde20
ms.contentlocale: ko-kr
ms.lasthandoff: 08/11/2017

---
# <a name="using-arrays-javascript"></a>배열 사용(JavaScript)
[!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]의 배열은 *스파스*입니다. 즉, 0, 1 및 2로 번호가 지정된 세 개의 요소가 포함된 배열이 있으면 요소 3~49를 고려하지 않으면서 요소 50을 만들 수 있습니다. 배열에 자동 길이 변수(배열 길이 자동 모니터링에 대한 설명은 [내장 개체](../../javascript/intrinsic-objects-javascript.md) 참조)가 있으면 길이 변수는 4가 아니라 51로 설정됩니다. 요소의 번호를 지정할 때 간격이 없는 배열을 만들 수 있지만 필수는 아닙니다.  
  
 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]에서 개체와 배열은 서로 거의 동일합니다. 두 가지 주된 차이점은 비배열 개체에는 자동 길이 속성이 없으며 배열에는 개체의 속성과 메서드가 없다는 것입니다.  
  
## <a name="addressing-arrays"></a>배열 주소 지정  
 다음 예제에 표시된 대로 대괄호([])를 사용하여 배열의 주소를 지정합니다. 대괄호에는 숫자 값이나 정수로 확인되는 식이 포함됩니다.  
  
```JavaScript  
var entryNum = 5;  
  
sample = new Array();  
  
sample[1] = "Maple Street";  
sample[entryNum] = 25;  
  
document.write (sample[1]);  
document.write (" ");  
document.write (sample[entryNum]);  
  
// Output: Maple Street 25  
  
```  
  
## <a name="objects-as-associative-arrays"></a>연관 배열로서의 개체  
 일반적으로 점 연산자 “.”를 사용하여 개체의 속성에 액세스합니다. 예를 들면 다음과 같습니다.  
  
```JavaScript  
myObject.aProperty  
```  
  
 이 경우 속성 이름이 식별자입니다. 인덱스 연산자([])를 사용하여 개체의 속성에도 액세스할 수 있습니다. 이 경우 데이터 값이 문자열과 연결되는 *결합형 배열*로 개체를 취급합니다. 예를 들면 다음과 같습니다.  
  
```JavaScript  
myObject["aProperty"] // Same as above.  
```  
  
 인덱스 연산자는 더 일반적으로 액세스 배열 요소와 연결됩니다. 개체와 함께 사용하는 경우 인덱스는 속성 이름을 나타내는 문자열 리터럴입니다.  
  
 개체 속성에 액세스하는 두 방법 사이에는 중요한 차이점이 있습니다.  
  
1.  식별자(점(.) 구문)와 같이 취급되는 속성 이름은 데이터와 같이 조작할 수 없습니다.  
  
2.  인덱스(대괄호([]) 구문)와 같이 취급되는 속성 이름은 데이터와 같이 조작할 수 있습니다.  
  
 이러한 차이점은 런타임 시까지 속성 이름을 알지 못하는 경우 유용합니다(예: 사용자 입력을 기반으로 개체를 구성하는 경우). 결합형 배열에서 속성을 모두 추출하려면 `for...in` 루프를 사용해야 합니다.
