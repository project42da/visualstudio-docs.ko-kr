---
title: "Math.log 함수 (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: log
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- log method
- Math object
ms.assetid: 5d617fb5-4b27-404e-842f-eea5549a7c1a
caps.latest.revision: "9"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 62bfb6bf9bb95b541a51224af4484ded22ccb4e8
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="mathlog-function-javascript"></a>Math.log 함수(JavaScript)
자연 로그를 반환 합니다 (기본 `e`) 숫자의 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
Math.log(number)   
```  
  
#### <a name="parameters"></a>매개 변수  
 number  
 숫자입니다.  
  
## <a name="return-value"></a>반환 값  
 경우 `number` 이 양수인 경우이 함수는 숫자의 자연 로그를 반환 합니다. 경우 `number` 가 음수 이면이 함수는 반환 `NaN`합니다. 경우 `number` 은 0으로,이 함수는 반환 `-Infinity`합니다.  
  
## <a name="example"></a>예제  
 다음 코드에는이 함수를 사용 하는 방법을 보여 줍니다.  
  
```JavaScript  
var numArr = [ 45.3, 69.0, 557.04, 0.222 ];  
  
for (i in numArr) {  
    document.write(Math.log(numArr[i]));  
    document.write("<br/>");  
}  
  
// Output:   
// 3.8133070324889884  
// 4.23410650459726  
// 6.322637050634291  
// -1.5050778971098575  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **적용 대상**: [Math 개체](../../javascript/reference/math-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [Math.sqrt 함수](../../javascript/reference/math-sqrt-function-javascript.md)