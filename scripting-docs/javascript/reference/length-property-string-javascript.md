---
title: "length 속성 (String) (JavaScript) | Microsoft Docs"
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
- length Property
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- strings [Visual Studio], length
- Length property
- length property (String)
ms.assetid: 7dbd4a0e-c24e-4561-9b5b-e75e649a10a4
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 706a7f6986086f95613e09b9a8355eb5bc2702a7
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="length-property-string-javascript"></a>length 속성(String)(JavaScript)
`String` 개체의 길이를 반환합니다.  
  
> [!WARNING]
>  JavaScript 문자열을 변경할 수 있는 되지 않으므로 문자열의 길이 수정할 수 없습니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
      strVariable.length  
"String Literal".length   
```  
  
## <a name="remarks"></a>설명  
 `length` 에 있는 문자의 수를 나타내는 정수를 포함 하는 속성은 `String` 개체입니다. 마지막 문자는 `String` 개체의 인덱스는 i`length` -1입니다.  
  
## <a name="example"></a>예제  
 다음 코드를 사용 하는 방법을 보여 줍니다 `length`합니다. JavaScript 변경할 수 없는 문자열과 현재 위치에서 수정할 수 없습니다. 그러나 역방향된 문자열 배열로 작성 하 고 다음 호출 수 `join` 구분 기호 문자가 없는 string 빈 문자를 생성 합니다.  
  
```JavaScript  
var str = "every good boy does fine";  
        var start = 0;  
        var end = str.length - 1;  
        var tmp = "";  
        var arr = new Array(end);  
  
        while (end >= 0) {  
            arr[start++] = str.charAt(end--);  
        }  
  
// Join the elements of the array with a   
        var str2 = arr.join('');  
        document.write(str2);  
  
// Output: enif seod yob doog yreve  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]