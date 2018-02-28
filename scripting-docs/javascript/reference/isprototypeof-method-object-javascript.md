---
title: "isPrototypeOf 메서드 (Object) (JavaScript) | Microsoft Docs"
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
- isPrototypeOf
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- isPrototypeOf method
ms.assetid: 9c821319-c208-480f-915e-565ef6e017b6
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 47ce97faecfade089bbf0b7a725a02ee73b54718
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="isprototypeof-method-object-javascript"></a>isPrototypeOf 메서드(Object)(JavaScript)
개체가 다른 개체의 프로토타입 체인에 있는지 여부를 확인합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
prototype.isPrototypeOf(object)  
```  
  
## <a name="parameters"></a>매개 변수  
 `prototype`  
 필수 요소. 개체 프로토타입  
  
 `object`  
 필수 요소. 프로토타입 체인을 확인할 또 다른 개체입니다.  
  
## <a name="remarks"></a>설명  
 `isPrototypeOf`의 프로토타입 체인에 `true`이 포함된 경우 `object` 메서드가 `prototype`를 반환합니다. 프로토타입 체인은 동일한 유형의 개체 인스턴스 사이에 기능을 공유할 때 사용합니다. `isPrototypeOf`가 개체가 아니거나 `false`이 `object`의 프로토타입 체인에 표시되지 않으면 `prototype` 메서드가 `object`를 반환합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `isPrototypeOf` 메서드를 사용하는 방법을 보여 줍니다.  
  
```JavaScript  
function Rectangle() {  
}  
  
var rec = new Rectangle();  
  
document.write(Rectangle.prototype.isPrototypeOf(rec));  
  
// Output: true  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [prototype 속성(Object)](../../javascript/reference/prototype-property-object-javascript.md)