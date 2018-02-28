---
title: "length 속성 (arguments) (JavaScript) | Microsoft Docs"
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
- length Property
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- length property (arguments)
- Length property
ms.assetid: 3cf36823-15bc-489b-a951-24c4923d9dba
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: cede75a91244442f5f28ec9f71b7128814bed5d2
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="length-property-arguments-javascript"></a>length 속성(인수)(JavaScript)
호출자가 함수에 전달 된 인수의 실제 수를 반환 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
[function.]arguments.length  
```  
  
## <a name="remarks"></a>설명  
 선택적 *함수* 인수는 현재 실행의 이름 `Function` 개체입니다.  
  
 **길이** 의 속성은 **인수** 개체 스크립팅 엔진에 전달 된 인수의 실제 수에 의해 초기화 됩니다는 `Function` 해당 함수에서 실행이 시작 될 때입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 **길이** 의 속성은 **인수** 개체입니다. 예제를 완벽 하 게 이해 하려면 두 인수를 예상 보다 함수에 더 많은 인수를 전달:  
  
```JavaScript  
function ArgTest(a, b){  
   var s = "";  
  
   s += "Expected Arguments: " + ArgTest.length;  
   s += "<br />";  
   s += "Passed Arguments: " + arguments.length;  
  
   document.write (s);  
}  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
 **적용 대상**: [인수 개체](../../javascript/reference/arguments-object-javascript.md)&#124; [개체 함수](../../javascript/reference/function-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [arguments 속성 (Function)](../../javascript/reference/arguments-property-function-javascript.md)   
 [length 속성 (Array)](../../javascript/reference/length-property-array-javascript.md)   
 [length 속성(String)](../../javascript/reference/length-property-string-javascript.md)