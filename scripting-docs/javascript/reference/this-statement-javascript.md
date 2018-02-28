---
title: "이 문 (JavaScript) | Microsoft Docs"
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
- this_JavaScriptKeyword
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- this statement
- constructors, referring to current object
ms.assetid: 8510a00b-2f14-4700-a276-4d9a523c5112
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f4afed1bd978d1985c151efa77873c93e699f0b1
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="this-statement-javascript"></a>this 문(JavaScript)
현재 개체를 참조합니다.  
  
## <a name="syntax"></a>구문  
  
```  
this.property  
```  
  
## <a name="remarks"></a>설명  
 필수 `property` 인수는 현재 개체의 속성 중 하나입니다.  
  
 `this` 키워드는 개체 생성자에서 현재 개체를 참조할 때 사용합니다.  
  
## <a name="example"></a>예제  
 다음 예에서 **이** 새로 만든된 Car 개체를 참조 하 고 세 가지 속성에 값을 할당 합니다.  
  
```JavaScript  
function Car(color, make, model){  
   this.color = color;  
   this.make = make;  
   this.model = model;  
}  
```  
  
 **이** 키워드를 일반적으로 참조는 **창** 개체를 다른 개체의 범위 외부에서 사용 합니다. 그러나 이벤트 처리기 내에서 `this`는 이벤트를 발생시킨 DOM 요소를 나타냅니다.  
  
 다음 코드(Internet Explorer 9 이상)에서 이벤트 처리기는 ID가 "clicker"인 단추의 문자열 버전을 인쇄합니다.  
  
```JavaScript  
document.getElementById("clicker").addEventListener("click", eventHandler, false);  
  
        function eventHandler(ev) {  
            document.write(this.toString());  
        }  
  
// Output (when you click the button): [object HTMLButtonElement]  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [new 연산자](../../javascript/reference/new-operator-decrementjavascript.md)   
 [bind 메서드 사용](../../javascript/advanced/using-the-bind-method-javascript.md)