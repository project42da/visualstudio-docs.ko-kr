---
title: "length 속성 (Function) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: length Property
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Length property
- length property (function)
ms.assetid: fdc8e1c9-0dac-4e1b-ba3a-11073c37ef63
caps.latest.revision: "15"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4fbd0334c18da2c6ef8de8366555d79f791e6855
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="length-property-function-javascript"></a>length 속성(Function)(JavaScript)
함수에 대해 정의 된 인수 개수를 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
functionName.length  
```  
  
## <a name="remarks"></a>설명  
 필요한 *functionName* 함수 이름입니다.  
  
 **길이** 함수의 속성은 함수의 인스턴스를 만들 때 스크립팅 엔진 수의 함수 정의에 인수에 의해 초기화 됩니다.  
  
 값과에서 다른 인수 수가 함수를 호출 하는 경우 해당 **길이** 속성 함수에 따라 달라 집니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 **길이** 속성:  
  
```JavaScript  
function ArgTest(a, b){  
    var s = "";  
  
    s += "Expected Arguments: " + ArgTest.length;  
    s += "<br />";  
    s += "Passed Arguments: " + arguments.length;  
  
    return s;  
}  
  
document.write(ArgTest(1, 2));  
  
// Output:   
// Expected Arguments: 2  
// Passed Arguments: 2  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [arguments 속성 (Function)](../../javascript/reference/arguments-property-function-javascript.md)   
 [length 속성 (Array)](../../javascript/reference/length-property-array-javascript.md)   
 [length 속성(String)](../../javascript/reference/length-property-string-javascript.md)