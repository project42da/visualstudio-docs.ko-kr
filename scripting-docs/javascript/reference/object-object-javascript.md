---
title: "개체 개체 (JavaScript) | Microsoft Docs"
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
- object
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Object object
ms.assetid: d24ef8fc-217b-4828-94e1-19f72780bae0
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 17e82b9c66c286c7f847e7b67b1b5928aadd613e
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="object-object-javascript"></a>Object 개체(JavaScript)
모든 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 개체에 공통 기능을 제공합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
obj  
 = new Object([value])   
```  
  
## <a name="parameters"></a>매개 변수  
 `obj`  
 필수 요소. `Object` 개체가 할당되는 변수 이름입니다.  
  
 *value*  
 선택 사항입니다. [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 기본 데이터 형식의 하나(숫자, 부울 또는 문자열). 값이 개체이면 개체가 수정 없이 반환됩니다. 경우 *값* 은 `null`, **정의 되지 않은**, 또는 제공 되지 않으면 콘텐츠 없는 개체가 생성 됩니다.  
  
## <a name="remarks"></a>설명  
 `Object` 개체는 모든 기타 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 개체에 포함되고, 모든 해당 메서드 및 속성을 모든 기타 개체에서 사용할 수 있습니다. 메서드는 사용자 정의 개체에서 다시 정의할 수 있고 해당할 때 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]를 통해 호출됩니다. **toString** 메서드 자주 다시 정의의 예로 `Object` 메서드.  
  
 이 언어 참조에서 각 `Object` 메서드의 설명에는 내장 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 개체에 대한 기본 및 개체별 구현 정보가 둘 다 포함됩니다.  
  
## <a name="requirements"></a>요구 사항  
 `Object Object`는 [!INCLUDE[jsv3text](../../javascript/reference/includes/jsv3text-md.md)]에서 도입되었습니다. 다음 목록의 일부 멤버는 이후 버전에서 도입되었습니다.  
  
## <a name="properties"></a>속성  
 다음 표에서는 `Object Object`의 속성을 보여 줍니다.  
  
|속성|설명|  
|--------------|-----------------|  
|[__proto\_ \_ 속성](../../javascript/reference/proto-property-object-javascript.md)|개체의 프로토타입을 지정합니다.|  
|[constructor 속성](../../javascript/reference/constructor-property-object-javascript.md)|개체를 만드는 함수를 지정합니다.|  
|[prototype 속성](../../javascript/reference/prototype-property-object-javascript.md)|개체 클래스의 프로토타입에 대한 참조를 반환합니다.|  
  
## <a name="functions"></a>함수  
 다음 표에서는 `Object Object`의 함수를 보여줍니다.  
  
|함수|설명|  
|--------------|-----------------|  
|[Object.assign 함수](../../javascript/reference/object-assign-function-object-javascript.md)|하나 이상의 소스 개체에서 대상 개체로 값을 복사합니다.|  
|[Object.create 함수](../../javascript/reference/object-create-function-javascript.md)|지정된 프로토타입이 있고 선택적으로 지정된 속성을 포함하는 개체를 만듭니다.|  
|[Object.defineProperties 함수](../../javascript/reference/object-defineproperties-function-javascript.md)|개체에 하나 이상의 속성을 추가하거나 기존 속성의 특성을 수정합니다.|  
|[Object.defineProperty 함수](../../javascript/reference/object-defineproperty-function-javascript.md)|개체에 속성을 추가하거나 기존 속성의 특성을 수정합니다.|  
|[Object.freeze 함수](../../javascript/reference/object-freeze-function-javascript.md)|기존 속성 특성 및 값의 수정을 방지하고 새 속성 추가를 방지합니다.|  
|[Object.getOwnPropertyDescriptor 함수](../../javascript/reference/object-getownpropertydescriptor-function-javascript.md)|데이터 속성 또는 접근자 속성의 정의를 반환합니다.|  
|[Object.getOwnPropertyNames 함수](../../javascript/reference/object-getownpropertynames-function-javascript.md)|개체의 속성 및 메서드 이름을 반환합니다.|  
|[Object.getOwnPropertySymbols 함수](../../javascript/reference/object-getownpropertysymbols-function-javascript.md)|개체의 기호 속성을 반환합니다.|  
|[Object.getPrototypeOf 함수](../../javascript/reference/object-getprototypeof-function-javascript.md)|개체의 프로토타입을 반환합니다.|  
|[Object.is 함수](../../javascript/reference/object-is-function-javascript.md)|두 값이 같은 값인지를 나타내는 값을 반환합니다.|  
|[Object.isExtensible 함수](../../javascript/reference/object-isextensible-function-javascript.md)|개체에 새 속성을 추가할 수 있는지를 나타내는 값을 반환합니다.|  
|[Object.isFrozen 함수](../../javascript/reference/object-isfrozen-function-javascript.md)|개체에서 기존 속성 특성 및 값을 수정할 수 없고 개체에 새 속성을 추가할 수 없으면 `true`를 반환합니다.|  
|[Object.isSealed 함수](../../javascript/reference/object-issealed-function-javascript.md)|개체에서 기존 속성 특성을 수정할 수 없고 개체에 새 속성을 추가할 수 없으면 `true`를 반환합니다.|  
|[Object.keys 함수](../../javascript/reference/object-keys-function-javascript.md)|개체의 열거 가능한 속성 및 메서드 이름을 반환합니다.|  
|[Object.preventExtensions 함수](../../javascript/reference/object-preventextensions-function-javascript.md)|개체에 대한 새 속성 추가를 방지합니다.|  
|[Object.seal 함수](../../javascript/reference/object-seal-function-javascript.md)|기존 속성 특성의 수정을 방지하고 새 속성 추가를 방지합니다.|  
|[Object.setPrototypeOf 함수](../../javascript/reference/object-setprototypeof-function-javascript.md)|개체의 프로토타입을 설정합니다.|  
  
## <a name="methods"></a>메서드  
 다음 표에서는 `Object Object`의 메서드를 보여 줍니다.  
  
|메서드|설명|  
|------------|-----------------|  
|[hasOwnProperty 메서드](../../javascript/reference/hasownproperty-method-object-javascript.md)|개체에 지정된 이름을 가진 속성이 있는지 여부를 나타내는 부울 값을 반환합니다.|  
|[isPrototypeOf 메서드](../../javascript/reference/isprototypeof-method-object-javascript.md)|개체가 다른 개체의 프로토타입 계층 구조에 있는지 여부를 나타내는 부울 값을 반환합니다.|  
|[propertyIsEnumerable 메서드](../../javascript/reference/propertyisenumerable-method-object-javascript.md)|지정된 속성이 개체의 일부인지 여부 및 열거 가능한지 여부를 나타내는 부울 값을 반환합니다.|  
|[toLocaleString 메서드](../../javascript/reference/tolocalestring-method-object-javascript.md)|현재 로캘에 따라 문자열로 변환된 개체를 반환합니다.|  
|[toString 메서드](../../javascript/reference/tostring-method-object-javascript.md)|개체를 나타내는 문자열을 반환합니다.|  
|[valueOf 메서드](../../javascript/reference/valueof-method-object-javascript.md)|지정된 개체의 기본 값을 반환합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [JavaScript 개체](../../javascript/reference/javascript-objects.md)