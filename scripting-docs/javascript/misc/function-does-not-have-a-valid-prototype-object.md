---
title: "함수에 유효한 프로토타입 개체가 없습니다. | Microsoft Docs"
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
  - "VS.WebClient.Help.SCRIPT5023"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
ms.assetid: b9e34652-190f-4b57-b253-df2e8c4d09c6
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# 함수에 유효한 프로토타입 개체가 없습니다.
**instanceof**를 사용하여 개체가 특정 함수 클래스에서 파생되는지 여부를 확인하려고 했지만 개체의 `prototype` 속성을 `null`로 재정의했거나 외부 개체 형식으로 재정의했습니다\(둘 다 유효한 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 개체가 아님\).  외부 개체는 Internet Explorer의 문서 또는 창 개체와 같은 호스트 개체 모델의 개체이거나 외부 COM 개체일 수 있습니다.  
  
### 이 오류를 해결하려면  
  
-   함수의 `prototype` 속성이 유효한 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 개체를 참조하도록 합니다.  
  
## 참고 항목  
 [Function 개체](../../javascript/reference/function-object-javascript.md)   
 [prototype 속성\(Object\)](../../javascript/reference/prototype-property-object-javascript.md)