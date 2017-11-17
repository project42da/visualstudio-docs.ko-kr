---
title: "arguments 개체 (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: arguments
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- arguments, arguments object
- arguments object
ms.assetid: 5eb79ca9-bbb8-4a42-aaf5-16a93ecb425f
caps.latest.revision: "15"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 2a5c526d19ad5469d9d099f51cc5a2e2d089814f
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="arguments-object-javascript"></a>arguments 개체(JavaScript)
현재 실행 중인 함수 및 해당 함수를 호출한 함수에 대한 인수를 나타내는 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
[function.]arguments[n]  
```  
  
## <a name="parameters"></a>매개 변수  
 *function*  
 선택 사항입니다. 현재 실행의 이름 `Function` 개체입니다.  
  
 *n*  
 필수 요소. 에 전달 된 인수 값에 0부터 시작 인덱스는 `Function` 개체입니다.  
  
## <a name="remarks"></a>설명  
 명시적으로 만들 수 없습니다는 **인수** 개체입니다. **인수** 개체만을 사용할 수는 함수 실행을 시작 합니다. **인수** 함수 개체를 배열에 아니라 개별 인수에 배열 요소 액세스는 동일한 방식으로 액세스 합니다. 인덱스  *n*  실제로 중 하나에 대 한 참조는 **0**  ***n***  의 속성은 **인수** 개체입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 **인수** 개체입니다.  
  
```JavaScript  
function ArgTest(a, b)  
{  
   var s = "";  
  
   s += "Expected Arguments: " + ArgTest.length;  
   s += "<br />";  
   s += "Passed Arguments: " + arguments.length;  
   s += "<br />";  
  
   s += "The individual arguments are: "  
   for (n = 0; n < arguments.length; n++)  
   {  
      s += ArgTest.arguments[n];  
      s += " ";  
   }  
  
   document.write(s);  
}  
  
ArgTest(1, 2, "hello", new Date())  
  
// Output:  
// Expected Arguments: 2  
// Passed Arguments: 4  
// The individual arguments are: 1 2 hello Tues Jan 8 08:27:09 PST 20xx  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [0... n 속성 (arguments)](../../javascript/reference/0-dot-dot-dot-n-properties-arguments-javascript.md)   
 [callee 속성 (arguments)](../../javascript/reference/callee-property-arguments-javascript.md)   
 [length 속성(arguments)](../../javascript/reference/length-property-arguments-javascript.md)