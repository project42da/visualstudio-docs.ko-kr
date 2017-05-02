---
title: "특수 문자(JavaScript) | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-javascript"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "백슬래시(\)"
  - "이스케이프 시퀀스"
  - "줄 종결자 문자"
  - "유니코드 문자"
  - "공백 문자"
ms.assetid: 3b38b1bd-1f0f-4748-b13e-55cab36fd126
caps.latest.revision: 31
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 31
---
# 특수 문자(JavaScript)
[!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]는 직접 입력할 수 없는 문자를 만들기 위해 문자열에 포함시킬 수 있는 이스케이프 시퀀스를 제공합니다.  
  
## 주의  
 문자열 값은 0자 이상의 일련의 유니코드 문자\(문자, 숫자 및 기타 문자\)입니다.  문자열 리터럴은 일치하는 작은따옴표 또는 큰따옴표 쌍으로 묶입니다.  큰따옴표를 작은따옴표로 묶인 문자열에 포함할 수 있습니다.  작은따옴표를 큰따옴표로 묶인 문자열에 포함할 수 있습니다.  
  
 문자열 리터럴의 각 문자는 이스케이프 시퀀스로 나타낼 수 있습니다.  이스케이프 시퀀스는 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 인터프리터에 다음 문자가 특수 문자임을 알리는 백슬래시\(\\\)로 시작합니다.  
  
 \\u*hhhh* 이스케이프 시퀀스를 사용하여 유니코드 문자를 지정할 수 있습니다. 여기서 *hhhh*는 16진수 4개입니다.  유니코드 이스케이프 시퀀스는 임의의 16비트 문자를 나타낼 수 있습니다.  자세한 내용은 [유니코드 코드 포인트 이스케이프 시퀀스](#CodePoint)를 참조하세요.  
  
 일부 문자에 대해 단일 문자 이스케이프 시퀀스를 사용할 수 있습니다.  예를 들어 \\t는 탭 문자를 지정합니다.  
  
## 이스케이프 시퀀스  
 다음 표에서는 일반적인 문자에 대한 이스케이프 시퀀스의 몇 가지 예를 보여 줍니다.  
  
|유니코드 문자 값|이스케이프 시퀀스|의미|범주|  
|---------------|---------------|--------|--------|  
|\\u0008|\\b|백스페이스||  
|\\u0009|\\t|탭|공백|  
|\\u000A|\\n|줄 바꿈\(새 줄\)|줄 종결자|  
|\\u000B|\\v<br /><br /> \(이 표 아래에 있는 정보 참조\)|세로 탭|공백|  
|\\u000C|\\f|폼 피드|공백|  
|\\u000D|\\r|캐리지 리턴|줄 종결자|  
|\\u0020||공백|공백|  
|\\u0022|\\"|큰따옴표\("\)||  
|\\u0027|\\'|작은따옴표\('\)||  
|\\u005C|\\\\|백슬래시\(\\\)||  
|\\u00A0||줄 바꿈하지 않는 공백|공백|  
|\\u2028||줄 구분 기호|줄 종결자|  
|\\u2029||단락 구분 기호|줄 종결자|  
|\\uFEFF||바이트 순서 표시|공백|  
  
 범주 열은 문자가 공백인지 또는 줄 종결자 문자인지를 지정합니다.  [trim 메서드\(String\)](../../javascript/reference/trim-method-string-javascript.md)는 문자열에서 선행 및 후행 공백과 줄 종결자 문자를 제거합니다.  
  
 백슬래시 자체는 이스케이프 문자로 사용됩니다.  따라서 스크립트에 직접 입력할 수는 없습니다.  백슬래시를 쓰려는 경우 두 개를 함께 입력해야 합니다\(\\\\\).  
  
> [!NOTE]
>  [!INCLUDE[jsv9text](../../javascript/includes/jsv9text-md.md)]부터 세로 탭\(\\v\)과 "v"가 같은지 테스트하여 브라우저를 Internet Explorer로 식별할 수 없습니다.  이전 버전에서는 `"\v" === "v"` 식이 `true`를 반환합니다.  [!INCLUDE[jsv9text](../../javascript/includes/jsv9text-md.md)]에서는 식이 `false`를 반환합니다.  
  
## 예제  
  
### 설명  
 다음 예제에서는 \\\\ 및 \\' 이스케이프 시퀀스를 보여 줍니다.  
  
### 코드  
  
```javascript  
document.write('The image path is C:\\webstuff\\mypage\\gifs\\garden.gif.');  
document.write ("<br />");  
document.write('The caption reads, "After the snow of \'97. Grandma\'s house is covered."');  
```  
  
<a name="CodePoint"></a>   
## 유니코드 코드 포인트 이스케이프 시퀀스  
 [!INCLUDE[jsv12text](../../javascript/includes/jsv12text-md.md)]에서는 유니코드가 완전히 지원됩니다.  가장 일반적인 유니코드 코드 포인트는 탭 문자를 나타내는 \/u0009와 같이 16진수 4개로 표현됩니다.  16진수가 5개 이상 필요한 모든 기호를 포함하는 아스트랄 코드 포인트는 이제 간소화된 형식으로 지원됩니다.  "\\u{*codepoint*}" 형식을 사용하여 전체 유니코드 문자 집합을 리터럴 형식으로 나타낼 수 있습니다.  예를 들어 "𠮷" 기호를 나타내려면 "\\u{20BB7}" 형식을 사용할 수 있습니다.  
  
 다음 코드 예제에서는 문자열이 모두 동일합니다.  \\uD842\\uDFB7은 이전 버전에서 이 기호를 지정하는 해결 방법입니다.  
  
```javascript  
"\u{20BB7}"=="𠮷"=="\uD842\uDFB7"  
  
```  
  
 아스트랄 코드 포인트를 완전히 지원하기 위해 이제 RegExp에 \/u 플래그가 포함되었습니다.  예를 들어 다음 코드 예제에서 정규식의 \/u 플래그는 아스트랄 코드 포인트를 일치시킬 수 있도록 합니다\(마침표는 제공된 문자열의 임의 문자와 일치함\).  
  
```javascript  
"𠮷".match(/./u)[0].length == 2  
  
```  
  
 \/u 플래그를 사용하면 새로운 형식 \\u{codepoint}\)를 유니코드 이스케이프 시퀀스로 구문 분석할 수 있습니다.  \/u 플래그가 없는 \\u{xxxxx}는 정규식에서 다른 의미를 갖기 때문에 이 플래그가 필요합니다.  
  
> [!NOTE]
>  아스트랄 코드 포인트의 길이는 항상 2입니다.  이 동작은 이전 버전과 일치합니다.  
  
 아스트랄 코드 포인트를 지원하기 위해 이제 String 개체에 두 개의 새 메서드 String.codePointAt 및 String.fromCodePoint가 포함되었습니다.  예를 들어 codePointAt를 사용하여 "𠮷" 기호에 해당하는 코드 포인트를 반환할 수 있습니다.  
  
```javascript  
"𠮷".codePointAt(0) == 0x20BB7  
  
```  
  
 `for…of` 문을 사용하여 코드 포인트를 반복할 수도 있습니다.  
  
```javascript  
for(var c of "𠮷") {  
    console.log(c);  
}  
  
```  
  
## 참고 항목  
 [String.fromCharCode 함수](../../javascript/reference/string-fromcharcode-function-javascript.md)