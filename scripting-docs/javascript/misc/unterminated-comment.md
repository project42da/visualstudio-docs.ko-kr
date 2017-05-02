---
title: "종결되지 않은 주석입니다. | Microsoft Docs"
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
  - "VS.WebClient.Help.SCRIPT1016"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
ms.assetid: d4286315-814b-4966-b4c4-1ee19d796eff
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# 종결되지 않은 주석입니다.
여러 줄로 된 주석 블록을 시작했지만 제대로 종결하지 않았습니다.  여러 줄로 된 주석은 "\/\*" 조합으로 시작되고 "\*\/" 조합으로 끝납니다.  예를 들면 다음과 같습니다.  
  
```javascript  
/* This is a comment  
This is another part of the same comment.*/  
```  
  
### 이 오류를 해결하려면  
  
-   여러 줄로 된 주석은 "\*\/"로 종결해야 합니다.  
  
## 참고 항목  
 [Comment 문](../../javascript/reference/comment-statements-javascript.md)