---
title: "unescape 함수 (JavaScript) | Microsoft Docs"
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
- unescape
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- Unescape method
ms.assetid: 4adf0270-88b5-4d54-8110-d879d6ae97c2
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 96601fc21f47c86aec8c3702a6861c3676aacacf
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="unescape-function-javascript"></a>unescape 함수(JavaScript)
디코딩합니다 `String` 개체로 인코딩하여는 `escape` 함수입니다. 더 이상 사용되지 않습니다.  
  
## <a name="syntax"></a>구문  
  
```  
unescape(charString)   
```  
  
## <a name="remarks"></a>설명  
 필요한 `charString` 인수가 `String` 개체 또는 디코딩할 수 리터럴입니다.  
  
 `unescape` 의 내용을 포함 하는 문자열 값을 반환 하는 함수 `charstring`합니다. %로 인코딩된 문자는 모든*xx* 16 진수 형식 해당 ascii 문자 집합으로 대체 됩니다.  
  
 에 인코딩된 문자 **%u** *xxxx* 16 진수 인코딩을 사용 하 여 유니코드 문자 형식 (유니코드 문자)가 바뀝니다 *xxxx*합니다.  
  
> [!NOTE]
>  `unescape` 식별자 URI (Uniform Resource) 디코딩할 함수를 사용 해야 합니다. 사용 하 여 `decodeURI` 및 `decodeURIComponent` 대신 작동 합니다.  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **적용 대상**: [전역 개체](../../javascript/reference/global-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [decodeURI 함수](../../javascript/reference/decodeuri-function-javascript.md)   
 [decodeURIComponent 함수](../../javascript/reference/decodeuricomponent-function-javascript.md)   
 [escape 함수](../../javascript/reference/escape-function-javascript.md)   
 [String 개체](../../javascript/reference/string-object-javascript.md)