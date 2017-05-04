---
title: "정규식에 &#39;]&#39;가 필요합니다.(JavaScript) | Microsoft Docs"
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
  - "VS.WebClient.Help.SCRIPT5019"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
ms.assetid: 1ca2079a-44dd-479f-a1e3-e04a14d0739e
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# 정규식에 &#39;]&#39;가 필요합니다.(JavaScript)
정규식 일치에 대한 문자 클래스를 만들려고 했지만 올바른 대괄호를 포함하지 않았습니다.  개별 리터럴 문자 조합은 대괄호 안에 문자 조합을 삽입하여 문자 클래스로 어셈블할 수 있습니다.  문자 클래스는 포함하는 임의의 문자 한 개와 일치합니다.  예를 들어 \/\[abc\]\/는 문자 "a", "b" 또는 "c" 중 하나와 일치합니다.  
  
### 이 오류를 해결하려면  
  
-   오른쪽 대괄호를 정규식에 추가합니다.  
  
    > [!NOTE]
    >  대괄호 하나가 일치하도록 하려면 백슬래시 \- \\\[로 이스케이프합니다. 그러면 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]에서 특수 문자로 해석하지 않습니다.  
  
## 참고 항목  
 [Regular Expression 개체](../../javascript/reference/regular-expression-object-javascript.md)   
 [Regular Expression Syntax \(JavaScript\)](http://msdn.microsoft.com/ko-kr/ab0766e1-7037-45ed-aa23-706f58358c0e)