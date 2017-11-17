---
title: "includes 메서드 (String) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- JavaScript
- TypeScript
- DHTML
ms.assetid: 2639e4e5-23ba-424a-80ea-be067a4cd65e
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 848143b64d3e32452aea41f08b6f5c57879d3e17
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="includes-method-string-javascript"></a>includes 메서드(String)(JavaScript)
전달된 문자열이 문자열 개체에 포함되어 있는지 여부를 나타내는 부울 값을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
stringObj.includes(substring [, position]);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `stringObj`  
 필수 요소. 테스트할 문자열 개체입니다.  
  
 `substring`  
 필수 요소. 테스트할 문자열입니다.  
  
 `position`  
 선택 사항입니다. 문자열 개체에서 테스트 기준으로 사용할 첫 번째 문자의 위치로, 0부터 시작합니다.  
  
## <a name="return-value"></a>반환 값  
 전달된 문자열이 문자열 개체에 포함되어 있으면 `includes` 메서드에서 `true`를 반환합니다. 그렇지 않으면 `false`를 반환합니다.  
  
## <a name="remarks"></a>설명  
  
## <a name="example"></a>예제  
  
```JavaScript  
// Returns true   
"abcde".includes("cd")  
"abcde".includes("cd", 2)  
  
// Returns false  
"abcde".includes("CD")  
"abcde".includes("cd", 3)  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]