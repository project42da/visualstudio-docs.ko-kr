---
title: "재귀(JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- functions, recursive function calls
- recursive procedures
- function calls, recursive
ms.assetid: 885855a6-3838-457d-9eb4-cce1ccaa5a8d
caps.latest.revision: "14"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 06735c244ed6bd3c8d9abe59123f9f961e6f1847
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="recursion-javascript"></a>재귀(JavaScript)
재귀는 함수가 자체를 호출하는 중요한 프로그래밍 기술입니다.  
  
## <a name="an-example-of-recursion"></a>재귀의 예  
 한 가지 예는 계승 계산입니다. 숫자 *n*의 계승은 1 \* 2 \* 3 \*... *n*을 곱하여 계산합니다. 다음 예제는 계승을 반복적으로 계산하는 방법, 즉 결과가 계산되는 `while` 루프를 사용하여 계산하는 방법을 보여 줍니다.  
  
```JavaScript  
function factorial(num)  
{  
    // If the number is less than 0, reject it.  
    if (num < 0) {  
        return -1;  
    }  
    // If the number is 0, its factorial is 1.  
    else if (num == 0) {  
        return 1;  
    }  
    var tmp = num;  
    while (num-- > 2) {  
        tmp *= num;  
    }  
    return tmp;  
}  
  
var result = factorial(8);  
document.write(result);  
  
// Output: 40320  
```  
  
 예제를 매우 간단하게 재귀적으로 만들 수 있습니다. `while` 루프를 사용하여 값을 계산하는 대신, `factorial`을 다시 호출하여 다음으로 낮은 값을 전달할 수 있습니다. 값이 1이면 재귀가 중지됩니다.  
  
```JavaScript  
function factorial(num)  
{  
    // If the number is less than 0, reject it.  
    if (num < 0) {  
        return -1;  
    }  
    // If the number is 0, its factorial is 1.  
    else if (num == 0) {  
        return 1;  
    }  
    // Otherwise, call this recursive procedure again.  
    else {  
        return (num * factorial(num - 1));  
    }  
}  
  
var result = factorial(8);  
document.write(result);  
  
// Output: 40320  
```