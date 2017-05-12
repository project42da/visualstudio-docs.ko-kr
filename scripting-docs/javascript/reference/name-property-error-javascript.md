---
title: "name 속성(Error)(JavaScript) | Microsoft Docs"
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
  - "name"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "Name 속성"
  - "name 속성, 오류 이름"
ms.assetid: 94df2d6b-f1a1-4931-a956-0a930cb87f76
caps.latest.revision: 15
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 15
---
# name 속성(Error)(JavaScript)
오류 이름을 반환합니다.  
  
## 구문  
  
```  
  
errorObj.  
name  
  
```  
  
## 매개 변수  
 `errorObj`  
 필수 요소.  `Error` 개체의 인스턴스입니다.  
  
## 설명  
 **name** 속성은 오류의 이름 또는 예외 형식을 반환합니다.  런타임 오류가 발생하면 name 속성은 다음 네이티브 예외 형식 중 하나로 설정됩니다.  
  
|예외 형식|의미|  
|-----------|--------|  
|ConversionError|이 오류는 변환할 수 없는 것으로 개체를 변환하려고 할 때마다 발생합니다.|  
|RangeError|이 오류는 허용 범위를 초과한 인수가 함수에 제공될 경우 발생합니다.  예를 들어 길이가 유효한 양의 정수가 아닌 `Array` 개체를 구성하려고 할 경우 이 오류가 발생합니다.|  
|ReferenceError|이 오류는 올바르지 않은 참조가 검색되면 발생합니다.  예를 들어 예상되는 참조가 `null`일 경우 이 오류가 발생합니다.|  
|RegExpError|이 오류는 정규식에서 컴파일 오류가 발생할 때 발생합니다.  일단 정규식이 컴파일되면 이 오류는 발생하지 않습니다.  예를 들어 정규식이 잘못된 구문이 있거나 플래그가 **i**, **g**, **m**이 아닌 패턴으로 선언되었거나, 같은 플래그가 두 개 이상 들어 있을 경우 이 오류가 발생합니다.|  
|SyntaxError|이 오류는 소스 텍스트가 구문 분석되고 해당 소스 텍스트가 올바른 구문을 따르지 않을 경우 발생합니다.  예를 들어 `eval` 함수가 유효한 프로그램 텍스트가 아닌 인수로 호출될 경우 이 오류가 발생합니다.|  
|TypeError|이 오류는 피연산자의 실제 유형이 예상 유형과 일치하지 않을 때마다 발생합니다.  예를 들어 개체가 아니거나 호출을 지원하지 않는 곳에서 함수를 호출할 경우 이 오류가 발생합니다.|  
|URIError|이 오류는 잘못된 URI\(Uniform Resource Indicator\)가 감지될 경우 발생합니다.  예를 들어 인코딩되거나 디코딩될 문자열에 잘못된 문자가 있을 경우 이 오류가 발생합니다.|  
  
## 예제  
 다음 예제에서는 TypeError 예외를 throw하고 오류 이름과 해당 메시지를 표시합니다.  
  
```javascript  
try  
{  
    var x = y;  
}  
catch(e)  
{  
    document.write ("Error Message: " + e.message);  
    document.write ("<br />");  
    document.write ("Error Code: ");  
    document.write (e.number & 0xFFFF)  
    document.write ("<br />");  
    document.write ("Error Name: " + e.name);  
}  
```  
  
## 예제  
 이 코드의 출력은 다음과 같습니다.  
  
```javascript  
Error Message: 'y' is undefined  
Error Code: 5009  
Error Name: TypeError  
```  
  
## 요구 사항  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
 **적용 대상**: [Error 개체](../../javascript/reference/error-object-javascript.md)  
  
## 참고 항목  
 [description 속성\(Error\)](../../javascript/reference/description-property-error-javascript.md)   
 [message 속성\(Error\)](../../javascript/reference/message-property-error-javascript.md)   
 [number 속성\(Error\)](../../javascript/reference/number-property-error-javascript.md)