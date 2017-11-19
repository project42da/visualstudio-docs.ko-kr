---
title: "String.fromCodePoint 함수 (JavaScript) | Microsoft Docs"
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
ms.assetid: 7c4c057b-c67a-4b10-afdd-4f75c7c5988c
caps.latest.revision: "3"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 0905b392606bec9fb59b08a04129ce30cb013db1
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="stringfromcodepoint-function-javascript"></a>String.fromCodePoint 함수(JavaScript)
유니코드 UTF-16 코드 포인트와 연결된 문자열을 반환합니다.  
  
## <a name="syntax"></a>구문  
  
```  
String.fromCodePoint(...codePoints);  
```  
  
#### <a name="parameters"></a>매개 변수  
 `...codePoints`  
 필수 요소. 하나 이상의 UTF-16 코드 포인트 값을 지정하는 rest 매개 변수입니다.  
  
## <a name="remarks"></a>설명  
 이 함수는  `...codePoints`가 유효한 UTF-16 코드 포인트가 아닌 경우 `RangeError` 예외를 발생시킵니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `fromCodePoint` 함수를 사용하는 방법을 보여 줍니다.  
  
```JavaScript  
var str1 = String.fromCodePoint(0x20BB7);  
var str2 = String.fromCodePoint(98);  
var str3 = String.fromCodePoint(97, 98, 99);  
  
if(console && console.log) {  
    console.log(str1);  
    console.log(str2);  
    console.log(str3);  
}  
  
// Output:  
// 𠮷  
// b  
// abc   
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]