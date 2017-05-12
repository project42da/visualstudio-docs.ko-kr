---
title: "toLocaleString 메서드(Object)(JavaScript) | Microsoft Docs"
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
  - "toLocaleString"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "toLocaleString 메서드"
ms.assetid: 0901afcb-126b-4ed7-bd6a-2301d50e2326
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# toLocaleString 메서드(Object)(JavaScript)
현재 로캘을 사용하여 문자열로 변환된 날짜를 반환합니다.  
  
## 구문  
  
```  
  
dateObj.toLocaleString()   
```  
  
## 설명  
 필수 `dateObj`는 `Date` 개체입니다.  
  
 `toLocaleString` 메서드는 현재 로캘의 긴 기본 형식에 날짜가 기록되어 있는  `String` 개체를 반환합니다.  
  
-   서기 1601년에서 1999년 사이 날짜의 경우 날짜에 사용자의 제어판 국가별 설정 서식이 사용됩니다.  
  
-   그 범위 외의 날짜의 경우 **toString** 메서드의 기본 서식이 사용됩니다.  
  
 예를 들어 미국에서 `toLocaleString`은 1월 5일에 대해 "01\/05\/96 00:00:00"을 반환합니다.  유럽에서는 같은 날짜에 대해 "05\/01\/96 00:00:00"이 반환됩니다. 유럽 변환의 경우 월 앞에 날짜를 넣기 때문입니다.  
  
> [!NOTE]
>  `toLocaleString`은 결과를 사용자에게 보여 주는 데만 사용해야 합니다. 반환되는 결과가 시스템마다 다르기 때문에 스크립트 내에서 계산의 기준으로 사용하면 안 됩니다.  
  
## 예제  
 다음 예제에서는 `toLocaleString` 메서드의 사용법을 보여 줍니다.  
  
```javascript  
function toLocaleStrDemo(){     
   var d, s;                      //Declare variables.  
   d = new Date();                //Create Date object.  
   s = "Current setting is ";  
   s += d.toLocaleString();       //Convert to current locale.  
   return(s);                     //Return converted date  
}  
```  
  
## 요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **적용 대상**: [Array 개체](../../javascript/reference/array-object-javascript.md)&#124; [Date 개체](../../javascript/reference/date-object-javascript.md)&#124; [Number 개체](../../javascript/reference/number-object-javascript.md)&#124; [Object 개체](../../javascript/reference/object-object-javascript.md)  
  
## 참고 항목  
 [toLocaleDateString 메서드\(Date\)](../../javascript/reference/tolocaledatestring-method-date-javascript.md)