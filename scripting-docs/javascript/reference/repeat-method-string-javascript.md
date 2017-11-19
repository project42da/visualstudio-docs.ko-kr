---
title: "repeat 메서드 (String) (JavaScript) | Microsoft Docs"
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
ms.assetid: fe02cdfd-f0f6-45a2-ad36-31c4300ef142
caps.latest.revision: "4"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: b1a3d6edce877a97b0e46a69c43b667231c26981
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="repeat-method-string-javascript"></a>repeat 메서드(String)(JavaScript)
지정된 횟수만큼 반복되는 원래 문자열과 같은 값과 함께 새 문자열 개체를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
stringObj.repeat(count);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `stringObj`  
 필수 요소. 문자열 개체입니다.  
  
 `count`  
 필수 요소. 반환된 문자열에서 원래 문자열을 반복할 횟수입니다.  
  
## <a name="exceptions"></a>예외  
 이 메서드는 인수가 음수이거나 +Infinity인 경우에만 RangeError를 throw합니다.  
  
## <a name="remarks"></a>설명  
 `repeat` 메서드는 `count`에 지정된 횟수만큼 원래 문자열을 새 문자열에 연결합니다.  
  
 이 메서드는 `count`가 `Infinity`보다 작은 양수가 아닐 경우 오류를 throw합니다.  
  
## <a name="example"></a>예제  
  
```JavaScript  
"abc".repeat(3); // Returns "abcabcabc"  
"abc".repeat(0); // Returns an empty string.  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]