---
title: "HTML 태그 메서드(JavaScript) | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-javascript"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "anchor 메서드[JavaScript]"
  - "big 메서드[JavaScript]"
  - "blink 메서드[JavaScript]"
  - "bold 메서드[JavaScript]"
  - "fixed 메서드[JavaScript]"
  - "fontcolor 메서드[JavaScript]"
  - "fontsize 메서드[JavaScript]"
  - "HTML 태그 메서드[JavaScript]"
  - "italics 메서드[JavaScript]"
  - "link 메서드[JavaScript]"
  - "small 메서드[JavaScript]"
  - "sub 메서드[JavaScript]"
  - "sup 메서드[JavaScript]"
ms.assetid: 50376223-be95-4aa4-9147-9e738a5d3cfa
caps.latest.revision: 15
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 15
---
# HTML 태그 메서드(JavaScript)
HTML 태그 메서드를 사용하여 `String` 개체의 텍스트 양 끝에 HTML 요소를 삽입할 수 있습니다.  
  
## 구문  
 다음 표에서는 각 HTML 태그 메서드에 대한 구문 및 설명을 보여 줍니다.  
  
 구문 열에서 `string1`은 `String` 개체 또는 리터럴입니다.  
  
 표준 열은 [W3C\(World Wide Web Consortium\)](http://go.microsoft.com/fwlink/?LinkId=199553) HTML 4 권장 사항을 나타냅니다.  "권장 안 함"은 해당 HTML 요소 대신 스타일시트를 사용하는 것이 더 좋음을 나타냅니다.  
  
|구문|방법 설명|매개 변수 설명|표준|  
|--------|-----------|--------------|--------|  
|`string1`.anchor\(`name`\)|텍스트 양 끝에 NAME 특성을 가진 HTML 앵커를 삽입합니다.|`name` 매개 변수는 HTML 앵커의 NAME 특성에 넣을 텍스트입니다.||  
|`string1`.big\(\)|텍스트 양 끝에 HTML \<BIG\> 태그를 삽입합니다.||권장 안 함|  
|`string1`.blink\(\)|텍스트 양 끝에 HTML \<BLINK\> 태그를 삽입합니다.  \<BLINK\> 태그는 Internet Explorer에서는 지원되지 않습니다.||표준에서 사용 안 함|  
|`string1`.bold\(\)|텍스트 양 끝에 HTML \<B\> 태그를 삽입합니다.||권장 안 함|  
|`string1`.fixed\(\)|텍스트 양 끝에 HTML \<TT\> 태그를 삽입합니다.||권장 안 함|  
|`string1`.fontcolor\(`color`\)|텍스트 양 끝에 COLOR 특성을 가진 HTML \<FONT\> 태그를 삽입합니다.|`color` 매개 변수는 16진수 값 또는 색상에 대해 미리 정의된 이름을 포함하는 문자열 값입니다.  미리 정의된 유효한 색 이름은 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 호스트 브라우저 및 해당 버전에 따라 달라집니다.|사용되지 않음|  
|`string1`.fontsize\(`size`\)|텍스트 양 끝에 SIZE 특성을 가진 HTML \<FONT\> 태그를 삽입합니다.|`size` 매개 변수는 텍스트 크기를 지정하는 정수 값입니다.  유효한 정수 값은 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 호스트 브라우저 및 해당 버전에 따라 달라집니다.|사용되지 않음|  
|`string1`.italics\(\)|텍스트 양 끝에 HTML \<I\> 태그를 삽입합니다.||권장 안 함|  
|`string1`.link\(`href`\)|텍스트 양 끝에 HREF 특성을 가진 HTML 앵커를 삽입합니다.|`href` 매개 변수는 HTML 앵커의 HREF 특성에 넣을 텍스트입니다.||  
|`string1`.small\(\)|텍스트 양 끝에 HTML \<SMALL\> 태그를 삽입합니다.||권장 안 함|  
|`string1`.strike\(\)|텍스트 양 끝에 HTML \<STRIKE\> 태그를 삽입합니다.||사용되지 않음|  
|`string1`.sub\(\)|텍스트 양 끝에 HTML \<SUB\> 태그를 삽입합니다.|||  
|`string1`.sup\(\)|텍스트 양 끝에 HTML \<SUP\> 태그를 삽입합니다.|||  
  
## 주의  
 HTML 태그가 문자열에 적용되었는지 여부를 확인하기 위한 검사는 수행되지 않습니다.  
  
## 예제  
 다음 예제에서는 HTML 태그 메서드의 사용법을 보여 줍니다.  
  
```javascript  
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
  
## 요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **적용 대상**: [String 개체](../../javascript/reference/string-object-javascript.md)  
  
## 참고 항목  
 [String 개체](../../javascript/reference/string-object-javascript.md)