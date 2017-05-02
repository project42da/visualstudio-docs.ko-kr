---
title: "정규식에 &#39;)&#39;가 필요합니다.(JavaScript) | Microsoft Docs"
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
  - "VS.WebClient.Help.SCRIPT5020"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
ms.assetid: 2087ba1d-9783-4d40-b609-e8542f579f7f
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# 정규식에 &#39;)&#39;가 필요합니다.(JavaScript)
정규식 캡처, 삽입 또는 그룹을 만들려고 했지만 닫는 괄호가 포함되지 않았습니다.  정규식에서 괄호는 몇 가지 목적으로 사용됩니다.  주로 하위 식을 캡처하고, 삽입을 지정하거나 패턴을 함께 그룹화하는 데 사용되어 항목이 \*, \+, ? 등으로 하나의 단위로 취급됩니다.  
  
### 이 오류를 해결하려면  
  
-   맨 오른쪽 괄호를 추가합니다.  
  
    > [!NOTE]
    >  괄호 하나가 일치하도록 하려면 백슬래시 \- \\\(로 이스케이프합니다. 그러면 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)]에서 특수 문자로 해석하지 않습니다.  
  
## 참고 항목  
 [Regular Expression 개체](../../javascript/reference/regular-expression-object-javascript.md)   
 [Regular Expression Syntax \(JavaScript\)](http://msdn.microsoft.com/ko-kr/ab0766e1-7037-45ed-aa23-706f58358c0e)