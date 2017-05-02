---
title: "VBArray가 필요합니다. | Microsoft Docs"
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
  - "VS.WebClient.Help.SCRIPT5013"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
ms.assetid: f2998d7d-13a4-4bbe-b872-3ff3316551e4
caps.latest.revision: 6
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 6
---
# VBArray가 필요합니다.
필요한 경우 Visual Basic safeArray가 아닌 개체를 제공했습니다.  
  
```  
new VBArray(safeArray);  
```  
  
 VBArray는 읽기 전용이며 직접 만들 수 없습니다.  safeArray 인수는 VBArray 값이며 `VBArray` 생성자로 전달되기 전에 VBArray 값을 받은 상태여야 합니다.  이렇게 하려면 기존 ActiveX나 다른 개체에서 값을 가져와야 합니다.  
  
### 이 오류를 해결하려면  
  
-   **VBArray** 개체만 **VBArray** 생성자에 전달해야 합니다.  
  
## 참고 항목  
 [VBArray 개체](../../javascript/reference/vbarray-object-javascript.md)   
 [배열 사용](../../javascript/advanced/using-arrays-javascript.md)