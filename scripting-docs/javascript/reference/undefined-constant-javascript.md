---
title: "undefined 상수 (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: undefined
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: undefined property
ms.assetid: 2a689d7d-00b0-48fb-9c95-5c2867bde006
caps.latest.revision: "20"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8ba7fa8b160e4f5d954c8d6545da5fae41c2f74b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="undefined-constant-javascript"></a>undefined 상수(JavaScript)
정의 하지 않았습니다, 예: 초기화 되지 않은 변수는 값입니다.  
  
## <a name="syntax"></a>구문  
  
```  
undefined  
```  
  
## <a name="remarks"></a>설명  
 `undefined` 상수의 멤버인는 `Global` 개체를 스크립팅 엔진을 초기화 하는 경우 사용할 수 있게 됩니다. 변수 선언 되었지만 초기화 되지 않았습니다 그 값은 **정의 되지 않은**합니다.  
  
 에 비교할 수 없으므로 변수 선언 되지 않은 경우 `undefined`, 하지만 "undefined" 라는 문자열을 변수의 형식을 비교할 수 있습니다.  
  
 `undefined` 상수가 유용한 경우에 명시적으로 테스트 또는 정의 되지 않은 변수를 설정 합니다.  
  
## <a name="example"></a>예제  
 사용 하는 방법을 보여 주는 다음 예제는 `undefined` 상수입니다.  
  
```JavaScript  
// A variable that has not been initialized.  
var declared;  
  
if (declared == undefined)  
    document.write("declared has not been given a value <br/>");  
else  
    document.write("declared has been given a value <br/>");  
  
document.write("typeof declared is " + typeof(declared) + "<br/>");  
  
// An undeclared variable cannot be compared to undefined,  
// so the next line would generate an error.  
// if (notDeclared == undefined);  
  
document.write("typeof notDeclared is " + typeof(notDeclared));  
  
// Output:  
// declared has not been given a value  
// typeof declared is undefined  
// typeof notDeclared is undefined  
```  
  
## <a name="requirements"></a>요구 사항  
 `undefined` 속성에 도입 된 [!INCLUDE[jsv55text](../../javascript/reference/includes/jsv55text-md.md)], 읽기 전용 액세스 만들어진 및 [!INCLUDE[jsv9textspecific](../../javascript/reference/includes/jsv9textspecific-md.md)]합니다.  
  
 **적용 대상**: [전역 개체](../../javascript/reference/global-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [typeof 연산자](../../javascript/reference/typeof-operator-decrementjavascript.md)