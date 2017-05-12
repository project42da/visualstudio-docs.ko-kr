---
title: "fill 메서드(Array)(JavaScript) | Microsoft Docs"
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
ms.assetid: 11526627-c0bb-4157-a8c4-0a039079b4a1
caps.latest.revision: 3
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 3
---
# fill 메서드(Array)(JavaScript)
지정된 값으로 배열을 채웁니다.  
  
## 구문  
  
```  
arrayObj.fill(value [ , start [ , end ] ]);  
```  
  
#### 매개 변수  
 `arrayObj`  
 필수 요소.  Array 개체입니다.  
  
 `value`  
 필수 요소.  배열을 채우는 데 사용되는 값입니다.  
  
 `start`  
 선택적 요소.  배열 값을 채우는 데 사용되는 시작 인덱스입니다.  기본값은 0입니다.  
  
 `end`  
 선택적 요소.  배열 값을 채우는 데 사용되는 끝 인덱스입니다.  기본값은 `this` 개체의 length 속성입니다.  
  
## 설명  
 `start`가 음수이면 `start`는 `length`\+`start`로 처리됩니다. 여기서 `length`는 배열의 길이입니다.  `end`가 음수이면 `end`는 `length`\+`end`로 처리됩니다.  
  
## 예제  
 다음 코드 예제에서는 배열을 값으로 채웁니다.  
  
```javascript  
[0, 0, 0].fill(7, 1);  
// Array contains [0,7,7]  
  
[0, 0, 0].fill(7);  
// Array contains [7,7,7]  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv12](../../javascript/reference/includes/jsv12-md.md)]