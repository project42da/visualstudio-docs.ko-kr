---
title: "hasOwnProperty 메서드(Object)(JavaScript) | Microsoft Docs"
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
  - "hasOwnProperty"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "hasOwnProperty 메서드"
ms.assetid: 3eb69d69-486f-4792-9518-4452aef369ca
caps.latest.revision: 15
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 15
---
# hasOwnProperty 메서드(Object)(JavaScript)
개체가 지정된 이름의 속성을 포함하는지 여부를 확인합니다.  
  
## 구문  
  
```  
  
object.hasOwnProperty(proName)  
```  
  
## 매개 변수  
 `object`  
 필수 요소.  개체의 인스턴스입니다.  
  
 `proName`  
 필수 요소.  속성 이름의 문자열 값입니다.  
  
## 설명  
 `hasOwnProperty` 메서드는 `object`에 지정된 이름의 속성이 있을 경우 `true`를 반환하고 그렇지 않으면 `false`를 반환합니다.  이 메서드가 개체의 프로토타입 체인에서 속성을 검사하지는 않으므로 속성이 개체 자체의 멤버여야 합니다.  
  
 이 속성은 Internet Explorer 8 이하의 호스트 개체에서 지원되지 않습니다.  
  
## 예제  
 다음 예제에서 모든 `String` 개체는 split 공용 메서드를 공유합니다.  다음 코드에서는 **false** 및 **true**를 표시합니다.  
  
```javascript  
var s = new String("Sample");  
document.write(s.hasOwnProperty("split"));  
document.write("<br/>");  
document.write(String.prototype.hasOwnProperty("split"));  
  
// Output:  
// false  
// true  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv55](../../javascript/reference/includes/jsv55-md.md)]  
  
## 참고 항목  
 [in 연산자](../../javascript/reference/in-operator-decrementjavascript.md)