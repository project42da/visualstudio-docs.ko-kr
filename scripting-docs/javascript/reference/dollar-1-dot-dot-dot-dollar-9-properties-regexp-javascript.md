---
title: "$1... $9 속성 (RegExp) (JavaScript) | Microsoft Docs"
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
- $1...$9
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- $1...$9 properties
ms.assetid: 8bd84851-f62f-4eb1-a93d-b67135ea091a
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: fc1926d6281c9003c432c9c9e89a73a48a584ef4
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="19-properties-regexp-javascript"></a>$1...$9 속성(RegExp)(JavaScript)
9 개 가장 최근에 찾아 저장 한 패턴 일치 하는 동안 부분을 반환 합니다. 읽기 전용입니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
RegExp.$n   
```  
  
## <a name="parameters"></a>매개 변수  
 `RegExp`  
 항상 전역 `RegExp` 개체입니다.  
  
 `n`  
 1에서 9 사이의 모든 정수입니다.  
  
## <a name="remarks"></a>설명  
 값은 **$1... $9** 때마다 괄호 일치 하는 속성이 수정 됩니다. 정규식 패턴에 괄호로 묶인 부분 문자열 수를 지정할 수 있지만 가장 최근 9만 저장할 수 있습니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 정규식 검색을 수행합니다. 일치 항목을 표시 하 고 전역에서 submatches `RegExp` 개체입니다. 부분 일치에 포함 된 괄호 일치 하는 `$1...$9` 속성입니다. 이 예제에서는 또한 일치 항목을 표시 하 고에서 반환 되는 배열에서 submatches는 `exec` 메서드.  
  
```JavaScript  
var newLine = "<br />";  
  
var re = /(\w+)@(\w+)\.(\w+)/g  
var src = "Please send mail to george@contoso.com and someone@example.com. Thanks!"  
  
var result;  
var s = "";  
  
// Get the first match.  
result = re.exec(src);  
  
while (result != null) {  
    // Show the entire match.  
    s += newLine;  
  
    // Show the match and submatches from the RegExp global object.  
    s += "RegExp.lastMatch: " + RegExp.lastMatch + newLine;  
    s += "RegExp.$1: " + RegExp.$1 + newLine;  
    s += "RegExp.$2: " + RegExp.$2 + newLine;  
    s += "RegExp.$3: " + RegExp.$3 + newLine;  
  
    // Show the match and submatches from the array that is returned  
    // by the exec method.  
    for (var index = 0; index < result.length; index++) {  
        s +=  index + ": ";  
        s += result[index];  
        s += newLine;  
    }  
  
    // Get the next match.  
    result = re.exec(src);  
}  
document.write(s);  
  
// Output:  
//  RegExp.lastMatch: george@contoso.com  
//  RegExp.$1: george  
//  RegExp.$2: contoso  
//  RegExp.$3: com  
//  0: george@contoso.com  
//  1: george  
//  2: contoso  
//  3: com  
  
//  RegExp.lastMatch: someone@example.com  
//  RegExp.$1: someone  
//  RegExp.$2: example  
//  RegExp.$3: com  
//  0: someone@example.com  
//  1: someone  
//  2: example  
//  3: com  
  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **적용 대상**: [RegExp 개체](../../javascript/reference/regexp-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [정규식 구문 (JavaScript)](http://msdn.microsoft.com/en-us/ab0766e1-7037-45ed-aa23-706f58358c0e)