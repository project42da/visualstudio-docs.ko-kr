---
title: "rightContext 속성 ($&#39;) (RegExp) (JavaScript) | Microsoft Docs"
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
- $'
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- rightContext property ($')
ms.assetid: 6999c056-d18c-4583-9dd9-8fbb6d3d0ee7
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d47ea5dd67de9d73ab59b615c567ad3a7a96fb7b
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="rightcontext-property-39-regexp-javascript"></a>rightContext 속성 ($&#39;) (RegExp) (JavaScript)
마지막 일치 항목이 검색된 되는 문자열의 끝에 다음 위치에서 문자를 반환 합니다. 읽기 전용입니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
RegExp.rightContext  
```  
  
## <a name="remarks"></a>설명  
 이 속성에 연결 된 개체는 항상 전역 `RegExp` 개체입니다.  
  
 초기 값은 **rightContext** 속성은 빈 문자열입니다. 값은 **rightContext** 속성이 변경 될 때마다 성공적으로 일치 하는 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 **rightContext** 속성:  
  
```JavaScript  
// Create the regular expression pattern.  
var re = new RegExp("d(b+)(d)","ig");  
var str = "cdbBdbsbdbdz";  
  
// Perform the search.  
var arr = re.exec(str);  
  
// Print the output.  
var s = ""   
s += "$1: " + RegExp.$1 + "<br />";  
s += "$2: " + RegExp.$2 + "<br />";  
s += "$3: " + RegExp.$3 + "<br />";  
s += "input: " + RegExp.input + "<br />";  
s += "lastMatch: " + RegExp.lastMatch + "<br />";  
s += "leftContext: " + RegExp.leftContext + "<br />";  
s += "rightContext: " + RegExp.rightContext + "<br />";   
s += "lastParen: " + RegExp.lastParen + "<br />";  
  
document.write(s);  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
 **적용 대상**: [RegExp 개체](../../javascript/reference/regexp-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [$1... $9 속성 (RegExp)](../../javascript/reference/dollar-1-dot-dot-dot-dollar-9-properties-regexp-javascript.md)   
 [index 속성 (RegExp)](../../javascript/reference/index-property-regexp-javascript.md)   
 [input 속성 ($_) (RegExp)](../../javascript/reference/input-property-dollar-regexp-javascript.md)   
 [lastIndex 속성 (RegExp)](../../javascript/reference/lastindex-property-regexp-javascript.md)   
 [lastMatch 속성 ($&) (RegExp)](../../javascript/reference/lastmatch-property-dollar-regexp-javascript.md)   
 [lastParen 속성 ($ +) (RegExp)](../../javascript/reference/lastparen-property-dollar-regexp-javascript.md)   
 [leftContext 속성($`)(RegExp)](../../javascript/reference/leftcontext-property-dollar-grave-regexp-javascript.md)