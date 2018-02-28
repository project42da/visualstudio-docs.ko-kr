---
title: "ignoreCase 속성 (Regular Expression) (JavaScript) | Microsoft Docs"
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
- ignoreCase
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords:
- IgnoreCase property
ms.assetid: 816f0df5-5a82-44a5-a4ab-dbc91fa76e61
caps.latest.revision: 
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: ae9fee8e6303fb944f59c11c173f9e8b7f7cc75a
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="ignorecase-property-regular-expression-javascript"></a>ignoreCase 속성(Regular Expression)(JavaScript)
IgnoreCase 플래그의 상태를 나타내는 부울 값을 반환 합니다 (**i**) 정규식 함께 사용 합니다. 기본값은 **false**합니다. 읽기 전용입니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
rgExp.ignoreCase  
```  
  
## <a name="remarks"></a>설명  
 필요한 `rgExp` 참조의 인스턴스가 `RegExp` 개체입니다.  
  
 **ignoreCase** 속성에서 반환 **true** ignoreCase 플래그는 정규식에 대 한 설정 되 고 반환 **false** 없는 경우.  
  
 IgnoreCase 플래그를 사용 하는 경우 검색된 문자열 내의 패턴과 일치 하는 경우 대/소문자를 무시 합니다 있는지를 나타냅니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 **ignoreCase** 속성입니다. "Gi"에 아래 표시 된 함수에 전달 하면 단어의 모든 인스턴스가 "the" 대체 단어로 초기를 포함 하 여 "a", "The"입니다. 즉, 검색 ignoreCase 플래그 집합과 함께 모든 대/소문자 구분을 무시 합니다. "따라서 T"는 "t"와 동일 하 게 일치에 대 한입니다.  
  
 이 함수는 허용 가능한 정규식 플래그의 상태를 나타내는 부울 값을 반환 **g**, **i**, 및 **m**합니다. 함수는 또한 모든 대체가 수행 된 문자열을 반환 합니다.  
  
```JavaScript  
function RegExpPropDemo(flag){  
    // The flag parameter is a string that contains  
    // g, i, or m. The flags can be combined.  
  
    // Check flags for validity.  
    if (flag.match(/[^gim]/))  
        {  
        return ("Flag specified is not valid");  
        }  
  
    // Create the string on which to perform the replacement.  
    var orig = "The batter hit the ball with the bat ";  
    orig += "and the fielder caught the ball with the glove.";  
  
    // Replace "the" with "a".  
    var re = new RegExp("the", flag);  
    var r = orig.replace(re, "a");          
  
    // Output the resulting string and the values of the flags.  
    var s = "";  
    s += "global: " + re.global.toString();  
    s += "<br />";  
    s += "ignoreCase: " + re.ignoreCase.toString();  
    s += "<br />";  
    s += "multiline: " + re.multiline.toString();  
    s += "<br />";  
    s += "Resulting String: " + r;  
    s += "<br />";  
    s += "<br />";  
    return (s);  
}  
  
document.write(RegExpPropDemo("gi"));  
document.write(RegExpPropDemo("g"));  
```  
  
## <a name="example"></a>예제  
 다음은 결과입니다.  
  
```JavaScript  
global: true  
ignoreCase: true  
multiline: false  
Resulting String: a batter hit a ball with a bat and a fielder caught a ball with a glove.  
  
global: true  
ignoreCase: false  
multiline: false  
Resulting String: The batter hit a ball with a bat and a fielder caught a ball with a glove.  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
 **적용 대상**: [Regular Expression 개체](../../javascript/reference/regular-expression-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [global 속성 (Regular Expression)](../../javascript/reference/global-property-regular-expression-javascript.md)   
 [multiline 속성 (Regular Expression)](../../javascript/reference/multiline-property-regular-expression-javascript.md)   
 [정규식 구문 (JavaScript)](http://msdn.microsoft.com/en-us/ab0766e1-7037-45ed-aa23-706f58358c0e)