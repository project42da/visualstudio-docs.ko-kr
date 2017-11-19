---
title: "arguments 속성 (Function) (JavaScript) | Microsoft Docs"
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
- arguments, arguments property
- Arguments property
ms.assetid: efc7a1ee-0880-4f05-b0f2-808f31a4af1d
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5b0b18fb8164639119e5db5e7a5d76b4280f9c9d
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="arguments-property-function-javascript"></a>arguments 속성(Function)(JavaScript)
현재 실행에 대 한 인수를 가져옵니다 `Function` 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
function.arguments  
```  
  
## <a name="remarks"></a>설명  
 `function` 인수는 현재 실행 중인 함수 이름이 며 생략할 수 있습니다.  
  
 이 속성을 사용 하면 여러 개의 인수를 처리 하는 함수입니다. **길이** 의 속성은 `arguments` 함수에 전달 된 인수의 수를 포함 하는 개체입니다. 에 포함 된 각각의 인수는 `arguments` 개체 배열 요소 액세스 같은 방식으로 액세스할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `arguments` 속성을 사용하는 방법을 보여 줍니다.  
  
```JavaScript  
function ArgTest(arg1, arg2){  
   var s = "";  
   s += "The individual arguments are: "  
   for (n = 0; n < arguments.length; n++){  
      s += ArgTest.arguments[n];  
      s += " ";  
   }  
   return(s);  
}  
document.write(ArgTest(1, 2, "hello"));  
  
//Output: function ArgTest(arg1, arg2){  
   var s = "";  
   s += "The individual arguments are: "  
   for (n = 0; n < arguments.length; n++){  
      s += ArgTest.arguments[n];  
      s += " ";  
   }  
   return(s);  
}  
document.write(ArgTest(1, 2, "hello"));  
  
// Output: The individual arguments are: 1 2 hello  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [arguments 개체](../../javascript/reference/arguments-object-javascript.md)   
 [function 문](../../javascript/reference/function-statement-javascript.md)