---
title: "endsWith 메서드 (String) (JavaScript) | Microsoft Docs"
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
ms.assetid: c7d836e3-bc43-4d1b-be60-0a93beb8b7a2
caps.latest.revision: "2"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: dc6d57d501f0f100f069522e4b51666918168fa0
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="endswith-method-string-javascript"></a>endsWith 메서드(String)(JavaScript)
문자열 또는 하위 문자열이 다른 지정된 문자열로 끝나는지 여부를 나타내는 값을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```vb  
  
stringObj.endsWith(str, [, position]);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `stringObj`  
 필수 요소. 검색 기준으로 사용할 문자열 개체입니다.  
  
 `str`  
 필수 요소. 검색 문자열입니다.  
  
 `position`  
 선택 사항입니다. 문자열 개체에서 검색 기준으로 사용할 첫 번째 문자의 위치입니다(0부터 시작).  
  
## <a name="return-value"></a>반환 값  
 `position`에서 시작하는 문자열이 검색 문자열로 끝나면 `endsWith` 메서드는 `true`를 반환하고, 그렇지 않으면 `false`를 반환합니다.  
  
## <a name="exceptions"></a>예외  
 `str`이 `RegExp`이면 `TypeError`가 throw됩니다.  
  
## <a name="remarks"></a>설명  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]