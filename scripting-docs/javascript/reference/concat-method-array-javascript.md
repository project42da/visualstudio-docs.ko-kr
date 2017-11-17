---
title: "concat 메서드 (Array) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: concat
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- concat method (array)
- Concat method
ms.assetid: bc2b4a6a-209e-4d59-8c24-59db01d53b1e
caps.latest.revision: "16"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 19f3a216a36f9ad8c422036476e46b89b6ee488c
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="concat-method-array-javascript"></a>concat 메서드(Array)(JavaScript)
두 개 이상의 배열을 결합합니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
array1.concat([item1[, item2[, . . . [, itemN]]]])   
```  
  
## <a name="parameters"></a>매개 변수  
 `array1`  
 필수 요소. `Array` 개체를 다른 배열 연결 됩니다.  
  
 `item1,. . ., itemN`  
 선택 사항입니다. 끝에 추가할 추가 항목을 `array1`합니다.  
  
## <a name="remarks"></a>설명  
 `concat` 메서드가 반환 되는 `Array` 연결을 포함 하는 개체 `array1` 및 기타 제공 된 항목입니다.  
  
 항목을 추가할 수 (*item1 itemN*) 배열에에 추가 된, 목록의 첫 번째 항목부터 순서입니다. 해당 내용을의 끝에 추가 되어 배열 항목 중 하나 이면 `array1`합니다. 항목이 포함 되지 않은 것 이면 배열의 끝에 단일 배열 요소로 추가 됩니다.  
  
 소스 배열의 요소는 다음과 같이 결과 배열에 복사 됩니다.  
  
-   새 배열에 연결 하는 배열 중 하나에서 개체를 복사 하는 경우 개체 참조가 동일한 개체를 가리키도록 계속 합니다. 새 배열 또는 원래 배열을 변경 하 고 다른 변경에 발생 합니다.  
  
-   숫자 또는 문자열 값을 새 배열에 추가 되 면 값만 복사 됩니다. 배열에 값을 변경 하는 경우에 다른 값을 적용 되지 않습니다.  
  
## <a name="example"></a>예제  
 사용 하는 방법을 보여 주는 다음 예제는 `concat` 메서드 배열와 함께 사용할 경우:  
  
```JavaScript  
var a, b, c, d;  
a = new Array(1,2,3);  
b = "dog";  
c = new Array(42, "cat");  
d = a.concat(b, c);  
document.write(d);  
  
//Output:   
1, 2, 3, "dog", 42, "cat"  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv3](../../javascript/reference/includes/jsv3-md.md)]  
  
## <a name="see-also"></a>참고 항목  
 [concat 메서드 (String)](../../javascript/reference/concat-method-string-javascript.md)   
 [join 메서드(Array)](../../javascript/reference/join-method-array-javascript.md)