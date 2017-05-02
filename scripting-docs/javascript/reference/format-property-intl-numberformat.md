---
title: "format 속성(Intl.NumberFormat) | Microsoft Docs"
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
ms.assetid: 68c3223a-023c-4fa0-aa99-d049a7a0e26a
caps.latest.revision: 5
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 5
---
# format 속성(Intl.NumberFormat)
지정된 숫자 포맷터 설정을 사용해서 로캘별 숫자 형식을 지정하는 함수를 반환합니다.  
  
## 구문  
  
```  
numberFormatObj.format  
```  
  
#### 매개 변수  
 `numberFormatObj`  
 필수 요소.  포맷터로 사용할 `NumberFormat` 개체의 이름입니다.  
  
## 설명  
 `format` 속성에서 반환되는 함수에는 `value`라는 인수 한 개가 있고 `NumberFormat` 개체에 지정된 옵션을 사용하여 지역화된 숫자를 표현하는 문자열을 반환합니다.  `value`가 제공되지 않은 경우 함수는 `NaN`\(숫자 아님\)을 반환합니다.  
  
## 예제  
 다음 예제에서는 `NumberFormat` 개체를 사용하여 지역화된 숫자를 만듭니다.  
  
```javascript  
var nf = new Intl.NumberFormat(["en-US"], {  
    style: "currency",  
    currency: "CNY",  
    currencyDisplay: "symbol",  
    maximumFractionDigit: 1  
})  
  
if (console && console.log) {  
    console.log(nf.format(100)); // "¥100.00"  
}  
  
```  
  
## 요구 사항  
 [!INCLUDE[jsv11](../../javascript/reference/includes/jsv11-md.md)]  
  
## 참고 항목  
 [Intl.NumberFormat 개체](../../javascript/reference/intl-numberformat-object-javascript.md)