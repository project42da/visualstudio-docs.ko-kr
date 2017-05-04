---
title: "valueOf 메서드(Object)(JavaScript) | Microsoft Docs"
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
  - "valueOf"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "valueOf 메서드"
ms.assetid: c555e38b-f451-4341-8fcd-4c8b02906a2c
caps.latest.revision: 10
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 10
---
# valueOf 메서드(Object)(JavaScript)
지정한 개체의 원시 값을 반환합니다.  
  
## 구문  
  
```  
  
object.valueOf( )  
```  
  
## 설명  
 필수 `object` 참조는 임의의 내장 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 개체입니다.  
  
 `valueOf` 메서드는 각 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 내장 개체에 따라 다르게 정의됩니다.  
  
|Object|반환 값|  
|------------|----------|  
|Array|배열 인스턴스를 반환합니다.|  
|Boolean|부울 값입니다.|  
|Date|UTC 1970년 1월 1일 자정부터 밀리초 단위로 저장된 시간 값입니다.|  
|함수|함수 그 자체입니다.|  
|Number|숫자 값입니다.|  
|Object|개체 그 자체이며  이 값이 기본값입니다.|  
|문자열|문자열 값입니다.|  
  
 **Math** 개체와 `Error` 개체는 `valueOf` 메서드를 가지지 않습니다.  
  
## 요구 사항  
 [!INCLUDE[jsv2](../../javascript/reference/includes/jsv2-md.md)]  
  
 **적용 대상**: [Array 개체](../../javascript/reference/array-object-javascript.md)&#124; [Boolean 개체](../../javascript/reference/boolean-object-javascript.md)&#124; [Date 개체](../../javascript/reference/date-object-javascript.md)&#124; [Function 개체](../../javascript/reference/function-object-javascript.md)&#124; [Number 개체](../../javascript/reference/number-object-javascript.md)&#124; [Object 개체](../../javascript/reference/object-object-javascript.md)&#124; [String 개체](../../javascript/reference/string-object-javascript.md)  
  
## 참고 항목  
 [toString 메서드\(Object\)](../../javascript/reference/tostring-method-object-javascript.md)