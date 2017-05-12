---
title: "getVarDate 메서드(Date)(JavaScript) | Microsoft Docs"
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
  - "getVarDate"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "Date 개체"
  - "getVarDate 메서드"
  - "날짜, VT_DATE 형식"
ms.assetid: 561238de-5c91-45a3-b839-a16910d3a1cf
caps.latest.revision: 18
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 18
---
# getVarDate 메서드(Date)(JavaScript)
`Date` 개체에서 VT\_DATE 값을 반환합니다.  
  
> [!WARNING]
>  이 메서드는 Internet Explorer에서만 지원됩니다.  
  
## 구문  
  
```  
  
dateObj.getVarDate()   
```  
  
#### 매개 변수  
 필요한 `dateObj` 참조는 `Date` 개체입니다.  
  
## 반환 값  
 VT\_DATE 값을 반환합니다.  
  
## 설명  
 `getVarDate` 메서드는 JavaScript 코드가 COM 개체, ActiveX 개체 또는 VT\_DATE 형식의 날짜 값을 허용하고 반환하는 기타 개체와 상호 작용할 때 사용됩니다. 여기에는 Visual Basic 및 VBScript\(Visual Basic Scripting Edition\)의 개체가 포함됩니다. 반환되는 값의 실제 형식은 국가별 설정에 따라 달라집니다.  
  
## 요구 사항  
 지원되는 문서 모드: Quirks, Internet Explorer 6 표준, Internet Explorer 7 표준, Internet Explorer 8 표준, Internet Explorer 9 표준 및 Internet Explorer 10 표준[!INCLUDE[win8_appname_long](../../javascript/advanced/includes/win8-appname-long-md.md)] 앱에서는 지원되지 않습니다.[버전 정보](../../javascript/reference/javascript-version-information.md)를 참조하십시오.  
  
 **적용 대상**: [Date 개체](../../javascript/reference/date-object-javascript.md)  
  
## 참고 항목  
 [getDate 메서드\(Date\)](../../javascript/reference/getdate-method-date-javascript.md)   
 [Date.parse 함수](../../javascript/reference/date-parse-function-javascript.md)