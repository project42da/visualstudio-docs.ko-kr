---
title: "multiline 속성 (Regular Expression) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: multiline
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: multiline property
ms.assetid: ca7b276a-1fe2-4189-ac27-f089ab3e9974
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 289cb8d8e103d8c4ac1b1ef06714105d21cba743
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="multiline-property-regular-expression-javascript"></a>multiline 속성(Regular Expression)(JavaScript)
여러 줄로 된 플래그의 상태를 나타내는 부울 값을 반환 합니다 (**m**) 정규식 함께 사용 합니다. 기본값은 **false**합니다. 읽기 전용입니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
rgExp.multiline  
```  
  
## <a name="remarks"></a>설명  
 필요한 `rgExp` 인수가의 인스턴스는 `RegExp` 개체  
  
 **여러 줄** 속성에서 반환 **true** 경우 여러 줄로 된 플래그는 정규식에 대 한 설정 되 고이 반환 하는 **false** 없는 경우. **여러 줄** 속성은 **true** 정규식 개체를 만든 경우의 **m** 플래그입니다.  
  
 경우 **여러 줄** 은 **false**, "^" 문자열과 일치 하는 "$" 항목의 시작 부분에 위치는 문자열의 끝에서 위치를 찾습니다. 경우 **여러 줄** 은 **true**, "^" "\n" 또는 "\r" 및 "$"을 다음 위치에는 문자열의 끝에 있는 위치와 일치 하 고 "\n 앞 위치 문자열의 시작 부분에 위치와 일치 "또는"\r"입니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는의 동작을 보여 줍니다.는 **여러 줄** 속성입니다. 단어 "while" 라는 단어로 대체 됩니다 "m"에 아래 표시 된 함수에 전달 하면 "및". 이 여러 줄 플래그로 설정 되어 있기 때문 이므로 단어 "while" 줄 바꿈 문자 이후에 줄의 시작 부분에서 발생 합니다. 여러 줄 플래그 검색을을 여러 줄 문자열에서 수행할 수 있습니다.  
  
```JavaScript  
function RegExpMultilineDemo(flag){  
   // The flag parameter is a string that contains  
   // g, i, or m.  The flags can be combined.  
  
   // Check flags for validity.  
   if (flag.match(/[^gim]/))  
      {  
      return ("Flag specified is not valid");  
      }  
  
   // Create the string on which to perform the replacement.  
   var ss = "The man hit the ball with the bat ";  
   ss += "\nwhile the fielder caught the ball with the glove.";  
  
   // Replace "while" with "and".  
   var re = new RegExp("^while", flag);  
   var r = ss.replace(re, "and");          
  
   // Output the multiline flag and the resulting string.  
   var s = "";  
   s += "Result for multiline = " + re.multiline.toString();  
   s += ": " + r;  
  
   return(s);  
  
}  
  
sa = RegExpMultilineDemo("m");  
sb = RegExpMultilineDemo("");  
document.write (sa + "<br />" + sb);  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
 **적용 대상**: [Regular Expression 개체](../../javascript/reference/regular-expression-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [global 속성 (Regular Expression)](../../javascript/reference/global-property-regular-expression-javascript.md)   
 [ignoreCase 속성 (Regular Expression)](../../javascript/reference/ignorecase-property-regular-expression-javascript.md)   
 [정규식 구문 (JavaScript)](http://msdn.microsoft.com/en-us/ab0766e1-7037-45ed-aa23-706f58358c0e)