---
title: "split 메서드 (String) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: split
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: split method
ms.assetid: 7f093336-c887-4efb-b91f-819b6d18a181
caps.latest.revision: "17"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: eea90dda2e8e4d52451af247d139eeee44f83917
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="split-method-string-javascript"></a>split 메서드(String)(JavaScript)
지정된 구분 기호를 사용하여 문자열을 부분 문자열로 분할하고 배열로 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
stringObj.split([separator[, limit]])  
```  
  
## <a name="parameters"></a>매개 변수  
 `stringObj`  
 필수 요소. 분할할 `String` 개체 또는 문자열 리터럴입니다. 이 개체에서 수정 되지 않습니다는 **분할** 메서드.  
  
 `separator`  
 선택 사항입니다. 문자열 또는 **정규식** 문자 또는 문자열을 구분 사용할 문자를 식별 하는 개체입니다. 생략하면 전체 문자열을 포함하는 단일 요소 배열이 반환됩니다.  
  
 `limit`  
 선택 사항입니다. 배열로 반환되는 요소의 수를 제한하는 값입니다.  
  
## <a name="return-value"></a>반환 값  
 결과 **분할** 메서드는 각 지점에서 분할 하는 문자열의 배열을 여기서 `separator` 에서 발생 `stringObj`합니다. `separator`는 어느 배열의 요소로도 반환되지 않습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 **분할** 메서드.  
  
```JavaScript  
var s = "The quick brown fox jumps over the lazy dog.";  
var ss = s.split(" ");  
for (var i in ss) {  
    document.write(ss[i]);  
    document.write("<br/>");  
}  
  
// Output:   
// The  
// quick  
// brown  
// fox  
// jumps  
// over  
// the  
// lazy  
// dog.  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
 **적용 대상**: [문자열 개체](../../javascript/reference/string-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [concat 메서드 (String)](../../javascript/reference/concat-method-string-javascript.md)   
 [RegExp 개체](../../javascript/reference/regexp-object-javascript.md)   
 [Regular Expression 개체](../../javascript/reference/regular-expression-object-javascript.md)   
 [정규식 구문 (JavaScript)](http://msdn.microsoft.com/en-us/ab0766e1-7037-45ed-aa23-706f58358c0e)   
 [샘플 앱 스크롤, 이동 및 확대/축소](http://code.msdn.microsoft.com/ie/Scrolling-panning-and-6834aaf9)