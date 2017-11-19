---
title: "HTML 태그 메서드 (JavaScript) | Microsoft Docs"
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
helpviewer_keywords:
- link method [JavaScript]
- blink method [JavaScript]
- fontsize method [JavaScript]
- italics method [JavaScript]
- sup method [JavaScript]
- anchor method [JavaScript]
- fixed method [JavaScript]
- fontcolor method [JavaScript]
- bold method [JavaScript]
- small method [JavaScript]
- HTML Tag methods [JavaScript]
- sub method [JavaScript]
- big method [JavaScript]
ms.assetid: 50376223-be95-4aa4-9147-9e738a5d3cfa
caps.latest.revision: "15"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 7639bc609d8e9b7e4b212fe67ae40f81487d708e
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="html-tag-methods-javascript"></a>HTML 태그 메서드(JavaScript)
HTML 태그 메서드를 사용 하 여 HTML 요소에 텍스트를 배치할 수는 `String` 개체입니다.  
  
## <a name="syntax"></a>구문  
 다음 표에서에 대 한 구문 및 각 HTML 태그 방법에 대 한 설명을 나열합니다.  
  
 구문 열에서 `string1` 는 `String` 개체 또는 리터럴입니다.  
  
 표준 열 표시 [World Wide Web Consortium (W3C)](http://go.microsoft.com/fwlink/?LinkId=199553) HTML 4에 대 한 권장 사항입니다. "권장 되지 않습니다" 스타일 시트를 위해 HTML 요소가 권장 되지 않습니다 나타냅니다.  
  
|구문|메서드 설명|매개 변수 설명|표준|  
|------------|------------------------|---------------------------|--------------|  
|`string1`.anchor (`name`)|텍스트를 둘러싸는 이름 특성을 가진 HTML 앵커를 삽입 합니다.|`name` 매개 변수는 HTML 앵커의 이름 특성에 배치할 텍스트입니다.||  
|`string1`.big()|에서는 HTML \<큰 > 텍스트 태그입니다.||권장 되지 않음|  
|`string1`.blink()|에서는 HTML \<BLINK > 텍스트 태그입니다. \<BLINK > Internet Explorer에서 태그를 사용할 수 없습니다.||Standard에 없는|  
|`string1`.bold()|에서는 HTML \<B > 텍스트 태그입니다.||권장 되지 않음|  
|`string1`.fixed()|에서는 HTML \<TT > 텍스트 태그입니다.||권장 되지 않음|  
|`string1`.fontcolor (`color`)|에서는 HTML \<글꼴 > 텍스트를 둘러싸는 COLOR 특성을 가진 태그입니다.|`color` 매개 변수는 16 진수 값 또는 미리 정의 된 색 이름을 포함 하는 문자열 값입니다. 에 유효한 미리 정의 된 색 이름을 종속는 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 브라우저와 해당 버전을 호스트 합니다.|사용 되지 않음|  
|`string1`.fontsize (`size`)|에서는 HTML \<글꼴 > 텍스트 주위의 크기 특성으로 태그입니다.|`size` 매개 변수는 텍스트의 크기를 지정 하는 정수 값입니다. 유효한 정수 값에 따라 달라 집니다는 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 브라우저와 해당 버전을 호스트 합니다.|사용 되지 않음|  
|`string1`.italics()|에서는 HTML \<I > 텍스트 태그입니다.||권장 되지 않음|  
|`string1`.link (`href`)|텍스트를 둘러싸는 HREF 특성을 가진 HTML 앵커를 삽입 합니다.|`href` 매개 변수는 HTML 앵커의 HREF 특성에 배치할 텍스트입니다.||  
|`string1`.small()|에서는 HTML \<작은 > 텍스트 태그입니다.||권장 되지 않음|  
|`string1`.strike()|에서는 HTML \<STRIKE > 텍스트 태그입니다.||사용 되지 않음|  
|`string1`.sub()|에서는 HTML \<하위 > 텍스트 태그입니다.|||  
|`string1`.sup()|에서는 HTML \<SUP > 텍스트 태그입니다.|||  
  
## <a name="remarks"></a>설명  
 확인 하지 않고 HTML 태그 문자열에 이미 적용 된 있는지 여부를 확인 하는 위해 수행 됩니다.  
  
## <a name="example"></a>예제  
 다음 예제 HTML 태그 메서드를 사용 하는 방법을 보여 줍니다.  
  
```JavaScript  
// anchor method.  
var strVariable = "This is an anchor.";  
document.write(strVariable.anchor("Anchor1"));  
// Output: <A NAME="Anchor1">This is an anchor.</A>  
  
// big method.  
var strVariable = "This is a string.";  
document.write(strVariable.big());  
// Output: <BIG>This is a string.</BIG>  
  
//  blink method.  
var strVariable = "This is a string.";  
document.write(strVariable.blink());  
// Output: <BLINK>This is a string.</BLINK>  
  
//  bold method.  
var strVariable = "This is a string.";  
document.write(strVariable.bold());  
// Output: <B>This is a string.</B>  
  
//  fixed method.  
var strVariable = "This is a string.";  
document.write(strVariable.fixed());  
// Output: <TT>This is a string.</TT>  
  
//  fontcolor method.  
var strVariable = "This is a string.";  
document.write(strVariable.fontcolor("red"));  
// Output: <FONT COLOR="red">This is a string.</FONT>  
  
//  fontsize method.  
var strVariable = "This is a string.";  
document.write(strVariable.fontsize(-1));  
// Output: <FONT SIZE="-1">This is a string.</FONT>  
  
//  italics method  
var strVariable = "This is a string.";  
document.write(strVariable.italics());  
// Output: <I>This is a string.</I>  
  
//  link method.  
var strVariable = "This is a hyperlink.";  
document.write(strVariable.link("http://www.microsoft.com"));  
// Output: <A HREF="http://www.microsoft.com">This is a hyperlink.</A>  
  
//  small method.  
var strVariable = "This is a string.";  
document.write(strVariable.small());  
// Output: <SMALL>This is a string.</SMALL>  
  
//  strike method.  
var strVariable = "This is a string.";  
document.write(strVariable.strike());  
// Output: <STRIKE>This is a string.</STRIKE>  
  
//  sub method.  
var strVariable = "This is a string.";  
document.write(strVariable.sub());  
// Output: <SUB>This is a string.</SUB>  
  
//  sup method.  
var strVariable = "This is a string.";  
document.write(strVariable.sup());  
// Output: <SUP>This is a string.</SUP>  
```  
  
## <a name="requirements"></a>요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **적용 대상**: [문자열 개체](../../javascript/reference/string-object-javascript.md)  
  
## <a name="see-also"></a>참고 항목  
 [String 개체](../../javascript/reference/string-object-javascript.md)