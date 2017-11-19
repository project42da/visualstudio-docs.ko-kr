---
title: "예기치 않은 수량자입니다 (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: javascript
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VS.WebClient.Help.SCRIPT5018
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: ba6d34f9-2d6f-486c-a929-6cd9818be322
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fb6d6d3129057c399dd7369c6f69eb7396f07ab4
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="unexpected-quantifier-javascript"></a>예기치 않은 수량자입니다.(JavaScript)
정규식 검색 패턴을 작성할 때 잘못 된 반복 비율로 패턴 요소를 만들었습니다. 예를 들어, 패턴  
  
```  
/^+/  
```  
  
 수행할 수 없습니다 때문에 요소 ^ (입력의 시작 부분) 반복 인수를 가질 수 없습니다. 다음 표에서 반복 요소를 가질 수 없는 요소를 나열 합니다.  
  
|요소|설명|  
|-------------|-----------------|  
|^|입력 시작 부분|  
|$|입력의 끝|  
|\b|단어 경계|  
|\B|비단어 경계|  
|*|0 개 이상의 반복|  
|+|하나 이상의 반복|  
|?|0 회 이상 여러 번의 반복|  
|{n}|n 회 반복|  
|{n}|n 또는 반복 횟수가|  
|{n, m}|N-m 반복 (포함)|  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   검색 패턴 요소 포함 법적 반복 요소만 확인 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Regular Expression 개체](../../javascript/reference/regular-expression-object-javascript.md)   
 [정규식 구문 (JavaScript)](http://msdn.microsoft.com/en-us/ab0766e1-7037-45ed-aa23-706f58358c0e)