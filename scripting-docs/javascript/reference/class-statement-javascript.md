---
title: "class 문 (JavaScript) | Microsoft Docs"
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
ms.assetid: bf45ebad-4678-4062-88df-55d32b603c69
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: e828ae86c3f8f585179e3b097d98b3449c3f3b45
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="class-statement-javascript"></a>class 문(JavaScript)
새 클래스를 선언합니다.  
  
## <a name="syntax"></a>구문  
  
```  
class classname () [extends object] {    [constructor([arg1 [,... [,argN]]]) {        statements    }]    [[static] method([arg1 [,... [,argN]]]) {        statements    }]}  
```  
  
#### <a name="parameters"></a>매개 변수  
 `classname`  
 필수 요소. 클래스의 이름입니다.  
  
 `object`  
 선택 사항입니다. 새 클래스가 속성과 메서드를 상속하는 소스 개체 또는 클래스입니다.  
  
 `constructor`  
 선택 사항입니다. 새 클래스 인스턴스를 초기화하는 생성자 함수입니다.  
  
 `arg1...argN`  
 선택 사항입니다. 함수가 인식하는 선택적, 쉼표로 구분된 인수 목록입니다.  
  
 `statements`  
 선택 사항입니다. 하나 이상의 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 문입니다.  
  
 `static`  
 선택 사항입니다. 정적 메서드를 지정합니다.  
  
 `method`  
 선택 사항입니다. 클래스 인스턴스에서 호출될 수 있는 하나 이상의 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 인스턴스 또는 정적 메서드입니다.  
  
## <a name="remarks"></a>설명  
 클래스를 통해 프로토타입 기반 상속, 생성자, 인스턴스 메서드 및 정적 메서드를 사용하여 새 개체를 만들 수 있습니다. 클래스 생성자나 클래스 메서드 내에서 `super` 개체를 사용하여 부모 클래스 또는 개체에서 같은 생성자 또는 메서드를 호출할 수 있습니다. 선택적으로 클래스 이름 뒤에 `extends` 문을 사용하여 새 클래스가 메서드를 상속하는 소스 클래스 또는 개체를 지정합니다.  
  
## <a name="example"></a>예제  
  
```JavaScript  
class Spelunking extends EXPERIENCE.Outdoor {  
  constructor(name, location) {  
    super(name, location);  
  
    this.minSkill = Spelunking.defaultSkill();  
    //...  
  }  
  update(minSkill) {  
    //...  
    super.update(minSkill);  
  }  
  static defaultSkill() {  
    return new EXPERIENCE.Level3();  
  }  
}  
```  
  
## <a name="example"></a>예제  
 클래스에 대한 계산된 속성 이름을 만들 수도 있습니다. 다음 코드 예제에서는 `set` 구문을 사용하여 계산된 속성 이름을 만듭니다.  
  
```JavaScript  
var propName = "prop_42";  
  
class Spelunking {  
    set [propName](v) {  
        this.value = v;  
    }  
};  
  
var s = new Spelunking();  
console.log(s.value);  
s.prop_42 = 42;  
console.log(s.value);  
  
// Output:  
// undefined  
// 42  
  
```  
  
## <a name="example"></a>예제  
 다음 코드 예제에서는 `get` 구문을 사용하여 동적으로 클래스의 속성 이름을 만듭니다.  
  
```JavaScript  
var propName = "prop_42";  
  
class Spelunking {  
    get [propName]() {  
        return 777;  
    }  
}  
  
var s = new Spelunking();  
console.log(s.prop_42);  
  
// Output:  
// 777  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv12exp](../../javascript/reference/includes/jsv12exp-md.md)]