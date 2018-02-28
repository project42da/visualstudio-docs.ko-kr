---
title: "lastIndexOf 메서드 (String) (JavaScript) | Microsoft Docs"
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
- lastIndexOf
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- lastIndexOf method, string
- string, lastIndexOf method
ms.assetid: 1ed36ccd-0f0b-4f16-be45-0567207670af
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0fa0f35e970435a4d0296493c20afdeaac128cae
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="lastindexof-method-string-javascript"></a>lastIndexOf 메서드(String)(JavaScript)
문자열의 부분 문자열의 마지막 항목을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
strObj.lastIndexOf(substring[, startindex])  
```  
  
## <a name="parameters"></a>매개 변수  
 `strObj`  
 필수 요소. `String` 개체 또는 문자열 리터럴입니다.  
  
 `substring`  
 필수 요소. 검색할 부분 문자열입니다.  
  
 `startindex`  
 선택 사항입니다. 검색을 시작할 인덱스입니다. 생략 하는 경우 검색 문자열의 끝에서 시작 됩니다.  
  
## <a name="remarks"></a>설명  
 **lastIndexOf** 에 부분 문자열의 시작 부분을 나타내는 정수 값을 반환 하는 메서드는 `String` 개체입니다. 부분 문자열이 없으면-1이 반환 됩니다.  
  
 `startindex`가 음수이면 `startindex`는 0으로 처리되고, 가장 큰 문자 위치 인덱스 보다 큰 경우에 사용할 수 있는 가장 큰 인덱스로 처리 됩니다.  
  
 검색 문자열의 마지막 문자에서 시작이 수행 됩니다. 그렇지 않으면이 메서드는 동일 **indexOf**합니다.  
  
 다음 예제에서는 **lastIndexOf** 메서드.  
  
```JavaScript  
var str = "time, time";  
  
var s = "";  
s += "time is at position " + str.lastIndexOf("time");  
s += "<br />";  
s += "abc is at position " + str.lastIndexOf("abc");  
  
document.write(s);  
  
// Output:  
// time is at position 6  
// abc is at position -1  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **적용 대상**: [문자열 개체](../../javascript/reference/string-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [indexOf 메서드(String)](../../javascript/reference/indexof-method-string-javascript.md)