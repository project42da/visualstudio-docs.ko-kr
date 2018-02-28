---
title: "decodeURI 함수 (JavaScript) | Microsoft Docs"
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
- decodeURI
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- decodeURI method
ms.assetid: af6c81dc-10f4-4243-a7ce-d18ae3ea0fb8
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 97291142083ae88c7dc84d9cd08af5c3c39ff9e8
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="decodeuri-function-javascript"></a>decodeURI 함수(JavaScript)
인코딩되지 않은 버전을의 인코딩된 식별자 URI (Uniform Resource)을 가져옵니다.  
  
## <a name="syntax"></a>구문  
  
```  
decodeURI(URIstring)  
```  
  
## <a name="remarks"></a>설명  
 필요한 `URIstring` 인수는 인코딩된 URI를 나타내는 값입니다.  
  
 사용 하 여는 `decodeURI` 사용 되지 않는 대신 함수 `unescape` 함수입니다.  
  
 `decodeURI` 함수는 문자열 값을 반환 합니다.  
  
 경우는 `URIString` 유효 하지 않을 경우는 URIError 발생 합니다.  
  
 **적용 대상**: [전역 개체](../../javascript/reference/global-object-javascript.md)  
  
## <a name="example"></a>예제  
 다음 코드는 먼저 URI 구성 요소를 인코딩합니다를 디코딩합니다.  
  
```JavaScript  
var uriEncode = encodeURIComponent ("www.Not a URL.com");  
var uriDecode = decodeURIComponent(uriEncode);  
  
document.write (uriEncode);  
document.write ("<br/>");  
document.write (uriDecode);  
  
// Output:  
// www.Not%20a%20URL.com  
// www.Not a URL.com  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [decodeURIComponent 함수](../../javascript/reference/decodeuricomponent-function-javascript.md)   
 [encodeURI 함수](../../javascript/reference/encodeuri-function-javascript.md)   
 [Global 개체](../../javascript/reference/global-object-javascript.md)