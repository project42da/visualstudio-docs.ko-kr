---
title: "Math.abs 함수 (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: abs
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- absolute values, calculating
- absolute values
- numeric expressions
- abs method
ms.assetid: 9af4b5b8-de77-47bb-bb59-abdde371e4c3
caps.latest.revision: "18"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 5719905a7de375f1b409378f0579e3d8b25209fc
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="mathabs-function-javascript"></a>Math.abs 함수(JavaScript)
(양수 또는 음수 인지에 관계 없이 값) 숫자의 절대값을 반환 합니다. 예를 들어-5의 절대 값 5의 절대 값와 같습니다.  
  
## <a name="syntax"></a>구문  
  
```  
Math.abs(number)  
```  
  
#### <a name="parameters"></a>매개 변수  
 필요한 `number` 인수는 절대값 필요한 숫자 식입니다.  
  
## <a name="return-value"></a>반환 값  
 절대값은 `number` 인수입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `abs` 함수를 사용하는 방법을 보여 줍니다.  
  
```JavaScript  
var s;  
var v1 = Math.abs(6);  
var v2 = Math.abs(-6);  
if (v1 == v2) {  
    document.write("Absolute values are the same.");  
}  
else {  
document.write("Absolute values are different.");  
}  
  
// Output: Absolute values are the same.  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **적용 대상**: [Math 개체](../../javascript/reference/math-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [Math 개체](../../javascript/reference/math-object-javascript.md)