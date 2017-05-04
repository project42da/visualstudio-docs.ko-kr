---
title: "문자 집합의 범위가 잘못되었습니다.(JavaScript) | Microsoft Docs"
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
  - "VS.WebClient.Help.SCRIPT5021"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
ms.assetid: 971e9d5a-f88a-47a8-af94-f3c7c4aed5ab
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# 문자 집합의 범위가 잘못되었습니다.(JavaScript)
잘못된 문자 집합 범위를 사용하여 정규식을 만들려고 했습니다.  문자 집합 범위는 a\-z 또는 0\-9와 같이 단일 문자만 포함해야 합니다. 문자 집합에 \\w와 같은 문자 클래스는 포함할 수 없습니다.  범위의 첫 번째 문자는 또한 해당 범위의 두 번째 문자 앞에 와야 합니다.  예를 들면 다음과 같습니다.  
  
```javascript  
var good = /[a-z]/;     // A valid character range - a comes before z.  
var notGood = /[z-a]/;  // An invalid character range - z does not come before a.  
```  
  
### 이 오류를 해결하려면  
  
-   단일 문자만 사용하여 정규식 문자 집합을 구성하고 순서가 올바른지 확인하세요.  
  
## 참고 항목  
 [Regular Expression 개체](../../javascript/reference/regular-expression-object-javascript.md)   
 [Regular Expression Syntax \(JavaScript\)](http://msdn.microsoft.com/ko-kr/ab0766e1-7037-45ed-aa23-706f58358c0e)