---
title: "global 속성 (Regular Expression) (JavaScript) | Microsoft Docs"
ms.custom: 
ms.date: 01/18/2017
ms.prod: windows-client-threshold
ms.reviewer: 
ms.suite: 
ms.technology: devlang-javascript
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: Global
dev_langs:
- JavaScript
- TypeScript
- DHTML
helpviewer_keywords: global property
ms.assetid: 76a0f115-0d89-4aca-86d5-932895c6d649
caps.latest.revision: "19"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7e2b0256fea60b7ab998c504e79565fc7028cd98
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="global-property-regular-expression-javascript"></a>global 속성(Regular Expression)(JavaScript)
전역 플래그의 상태를 나타내는 부울 값을 반환 (**g**) 정규식 함께 사용 합니다. 기본값은 **false**합니다. 읽기 전용입니다.  
  
## <a name="syntax"></a>구문  
  
```  
  
rgExp.global  
```  
  
## <a name="remarks"></a>설명  
 필요한 `rgExp` 참조의 인스턴스가 **정규식** 개체입니다.  
  
 `global` 속성에서 반환 **true** 경우 전역 플래그는 정규식에 대 한 설정 되 고이 반환 하는 **false** 없는 경우.  
  
 전역 플래그를 사용 하면 검색 패턴 검색된 된 첫 번째 뿐 아니라 문자열 내에서 모든 항목을 찾을 해야 나타냅니다. 이 일치 하는 전역 라고도 합니다.  
  
## <a name="example"></a>예제  
 다음 예제에서는 `global` 속성입니다. 전달 하는 경우 **g** 아래 표시 된 함수에는 단어의 모든 인스턴스 "the" 대체 단어 "a"입니다. 확인 하는 "The" 시작 부분에서 문자열의 바뀌지 않습니다는 **i** (대/소문자 무시) 플래그는 함수에 전달 되지 않습니다.  
  
 이 함수는 허용 가능한 정규식 플래그와 연결 된 속성의 조건이 표시 **g**, **i**, 및 **m**합니다. 함수는 또한 모든 대체가 수행 된 문자열을 표시 합니다.  
  
```JavaScript  
function RegExpPropDemo(flag){  
   // The flag parameter is a string that contains  
   // g, i, or m.  The flags can be combined.  
  
   // Check flags for validity.  
   if (flag.match(/[^gim]/))  
      {  
      return ("Flag specified is not valid");  
      }  
  
   // Create the string on which to perform the replacement.  
   var ss = "The batter hit the ball with the bat ";  
   ss += "and the fielder caught the ball with the glove.";  
  
   //Replace "the" with "a".  
   var re = new RegExp("the", flag);  
   var r = ss.replace(re, "a");          
  
   // Output the resulting string and the flags.  
   var s = "";  
   s += "global: " + re.global.toString();  
   s += "<br />";  
   s += "ignoreCase: " + re.ignoreCase.toString();  
   s += "<br />";  
   s += "multiline: " + re.multiline.toString();  
   s += "<br />";  
   s += "Resulting String: " + r;  
  
   return (s);  
}  
  
document.write(RegExpPropDemo("g"));  
```  
  
## <a name="example"></a>예제  
 다음은 결과입니다.  
  
```JavaScript  
global: true  
ignoreCase: false  
multiline: false  
Resulting String: The batter hit a ball with a bat and a fielder caught a ball with a glove.  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
 **적용 대상**: [Regular Expression 개체](../../javascript/reference/regular-expression-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [ignoreCase 속성 (Regular Expression)](../../javascript/reference/ignorecase-property-regular-expression-javascript.md)   
 [multiline 속성 (Regular Expression)](../../javascript/reference/multiline-property-regular-expression-javascript.md)   
 [정규식 구문 (JavaScript)](http://msdn.microsoft.com/en-us/ab0766e1-7037-45ed-aa23-706f58358c0e)