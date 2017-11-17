---
title: "indexOf 메서드 (String) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: indexOf
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- indexOf method, string
- string, indexOf method
ms.assetid: a17372fa-669b-471b-9240-46927a265152
caps.latest.revision: "18"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ecd96acb21f9d7711f9ee00dbf1c1bb70705c0d8
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="indexof-method-string-javascript"></a>indexOf 메서드(String)(JavaScript)
처음으로 나오는 부분 문자열의 위치를 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
strObj. indexOf(subString[, startIndex])  
```  
  
## <a name="parameters"></a>매개 변수  
 `strObj`  
 필수 요소. A `String` 개체 또는 문자열 리터럴입니다.  
  
 `subString`  
 필수 요소. 문자열에서 검색할 부분 문자열입니다.  
  
 `startIndex`  
 선택 사항입니다. `String` 개체의 검색을 시작할 인덱스입니다. 생략하면 문자열의 처음부터 검색을 시작합니다.  
  
## <a name="remarks"></a>설명  
 **indexOf** 에 부분 문자열의 시작 부분을 반환 하는 메서드는 `String` 개체입니다. 부분 문자열이 없으면 -1이 반환됩니다.  
  
 `startindex`가 음수이면 `startindex`는 0으로 처리되고, startindex가 가장 큰 인덱스보다 크면 가장 큰 인덱스로 처리됩니다.  
  
 검색은 왼쪽에서 오른쪽으로 수행됩니다. 그렇지 않으면이 메서드는 동일 **lastIndexOf**합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 **indexOf** 메서드.  
  
```JavaScript  
var str = "original equipment manufacturer";  
  
var s = "equip is at position " + str.indexOf("equip");  
s += "<br />";  
s += "abc is at position " + str.indexOf("abc");  
  
document.write(s);  
  
// Output:  
// equip is at position 9  
// abc is at position -1  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **적용 대상**: [문자열 개체](../../javascript/reference/string-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [lastIndexOf 메서드 (String)](../../javascript/reference/lastindexof-method-string-javascript.md)   
 [샘플 앱 스크롤, 이동 및 확대/축소](http://code.msdn.microsoft.com/ie/Scrolling-panning-and-6834aaf9)