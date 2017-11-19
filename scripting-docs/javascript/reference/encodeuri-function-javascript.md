---
title: "encodeURI 함수 (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: encodeURI
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: encodeURI method
ms.assetid: 17bab5a2-bcd4-46c2-8b52-b2b5a0ed98a3
caps.latest.revision: "12"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 8cf9bbdf34c0481c889d1176bc32ab0246a333a4
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="encodeuri-function-javascript"></a>encodeURI 함수(JavaScript)
으로 유효한 식별자 URI (Uniform Resource) 텍스트 문자열을 인코딩하십시오  
  
## <a name="syntax"></a>구문  
  
```  
  
encodeURI(  
URIString  
)  
  
```  
  
## <a name="remarks"></a>설명  
 필요한 `URIString` 인수는 인코딩된 URI를 나타내는 값입니다.  
  
 `encodeURI` 함수 인코딩된 URI를 반환 합니다. 결과를 전달 하는 경우 `decodeURI`, 원래 문자열이 반환 됩니다. `encodeURI` 함수는 다음 문자를 암호화 하지 않습니다: ":", "/", ";" 및 "?"입니다. 사용 하 여 `encodeURIComponent` 이러한 문자를 인코딩하는 데 있습니다.  
  
## <a name="example"></a>예제  
 다음 코드는 먼저 인코딩한 다음 URI를 디코딩합니다.  
  
```JavaScript  
var uriEncode = encodeURI ("http://www.Not a URL.com");  
var uriDecode = decodeURIComponent(uriEncode);  
  
document.write(uriEncode);  
document.write("<br/>");  
document.write(uriDecode);  
  
// Output:  
// http://www.Not%20a%20URL.com  
// http://www.Not a URL.com  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [decodeURI 함수](../../javascript/reference/decodeuri-function-javascript.md)   
 [decodeURIComponent 함수](../../javascript/reference/decodeuricomponent-function-javascript.md)