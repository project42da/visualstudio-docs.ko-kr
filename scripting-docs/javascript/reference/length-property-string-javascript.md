---
title: "length 속성(String)(JavaScript) | Microsoft Docs"
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
  - "length Property"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "문자열[Visual Studio], 길이"
  - "Length 속성"
  - "length 속성(String)"
ms.assetid: 7dbd4a0e-c24e-4561-9b5b-e75e649a10a4
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# length 속성(String)(JavaScript)
`String` 개체의 길이를 반환합니다.  
  
> [!WARNING]
>  JavaScript 문자열은 변경할 수 없으므로 문자열의 길이를 수정할 수 없습니다.  
  
## 구문  
  
```  
  
      strVariable.length  
"String Literal".length   
```  
  
## 설명  
 `length` 속성에는 `String` 개체의 문자 수를 나타내는 정수가 포함되어 있습니다.  `String` 개체의 마지막 문자에 대한 인덱스는 `length` \- 1입니다.  
  
## 예제  
 다음 코드에서는 `length`를 사용하는 방법을 보여 줍니다.  JavaScript 문자열은 변경할 수 없으며 현재 위치에서 수정할 수도 없습니다.  그러나 문자 순서를 역순으로 한 문자열을 배열에 기록한 다음 빈 문자와 함께 `join`을 호출할 수 있습니다. 이렇게 하면 구분 기호 문자가 없는 문자열이 생성됩니다.  
  
```javascript  
var str = "every good boy does fine";  
        var start = 0;  
        var end = str.length - 1;  
        var tmp = "";  
        var arr = new Array(end);  
  
        while (end >= 0) {  
            arr[start++] = str.charAt(end--);  
        }  
  
// Join the elements of the array with a   
        var str2 = arr.join('');  
        document.write(str2);  
  
// Output: enif seod yob doog yreve  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]