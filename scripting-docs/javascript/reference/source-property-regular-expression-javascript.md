---
title: "source 속성 (Regular Expression) (JavaScript) | Microsoft Docs"
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
- source
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Source property
ms.assetid: d58ac57e-fcde-49d1-bbba-e8c4218448c4
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 05bf118aec0f31de11a3df6f4b875fad3092e53d
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="source-property-regular-expression-javascript"></a>source 속성(Regular Expression)(JavaScript)
정규식 패턴의 텍스트의 복사본을 반환합니다. 읽기 전용입니다. `rgExp` 인수가 **정규식** 개체입니다. 변수 이름 또는 리터럴일 수 있습니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
rgExp.source  
```  
  
## <a name="example"></a>예제  
 다음 예제에서는 **소스** 속성:  
  
```JavaScript  
function SourceDemo(re, s){  
   var s1;  
   // Test string for existence of regular expression.  
   if (re.test(s))  
      s1 = " contains ";  
   else  
      s1 = " does not contain ";  
   // Get the text of the regular expression itself.  
   return(s + s1 + re.source);  
}  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **적용 대상**: [Regular Expression 개체](../../javascript/reference/regular-expression-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [Regular Expression 개체](../../javascript/reference/regular-expression-object-javascript.md)   
 [Regular Expression 개체](../../javascript/reference/regular-expression-object-javascript.md)   
 [정규식 구문 (JavaScript)](http://msdn.microsoft.com/en-us/ab0766e1-7037-45ed-aa23-706f58358c0e)