---
title: "instanceof 연산자 (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: instanceof_JavaScriptKeyword
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: instanceOf operator
ms.assetid: 92467bdc-56b5-42dc-adbd-a219776454d2
caps.latest.revision: "17"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b2124fe815c89c3c157be3ea729fa7edb9d96b39
ms.sourcegitcommit: f89ed5fc2e5078213e30a6ade4604e34df48181f
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/13/2018
---
# <a name="instanceof-operator-javascript"></a>instanceof 연산자(JavaScript)
개체가 특정 클래스의 인스턴스인지 여부를 나타내는 부울 값을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
result = object instanceof class  
```  
  
## <a name="parameters"></a>매개 변수  
 `result`  
 필수. 모든 변수입니다.  
  
 `object`  
 필수. 모든 개체 식입니다.  
  
 `class`  
 필수. 정의된 모든 개체 클래스입니다.  
  
## <a name="remarks"></a>설명  
 `instanceof`가 `true`의 인스턴스인 경우 `object` 연산자가 `class`를 반환합니다. 반환 `true` 경우 `class` 개체의 프로토타입 체인에 있습니다. `false`가 `object`의 인스턴스가 아니거나 `class`가 `object`인 경우에는 `null`를 반환합니다.  
  
## <a name="example"></a>예  
 다음 예제에서는 `instanceof` 연산자를 사용하는 방법을 보여 줍니다.  
  
```JavaScript  
function objTest(obj){  
    var i, t, s = "";  
    t = new Array();  
    t["Date"] = Date;  
    t["Object"] = Object;  
    t["Array"] = Array;  
        for (i in t){  
            if (obj instanceof t[i]) {   
                s += "obj is an instance of " + i + "<br/>";  
            }  
            else {  
                s += "obj is not an instance of " + i + "<br/>";  
        }  
    }  
    return(s);  
}  
  
var obj = new Date();  
document.write(objTest(obj));  
  
// Output:   
// obj is an instance of Date  
// obj is an instance of Object  
// obj is not an instance of Array  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv5](../../javascript/reference/includes/jsv5-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [연산자 우선 순위](../../javascript/operator-subtractprecedence-javascript.md)   
 [연산자 개요(JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)