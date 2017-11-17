---
title: "findIndex 메서드 (Array) (JavaScript) | Microsoft Docs"
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
ms.assetid: 3a200cf0-db67-4c7b-89f8-5e9f5dc1a926
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5c8da475b776e1c04e4fe5bfc7062318cfec952c
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="findindex-method-array-javascript"></a>findIndex 메서드(Array)(JavaScript)
호출 함수에 지정된 테스트 조건을 충족하는 첫 번째 배열 요소의 인덱스 값을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
arrayObj.findIndex(callbackfn [, thisArg]);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `arrayObj`  
 필수 요소. Array 개체입니다.  
  
 `callbackfn`  
 필수 요소. 배열의 각 요소를 테스트하는 호출 함수입니다.  
  
 `thisArg`  
 선택 사항입니다. 호출 함수에서 `this` 개체를 지정합니다. 지정하지 않으면 `this` 개체가 정의되지 않습니다.  
  
## <a name="remarks"></a>설명  
 `findIndex`는 요소가 `true`를 반환할 때까지 배열의 각 요소에 대해 한 번씩 오름차순으로 호출 함수를 호출합니다. 요소가 true를 반환하는 즉시 `findIndex`에서 true를 반환하는 요소의 인덱스 값을 반환합니다. true를 반환하는 배열의 요소가 없는 경우 `findIndex`에서 -1을 반환합니다.  
  
 `findIndex`는 배열 개체를 변경하지 않습니다.  
  
## <a name="callback-function-syntax"></a>콜백 함수 구문  
 호출 함수의 구문은 다음과 같습니다.  
  
 `function callbackfn(value, index, thisArg)`  
  
 매개 변수를 최대 3개까지 사용하여 호출 함수를 선언할 수 있습니다.  
  
 콜백 함수 매개 변수는 다음과 같습니다.  
  
|콜백 인수|정의|  
|-----------------------|----------------|  
|`value`|배열 요소의 값입니다.|  
|`index`|배열 요소의 숫자 인덱스입니다.|  
|`arrayObj`|트래버스할 배열 개체입니다.|  
  
## <a name="example"></a>예제  
 다음 예제에서 호출 함수는 배열의 각 요소가 2와 같은지 여부를 테스트합니다.  
  
```JavaScript  
[1,2,3].findIndex(function(x) { x == 2; });  
// Returns an index value of 1.  
  
```  
  
## <a name="example"></a>예제  
 다음 예제에서는 화살표 구문을 사용하여 각 요소를 테스트합니다. 이 예제에서는 `true`를 반환하는 요소가 없으며, `findIndex`에서 -1을 반환합니다.  
  
```  
[1,2,3].findIndex(x => x == 4);  
// Returns an index value of -1.   
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]