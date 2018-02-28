---
title: "substring 메서드 (String) (JavaScript) | Microsoft Docs"
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
- substring
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- substrings
- substring method
ms.assetid: 9cf9a005-cbe3-42fd-828b-57a39f54224c
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 15ebaadc7b24fa97f531a22f6deb1453ff52b3e7
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="substring-method-string-javascript"></a>substring 메서드(String)(JavaScript)
내에서 지정 된 위치의 부분 문자열을 반환는 `String` 개체입니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      strVariable. substring(start [, end])  
"String Literal".substring(start [, end])   
```  
  
## <a name="parameters"></a>매개 변수  
 `start`  
 필수 요소. 부분 문자열의 시작 부분을 나타내는 0부터 시작 인덱스입니다.  
  
 `end`  
 선택적 요소. 문자열의 끝을 나타내는 0부터 시작 인덱스입니다. 부분 문자열에 문자를까지 포함 되어 있지만 까지만으로 표시 되는 문자 `end`합니다.  
  
 경우 `end` 를 생략 하면에서 문자 `start` 원래 문자열의 끝까지 반환 됩니다.  
  
## <a name="remarks"></a>설명  
 `substring` 의 부분 문자열을 포함 하는 문자열을 반환 하는 메서드 `start` 포함 하지 않고 까지의 `end`합니다.  
  
 **부분 문자열** 메서드의 더 낮은 값을 사용 하 여 `start` 및 `end` 부분 문자열의 시작 지점으로 합니다. 예를 들어 strvar.substring (0, 3**)** 및 (3, 0) strvar.substring 동일한 부분 문자열을 반환 합니다.  
  
 경우 `start` 또는 `end` 은 `NaN` 또는 0으로 대체 음수 이면 됩니다.  
  
 부분 문자열의 길이 절대 값의 차이 `start` 및 `end`합니다. 예를 들어 strvar.substring (0, 3)에서 반환 되는 부분 문자열의 길이 및 strvar.substring (3, 0)는 3 개입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 **부분 문자열** 메서드.  
  
```JavaScript  
var s = "The quick brown fox jumps over the lazy dog.";  
var ss = s.substring(10, 15);  
document.write(ss);  
  
// Output:  
// brown  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [substr 메서드(String)](../../javascript/reference/substr-method-string-javascript.md)