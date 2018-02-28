---
title: "encodeURIComponent 함수 (JavaScript) | Microsoft Docs"
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
- encodeURIComponent
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- encodeURIComponent method
ms.assetid: 8202bce6-1342-40dc-a5ef-ac6d210a7d15
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 56680e9bcfe1de61d8a1eabd0ff8d2eced01d603
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="encodeuricomponent-function-javascript"></a>encodeURIComponent 함수(JavaScript)
유효한 구성 요소에는 식별자 URI (Uniform Resource)으로 텍스트 문자열을 인코딩합니다.  
  
## <a name="syntax"></a>구문  
  
```  
encodeURIComponent(encodedURIString)  
```  
  
## <a name="remarks"></a>설명  
 필요한 `encodedURIString` 인수는는 인코딩된 URI 구성 요소를 나타내는 값입니다.  
  
 `encodeURIComponent` 함수 인코딩된 URI를 반환 합니다. 결과를 전달 하는 경우 `decodeURIComponent`, 원래 문자열이 반환 됩니다. 때문에 `encodeURIComponent` 함수는 모든 문자를 인코딩합니다, 문자열와 같은 경로 나타내는 경우 주의 해야 **/folder1/folder2/default.html**합니다. 슬래시 문자 인코딩할 및 웹 서버에 요청으로 전송 하는 경우에 유효 하지 않게 됩니다. 사용 하 여는 `encodeURI` 단일 URI 구성 보다 많은 문자열이 포함 하는 경우에 작동 합니다.  
  
## <a name="example"></a>예제  
 다음 코드는 먼저 URI 구성 요소를 인코딩합니다를 디코딩합니다.  
  
```JavaScript  
var uriEncode = encodeURIComponent ("www.Not a URL.com");  
var uriDecode = decodeURIComponent(uriEncode);  
  
document.write(uriEncode);  
document.write("<br/>");  
document.write(uriDecode);  
  
// Output:  
// www.Not%20a%20URL.com  
// www.Not a URL.com  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [decodeURI 함수](../../javascript/reference/decodeuri-function-javascript.md)   
 [decodeURIComponent 함수](../../javascript/reference/decodeuricomponent-function-javascript.md)