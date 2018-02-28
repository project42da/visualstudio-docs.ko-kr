---
title: "escape 함수 (JavaScript) | Microsoft Docs"
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
- escape
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- encoding string objects
- Escape method
- hexadecimal
- String object, encoding
ms.assetid: caa92bea-ba69-4109-a68a-6e2debda463a
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b53a447ae6dde917c12a4711d9038136dc4500cf
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="escape-function-javascript"></a>escape 함수(JavaScript)
모든 컴퓨터에서 읽을 수 있도록 문자열을 인코딩합니다. 더 이상 사용되지 않습니다.  
  
## <a name="syntax"></a>구문  
  
```  
escape(charString)   
```  
  
## <a name="remarks"></a>설명  
 필요한 `charString` 모든 인수는 `String` 개체 또는 인코딩할 수 리터럴입니다.  
  
 **이스케이프** 함수 반환 형식으로 나타낸 유니코드의 내용을 포함 하는 문자열 값 `charstring`합니다. 악센트 부호가 있는 문자를 문장 부호, 모든 공백 및 기타 비 ASCII 문자가으로 바뀝니다 `%` *xx* 인코딩, 여기서 *xx* 해당 16 진수 숫자 나타내는 하는 문자입니다. "%20."으로 공백은 반환 하는 예를 들어  
  
 값이 255를 사용 하 여 저장 된 보다 큰 문자는 **%u** *xxxx* 형식입니다.  
  
> [!NOTE]
>  **이스케이프** 함수 식별자 URI (Uniform Resource)을 인코딩하는 데 사용 해야 합니다. 사용 하 여 `encodeURI` 및 `encodeURIComponent` 대신 작동 합니다.  
  
 **적용 대상**: [전역 개체](../../javascript/reference/global-object-javascript.md)  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [encodeURI 함수](../../javascript/reference/encodeuri-function-javascript.md)   
 [encodeURIComponent 함수](../../javascript/reference/encodeuricomponent-function-javascript.md)   
 [String 개체](../../javascript/reference/string-object-javascript.md)   
 [unescape 함수](../../javascript/reference/unescape-function-javascript.md)