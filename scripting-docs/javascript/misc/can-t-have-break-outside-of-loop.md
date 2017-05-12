---
title: "루프 외부에서 &#39;break&#39;를 사용할 수 없습니다. | Microsoft Docs"
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
  - "VS.WebClient.Help.SCRIPT1019"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
ms.assetid: 11d02172-2a78-4705-a730-d21111db5f42
caps.latest.revision: 6
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 6
---
# 루프 외부에서 &#39;break&#39;를 사용할 수 없습니다.
루프 밖에서 **break** 키워드를 사용하려고 했습니다.  **break** 키워드는 루프 또는 `switch` 문을 종료하는 데 사용됩니다.  이 키워드는 루프 또는 `switch` 문의 본문에 포함해야 합니다.  하지만 **label**은 break 키워드를 따를 수 있습니다.  
  
```  
break labelname;  
```  
  
 중첩된 루프 또는 `switch` 문을 사용 중이고 가장 안쪽 루프가 아닌 루프를 중단하려는 경우 **break** 키워드의 레이블이 지정된 형식이 필요합니다.  
  
### 이 오류를 해결하려면  
  
-   **break** 키워드가 바깥쪽 루프 또는 switch 문 안에 표시되는지 확인합니다.  
  
## 참고 항목  
 [break 문](../../javascript/reference/break-statement-javascript.md)   
 [프로그램 흐름 제어](../../javascript/controlling-program-flow-javascript.md)   
 [스크립트 문제 해결](../../javascript/advanced/troubleshooting-your-scripts-javascript.md)