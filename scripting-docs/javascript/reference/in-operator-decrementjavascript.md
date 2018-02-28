---
title: "in 연산자 (JavaScript) | Microsoft Docs"
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
- in_JavaScriptKeyword
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- in operator
ms.assetid: dcd8f901-96b8-4c91-848b-b1ec0ab1c11c
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: eefcd4c53d2e3366a26f0d8dfb099f59038507ae
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="in-operator-javascript"></a>in 연산자(JavaScript)
개체에 속성이 있는지 테스트합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
result = property in object  
```  
  
## <a name="parameters"></a>매개 변수  
 `result`  
 필수 요소. 모든 변수입니다.  
  
 `property`  
 필수 요소. 문자열 식으로 계산 되는 식입니다.  
  
 `object`  
 필수 요소. 모든 개체입니다.  
  
## <a name="remarks"></a>설명  
 `in` 개체에 라는 속성이 있는지 여부를 결정 하는 연산자 `property`합니다. 또한 속성 개체의 프로토타입 체인의 일부 인지 여부를 결정 합니다. 개체 프로토타입에 대 한 자세한 내용은 참조 [프로토타입 및 프로토타입 상속](../../javascript/advanced/prototypes-and-prototype-inheritance.md)합니다.  
  
## <a name="example"></a>예제  
 사용 하는 방법을 보여 주는 다음 예제는 `in` 연산자:  
  
```JavaScript  
// Create an object that has some properties.  
var myObject = new Object();  
myObject.name = "James";  
myObject.age = "22";  
myObject.phone = "555 0234";  
  
if ("phone" in myObject)  
   document.write ("property is present");  
else  
   document.write ("property is not present");  
  
// Output: property is present  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [연산자 우선 순위](../../javascript/operator-subtractprecedence-javascript.md)   
 [연산자 개요(JavaScript)](../../javascript/misc/operator-subtractsummary-javascript.md)