---
title: "데이터 속성 및 접근자 속성 | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-javascript"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
ms.assetid: 7e132831-375d-4728-9a57-5c6f91075b1c
caps.latest.revision: 3
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 3
---
# 데이터 속성 및 접근자 속성
이 단원에는 데이터 속성 및 접근자 속성에 대해 필요할 수 있는 모든 정보가 포함되어 있습니다.  
  
### 데이터 속성  
 *데이터 속성*은 값을 가져오고 설정할 수 있는 속성입니다.  데이터 속성에는 해당 설명에 `value` 및 `writable` 속성이 포함됩니다.  
  
 다음 표에서는 데이터 속성 설명자의 특성을 보여 줍니다.  
  
|데이터 설명자 특성|설명|기본값|  
|----------------|--------|---------|  
|`value`|속성의 현재 값입니다.|`undefined`|  
|`writable`|`true` 또는 `false` `writable`이 `true`로 설정되어 있으면 속성 값을 수정할 수 있습니다.|`false`|  
|`enumerable`|`true` 또는 `false` `enumerable`이 `true`로 설정되어 있으면 `for…in` 문으로 속성을 열거할 수 있습니다.|`false`|  
|`configurable`|`true` 또는 `false` `configurable`이 `true`로 설정되어 있으면 속성 특성을 변경할 수 있고 속성을 삭제할 수 있습니다.|`false`|  
  
 설명자에 `value`, `writable`, `get` 또는 `set` 특성이 포함되지 않았고 지정된 속성 이름이 없으면 데이터 속성이 추가됩니다.  
  
 `configurable` 특성이 `false`이고 `writable`이 `true`이면 `value` 및`writable` 특성을 변경할 수 있습니다.  
  
#### defineProperty를 사용하지 않고 추가된 데이터 속성  
 `Object.defineProperty`, `Object.defineProperties` 또는 `Object.create` 함수를 사용하지 않고 데이터 속성을 추가할 경우 `writable`, `enumerable` 및 `configurable` 특성이 모두 `true`로 설정됩니다.  속성을 추가한 후에는 `Object.defineProperty` 함수를 사용하여 수정할 수 있습니다.  
  
 다음과 같은 방식으로 데이터 속성을 추가할 수 있습니다.  
  
-   할당 연산자\(\=\), 예: `obj.color = "white";`  
  
-   개체 리터럴, 예: `obj = { color: "white", height: 5 };`  
  
-   [생성자를 사용하여 형식 정의](../../javascript/advanced/using-constructors-to-define-types.md)에 설명된 생성 함수  
  
### 접근자 속성  
 *접근자 속성*은 속성 값을 설정하거나 검색할 때마다 사용자가 제공한 함수를 호출합니다.  접근자 속성의 설명자에는 `get` 특성이나 `set` 특성 또는 두 특성이 모두 포함됩니다.  
  
 다음 표에서는 접근자 속성 설명자에 대한 특성을 보여 줍니다.  
  
|접근자 설명자 특성|설명|기본값|  
|----------------|--------|---------|  
|`get`|속성 값을 반환하는 함수입니다.  이 함수에는 매개 변수가 없습니다.|`undefined`|  
|`set`|속성 값을 설정하는 함수입니다.  여기에는 할당할 값을 포함하는 매개 변수가 하나 있습니다.|`undefined`|  
|`enumerable`|`true` 또는 `false` `enumerable`이 `true`로 설정되어 있으면 `for…in` 문으로 속성을 열거할 수 있습니다.|`false`|  
|`configurable`|`true` 또는 `false` `configurable`이 `true`로 설정되어 있으면 속성 특성을 변경할 수 있고 속성을 삭제할 수 있습니다.|`false`|  
  
 `get` 접근자가 정의되지 않았고 속성 값에 액세스하려고 시도하면 `undefined` 값이 반환됩니다.  `set` 접근자가 정의되지 않았고 접근자 속성에 값을 할당하려고 시도하면 아무 것도 발생하지 않습니다.  
  
### 속성 수정  
 개체에 지정된 이름의 속성이 이미 있으면 속성 특성이 수정됩니다.  속성을 수정하면 설명자에 지정되지 않은 특성이 동일한 상태로 유지됩니다.  
  
 기존 속성의 `configurable` 특성이 `false`인 경우 허용되는 유일한 수정은 `writable` 특성을 `true`에서 `false`로 변경하는 것뿐입니다.  
  
 데이터 속성을 접근자 속성으로 변경하거나 그 반대로 변경할 수 있습니다.  이렇게 하면 설명자에 지정되지 않은 `configurable` 및 `enumerable` 특성이 속성에 보존됩니다.  설명자에 지정되지 않은 기타 특성은 해당 기본값으로 설정됩니다.  
  
 `Object.defineProperty` 함수에 대한 다중 호출을 사용하여 구성 가능한 접근자 속성을 증분식으로 정의할 수 있습니다.  예를 들어 한 번의 `Object.defineProperty` 호출로 `get` 접근자만 정의하고  이후 동일한 속성 이름에 대한 호출을 수행하여 `set` 접근자를 정의할 수 있습니다.  그러면 속성이 `get` 접근자와 `set` 접근자를 모두 포함하게 됩니다.  
  
 기존 속성에 적용되는 설명자 개체를 가져오려면 [Object.getOwnPropertyDescriptor 함수](../../javascript/reference/object-getownpropertydescriptor-function-javascript.md)를 사용할 수 있습니다.  
  
 [Object.seal 함수](../../javascript/reference/object-seal-function-javascript.md) 및 [Object.freeze 함수](../../javascript/reference/object-freeze-function-javascript.md)를 사용하여 속성 특성이 수정되지 않도록 방지할 수 있습니다.