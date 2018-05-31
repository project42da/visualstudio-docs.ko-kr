---
title: forEach 메서드 (Map) (JavaScript) | Microsoft Docs
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
ms.assetid: 9cdf0adc-77c7-4407-8ba7-ada0fb09e507
caps.latest.revision: 7
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 549d7d625fb4dfe88b2db69e6aa0ff66c7e90f66
ms.sourcegitcommit: 37144589d9f850ff81ec7bfb884429989925a43d
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/19/2018
ms.locfileid: "34335803"
---
# <a name="foreach-method-map-javascript"></a>forEach 메서드(Map)(JavaScript)
각 지도 요소에 대 한 지정된 된 작업을 수행합니다.  
  
## <a name="syntax"></a>구문  
  
```JavaScript  
mapObj.forEach(callbackfn[, thisArg])  
```  
  
#### <a name="parameters"></a>매개 변수  
 `mapObj`  
 필수. `Map` 개체입니다.  
  
 `callbackfn`  
 필수. 함수는 `forEach` 맵의 각 요소에 대해 한 번 호출 합니다. `callbackfn` 최대 3 개의 인수를 허용합니다. `forEach` 호출 된 `callbackfn` 맵의 각 요소 마다 한 번씩 작동 합니다.  
  
 `thisArg`  
 선택 사항입니다. 개체는는 `this` 키워드에 결과를 참조할 수는 `callbackfn` 함수입니다. `thisArg`가 생략되면 `undefined`가 `this` 값으로 사용됩니다.  
  
## <a name="exceptions"></a>예외  
 `callbackfn` 인수가 함수 개체가 아닌 경우 `TypeError` 예외가 throw됩니다.  
  
## <a name="remarks"></a>설명  
 호출 함수의 구문은 다음과 같습니다.  
  
 `function callbackfn(value, key, mapObj)`  
  
 다음 표에 나와 있는 것 처럼 최대 3 개의 매개 변수를 사용 하 여 콜백 함수를 선언할 수 있습니다.  
  
|호출 인수|정의|  
|-----------------------|----------------|  
|`value`|지도에 포함 된 값입니다.|  
|`key`|지도에 포함 된 키입니다.|  
|`mapObj`|`Map` 를 트래버스해야 하는 개체입니다.|  
  
## <a name="example"></a>예제  
 구성원을 검색 하는 방법을 보여 주는 다음 예제는 `Map` 를 사용 하 여 `forEach`합니다.  
  
```JavaScript  
var m = new Map();  
m.set(1, "black");  
m.set(2, "red");  
m.set("colors", 2);  
m.set({x:1}, 3);  
  
m.forEach(function (value, key, mapObj) {  
    document.write(value.toString() + "<br />");  
});  
  
document.write("<br />");  
document.write(m.get(2));  
  
// Output:  
// black  
// red  
// 2  
// 3  
//  
// red  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]
