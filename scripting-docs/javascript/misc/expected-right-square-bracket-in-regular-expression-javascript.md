---
title: "예상 &#39;] &#39; 정규식 (JavaScript)에서 | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: javascript
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: VS.WebClient.Help.SCRIPT5019
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 1ca2079a-44dd-479f-a1e3-e04a14d0739e
caps.latest.revision: "7"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 4c59dcbeea91a1bc01e870d0a49fd22cace6562d
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="expected-3939-in-regular-expression-javascript"></a>예상 &#39;] &#39; 정규식 (JavaScript)
정규식 일치에 대 한 문자 클래스를 생성 하려고 하지만 오른쪽 대괄호를 포함 하지 않았습니다. 괄호 안에 배치 하 여 문자 클래스에 개별 리터럴 문자 조합은 조합할 수 있습니다. 문자 클래스는 포함 된 하나의 문자를 찾습니다. 예를 들어 / [abc] "a", "b", 문자 중 하 나와 일치 / 또는 "c"입니다.  
  
### <a name="to-correct-this-error"></a>이 오류를 해결하려면  
  
-   정규식에 오른쪽 대괄호를 추가 합니다.  
  
    > [!NOTE]
    >  단일 괄호 하려면-백슬래시로 이스케이프 \\[로 하 여 특수 문자로 해석 되지 않습니다 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Regular Expression 개체](../../javascript/reference/regular-expression-object-javascript.md)   
 [정규식 구문 (JavaScript)](http://msdn.microsoft.com/en-us/ab0766e1-7037-45ed-aa23-706f58358c0e)