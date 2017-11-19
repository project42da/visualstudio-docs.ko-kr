---
title: "decodeURIComponent 함수 (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: decodeURIComponent
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: decodeURIComponent method
ms.assetid: 486ccee2-afd7-4863-97ce-4adb50cf39c0
caps.latest.revision: "11"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ef7bdcd374a328bad632381d19e9823853d37f01
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="decodeuricomponent-function-javascript"></a>decodeURIComponent 함수(JavaScript)
인코딩되지 않은 버전이 인코딩된 구성 요소에는 식별자 URI (Uniform Resource)을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
decodeURIComponent(encodedURIString)  
```  
  
## <a name="remarks"></a>설명  
 필요한 `encodedURIString` 인수는는 인코딩된 URI 구성 요소를 나타내는 값입니다.  
  
 URIComponent는 완전 한 URI의 일부입니다.  
  
 경우는 `encodedURIString` 유효 하지 않을 경우는 URIError 발생 합니다.  
  
## <a name="example"></a>예제  
 다음 코드는 먼저 인코딩한 다음 URI를 디코딩합니다.  
  
```JavaScript  
var uriEncode = encodeURI ("http://www.Not a URL.com");  
var uriDecode = decodeURIComponent(uriEncode);  
  
document.write (uriEncode);  
document.write("<br/>");  
document.write (uriDecode);  
  
// Output:  
// http://www.Not%20a%20URL.com  
// http://www.Not a URL.com  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [decodeURI 함수](../../javascript/reference/decodeuri-function-javascript.md)   
 [encodeURI 함수](../../javascript/reference/encodeuri-function-javascript.md)