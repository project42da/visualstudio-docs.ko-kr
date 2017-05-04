---
title: "예기치 않은 수량자입니다.(JavaScript) | Microsoft Docs"
ms.custom: ""
ms.date: "01/18/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "javascript"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VS.WebClient.Help.SCRIPT5018"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
ms.assetid: ba6d34f9-2d6f-486c-a929-6cd9818be322
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# 예기치 않은 수량자입니다.(JavaScript)
정규식 검색 패턴을 구성할 때 잘못된 반복 비율을 사용하여 패턴 요소를 만들었습니다.  예를 들어  
  
```  
/^+/  
```  
  
 패턴은 ^\(입력 시작\) 요소가 반복 비율을 가질 수 없기 때문에 잘못되었습니다.  다음 표에서는 반복 비율을 가질 수 없는 요소를 보여 줍니다.  
  
|요소|설명|  
|--------|--------|  
|^|입력 시작|  
|$|입력 끝|  
|\\b|단어 경계|  
|\\B|비단어 경계|  
|\*|0회 이상 반복|  
|\+|1회 이상 반복|  
|?|0 또는 1회 반복|  
|{n}|n회 반복|  
|{n,}|n회 이상 반복|  
|{n,m}|n~m회 반복\(포함\)|  
  
### 이 오류를 해결하려면  
  
-   검색 패턴 요소가 올바른 반복 요소만 포함하는지 확인하세요.  
  
## 참고 항목  
 [Regular Expression 개체](../../javascript/reference/regular-expression-object-javascript.md)   
 [Regular Expression Syntax \(JavaScript\)](http://msdn.microsoft.com/ko-kr/ab0766e1-7037-45ed-aa23-706f58358c0e)