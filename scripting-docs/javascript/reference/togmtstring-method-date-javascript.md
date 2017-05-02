---
title: "toGMTString 메서드(Date)(JavaScript) | Microsoft Docs"
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
  - "toGMTString"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "toGMTString 메서드"
ms.assetid: 9dc1e722-5722-4b8c-a213-a2650f55f207
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# toGMTString 메서드(Date)(JavaScript)
GMT\(그리니치 표준시\)를 사용하여 문자열로 변환된 날짜를 반환합니다.  
  
## 구문  
  
```  
  
dateObj.toGMTString()   
```  
  
## 설명  
 필수 `dateObj` 참조는 임의의 `Date` 개체입니다.  
  
 `toGMTString` 메서드는 이전 방식이며 이전 버전과의 호환성을 유지하기 위해 제공됩니다.  대신 `toUTCString` 메서드를 사용하세요.  
  
 `toGMTString` 메서드는 GMT 규칙을 사용하여 서식을 지정한 날짜를 포함하는 `String` 개체를 반환합니다.  반환 값의 형식은 "05 Jan 1996 00:00:00 GMT"와 같습니다.  
  
## 요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **적용 대상**: [Date 개체](../../javascript/reference/date-object-javascript.md)  
  
## 참고 항목  
 [toUTCString 메서드\(Date\)](../../javascript/reference/toutcstring-method-date-javascript.md)