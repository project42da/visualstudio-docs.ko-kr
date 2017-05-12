---
title: "getYear 메서드(Date)(JavaScript) | Microsoft Docs"
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
  - "getYear"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
helpviewer_keywords: 
  - "날짜, 연도 반환"
  - "GetYear 메서드"
ms.assetid: 0e23e832-acd4-49a9-a175-515d0094f172
caps.latest.revision: 19
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 19
---
# getYear 메서드(Date)(JavaScript)
1 년짜리는 `Date` 개체.  
  
## 구문  
  
```  
  
dateObj.getYear()   
```  
  
#### 매개 변수  
 필요한 `dateObj` 참조 되는 `Date` 개체입니다.  
  
## 반환 값  
 연도 반환합니다.  
  
## 설명  
  
> [!IMPORTANT]
>  이 메서드가 사용 되지 않으며 이전 버전과 호환성을 위해서만 제공 됩니다.  대신 `getFullYear` 메서드를 사용하십시오.  
  
 [!INCLUDE[jsv1textspecific](../../javascript/reference/includes/jsv1textspecific-md.md)], Internet Explorer 버전부터 시작 하 여 다음에 [!INCLUDE[jsv9textspecific](../../javascript/reference/includes/jsv9textspecific-md.md)], 반환 값은 저장 된 연도 1900 뺀 값입니다.  예를 들어, 1899년은 \-1을 반환하고 2000년은 100을 반환합니다.  
  
 [!INCLUDE[jsv3textspecific](../../javascript/reference/includes/jsv3textspecific-md.md)] \- [!INCLUDE[jsv58textspecific](../../javascript/reference/includes/jsv58textspecific-md.md)], 수식을 연도에 따라 달라 집니다.  1900부터 1999 년에 반환 된 값 저장 된 연도 1900 뺀 숫자 2 값이입니다.  이 범위 밖의 날짜의 4 자리 연도 반환 됩니다.  예를 들어, 1996 96으로 반환 되지만 1825 고 그대로 반환 됩니다.  
  
## 요구 사항  
 [!INCLUDE[jsv1](../../javascript/misc/includes/jsv1-md.md)]  
  
 **적용**.[Date 개체](../../javascript/reference/date-object-javascript.md)  
  
## 참고 항목  
 [getFullYear 메서드\(Date\)](../../javascript/reference/getfullyear-method-date-javascript.md)   
 [getUTCFullYear 메서드\(Date\)](../../javascript/reference/getutcfullyear-method-date-javascript.md)   
 [setFullYear 메서드\(Date\)](../../javascript/reference/setfullyear-method-date-javascript.md)   
 [setUTCFullYear 메서드\(Date\)](../../javascript/reference/setutcfullyear-method-date-javascript.md)   
 [setYear 메서드\(Date\)](../../javascript/reference/setyear-method-date-javascript.md)