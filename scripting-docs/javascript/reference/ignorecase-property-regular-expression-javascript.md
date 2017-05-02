---
title: "ignoreCase 속성(Regular Expression)(JavaScript) | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-javascript"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "ignoreCase"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "IgnoreCase 속성"
ms.assetid: 816f0df5-5a82-44a5-a4ab-dbc91fa76e61
caps.latest.revision: 17
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 17
---
# ignoreCase 속성(Regular Expression)(JavaScript)
정규식에 사용된 ignoreCase 플래그\(**i**\)의 상태를 나타내는 부울 값을 반환합니다.  기본값은 **false**입니다.  읽기 전용입니다.  
  
## 구문  
  
```  
  
rgExp.ignoreCase  
```  
  
## 설명  
 필수 `rgExp` 참조는 `RegExp` 개체의 인스턴스입니다.  
  
 **ignoreCase** 속성은 정규식에 ignoreCase 플래그가 설정되면 **true**를 반환하고 그렇지 않으면 **false**를 반환합니다.  
  
 ignoreCase 플래그가 사용되면 검색 문자열 내에서 패턴이 일치할 경우 대소문자를 무시합니다.  
  
## 예제  
 다음 예제는 **ignoreCase** 속성의 사용법을 보여 줍니다.  아래 표시된 함수에 "gi"를 전달하면 초기 "The"를 비롯한 단어 "the"의 모든 인스턴스가 단어 "a"로 바뀝니다.  이는 ignoreCase 플래그가 설정된 경우 검색에서 대\/소문자 구분을 무시하기 때문입니다.  따라서 일치 시 "T"는 "t"와 같습니다.  
  
 이 함수는 허용 가능한 정규식 플래그인 **g**, **i** 및 **m**의 상태를 나타내는 부울 값을 반환합니다.  또한 모든 대체가 수행된 문자열을 반환합니다.  
  
```javascript  
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
  
## 예제  
 다음은 결과 출력입니다.  
  
```javascript  
global: true  
ignoreCase: true  
multiline: false  
Resulting String: a batter hit a ball with a bat and a fielder caught a ball with a glove.  
  
global: true  
ignoreCase: false  
multiline: false  
Resulting String: The batter hit a ball with a bat and a fielder caught a ball with a glove.  
```  
  
## 요구 사항  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
 **적용 대상**: [Regular Expression 개체](../../javascript/reference/regular-expression-object-javascript.md)  
  
## 참고 항목  
 [global 속성\(Regular Expression\)](../../javascript/reference/global-property-regular-expression-javascript.md)   
 [multiline 속성\(Regular Expression\)](../../javascript/reference/multiline-property-regular-expression-javascript.md)   
 [Regular Expression Syntax \(JavaScript\)](http://msdn.microsoft.com/ko-kr/ab0766e1-7037-45ed-aa23-706f58358c0e)