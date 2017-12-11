---
title: "연산자 우선 순위(JavaScript) | Microsoft Docs"
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
- operator precedence
- order of precedence
ms.assetid: cf3c510a-2214-4b47-b8fe-3521298efaab
caps.latest.revision: "15"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 82503a312a4a4996e3bd38f596eef3104af3f11b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: HT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="operator-precedence-javascript"></a>연산자 우선 순위(JavaScript)
연산자 우선 순위는 식이 계산될 때 연산을 수행하는 순서에 대해 설명합니다. 우선 순위가 높은 연산이 우선 순위가 낮은 연산보다 먼저 수행됩니다. 예를 들어, 곱하기가 더하기보다 먼저 수행됩니다.  
  
## <a name="includejavascriptjavascriptincludesjavascript-mdmd-operators"></a>[!INCLUDE[javascript](../javascript/includes/javascript-md.md)] 연산자  
 다음 표에는 [!INCLUDE[javascript](../javascript/includes/javascript-md.md)] 연산자가 높은 우선 순위에서 낮은 우선 순위 순서로 나열되어 있습니다. 우선 순위가 같은 연산자는 왼쪽에서 오른쪽으로 계산됩니다.  
  
|연산자|설명|  
|--------------|-----------------|  
|입니다. [ ] ( )|필드 액세스, 배열 인덱싱, 함수 호출, 식 묶기|  
|++ -- - ~ ! delete new typeof void|단항 연산자, 데이터 형식 반환, 개체 만들기, undefined 값|  
|* / %|곱하기, 나누기, 나머지 나누기|  
|+ - +|더하기, 빼기, 문자열 연결|  
|<\< >> >>>|비트 시프트|  
|< \<= > >= instanceof|보다 작음, 작거나 같음, 보다 큼, 크거나 같음, instanceof|  
|== != === !==|같음, 같지 않음, 완전 같음, 완전 같지 않음|  
|&|비트 AND|  
|^|비트 XOR|  
|&#124;|비트 OR|  
|&&|논리적 AND|  
|&#124;&#124;|논리적 OR|  
|?:|조건|  
|= *연산자*=|할당, 연산이 포함된 할당(예: += 및 &=)|  
|,|여러 식 계산|  
  
 연산자 우선 순위에 따라 결정된 계산 순서를 바꾸려면 괄호를 사용합니다. 즉, 괄호 안의 식이 완전히 계산된 후 이 값이 식의 나머지 부분에 사용됩니다.  
  
 예:  
  
```JavaScript  
var result = 78 * 96 + 3;  
document.write(result);  
document.write("<br/>");  
  
result = 78 * (9 + 3);  
document.write(result);  
  
// Output:  
// 7491  
// 936  
```  
  
 첫 번째 식에는 세 개의 연산자 =, *, +가 있습니다. 연산자 우선 순위 규칙에 따라 \*, +, = (78 \* 96 = 7488, 7488 + 3 = 7491) 순으로 계산됩니다.  
  
 두 번째 식에서는 () 연산자가 가장 먼저 계산되므로 더하기 식이 곱하기 전에 계산됩니다(9 + 3 = 12, 12 * 78 = 936).  
  
 다음 예제에서는 다양한 연산자를 포함하고 `true`인지 확인하는 문을 보여 줍니다.  
  
```JavaScript  
var num = 10;  
  
if(5 == num / 2 && (2 + 2 * num).toString() === "22") {  
    document.write(true);  
}  
    // Output:  
    // true  
```  
  
 연산자는 그룹화의 ( ), *, +(그룹화 내에서), 함수의 ".", 함수의 ( ), /, ==, ===, 및 && 순으로 계산됩니다.