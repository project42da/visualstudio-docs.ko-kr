---
title: "0... n 속성 (arguments) (JavaScript) | Microsoft Docs"
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
- 0...n
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- 0...n properties
ms.assetid: 52857c4b-3d56-4500-93ff-4db4729c2578
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: f46c7dafef1cdc27d27f619936349637af172740
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="0n-properties-arguments-javascript"></a>0...n 속성(arguments)(JavaScript)
개별 인수로의 실제 값을 반환 된 **인수** 에서 반환 된 개체는 **인수** 실행 중인 함수의 속성입니다.  
  
## <a name="syntax"></a>구문  
  
```  
[function.]arguments[[0|1|2|...|n]]  
```  
  
## <a name="parameters"></a>매개 변수  
 *function*  
 선택 사항입니다. 현재 실행의 이름 `Function` 개체입니다.  
  
 0, 1, 2, *, n*  
 필수 요소. 0부터 범위에 음수가 아닌 정수  *n*  여기서 0은 첫 번째 인수 및  *n*  최종 인수를 나타냅니다. 마지막 인수 값  *n*  은 **arguments.length 1**합니다.  
  
## <a name="remarks"></a>설명  
 0에서 반환 된 값입니다. 입니다. 입니다. n 개 속성은 실행 중인 함수에 전달 된 실제 값입니다. 실제로 인수의 배열, 하는 동안 각각의 인수를 구성 하는 **인수** 개체 배열 요소 액세스는 동일한 방식으로 액세스 됩니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 **0...**  ***n***속성은 **인수** 개체입니다. 예제를 완벽 하 게 이해 하려면 하나 이상의 인수를 함수에 전달 합니다.  
  
```JavaScript  
function ArgTest(){  
   var s = "";  
   s += "The individual arguments are: "  
   for (n = 0; n < arguments.length; n++){  
      s += ArgTest.arguments[n];  
      s += " ";  
   }  
   return(s);  
}  
document.write(ArgTest(1, 2, "hello", new Date()));  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
 **적용 대상**: [인수 개체](../../javascript/reference/arguments-object-javascript.md)&#124; [개체 함수](../../javascript/reference/function-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [length 속성 (arguments)](../../javascript/reference/length-property-arguments-javascript.md)   
 [length 속성(Function)](../../javascript/reference/length-property-function-javascript.md)