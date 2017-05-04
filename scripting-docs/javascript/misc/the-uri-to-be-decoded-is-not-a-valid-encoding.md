---
title: "디코딩할 URI가 올바른 인코딩이 아닙니다. | Microsoft Docs"
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
  - "VS.WebClient.Help.SCRIPT5025"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
ms.assetid: 029e0790-ffd1-496d-8700-3b3dbac1b6fd
caps.latest.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 9
---
# 디코딩할 URI가 올바른 인코딩이 아닙니다.
형식이 잘못된 URI\(Uniform Resource Identifier\)를 디코딩하려고 했습니다.  URI에 특별한 구문이 있으므로, 영숫자가 아닌 대부분의 문자는 인코딩을 해야 URI에 사용할 수 있습니다.  `encodeURI` 및 `encodeURIComponent` 메서드를 사용하여 일반 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 문자열에서 URI를 만들 수 있습니다.  
  
 완전한 URI는 구성 요소와 구분 기호의 시퀀스로 구성됩니다.  일반적인 형식은 다음과 같습니다.  
  
```javascript  
<Scheme>:<first>/<second>;<third>?<fourth>  
```  
  
 꺾쇠괄호의 이름은 구성 요소를 나타내며 ":", "\/", ";" 및 "?"는 구분 기호로 사용되는 예약 문자입니다.  
  
### 이 오류를 해결하려면  
  
-   유효한 URI만 디코딩하도록 합니다.  문자열에 잘못된 문자가 포함되어 있을 수 있기 때문에 일반 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 문자열을 디코딩할 수 없습니다.  
  
## 참고 항목  
 [decodeURI 함수](../../javascript/reference/decodeuri-function-javascript.md)   
 [decodeURIComponent 함수](../../javascript/reference/decodeuricomponent-function-javascript.md)