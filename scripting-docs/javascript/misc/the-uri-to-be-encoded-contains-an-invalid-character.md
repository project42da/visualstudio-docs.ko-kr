---
title: "인코딩할 URI에 잘못된 문자가 있습니다. | Microsoft Docs"
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
  - "VS.WebClient.Help.SCRIPT5024"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
ms.assetid: a3f0fdbb-8d4b-41ae-a396-43dfc9483760
caps.latest.revision: 8
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 8
---
# 인코딩할 URI에 잘못된 문자가 있습니다.
문자열을 URI\(Uniform Resource Identifier\)로 인코딩하려고 했지만 잘못된 문자가 포함되어 있습니다.  문자열 내에서 대부분의 문자가 URI로 변환하는 데 올바르지만 일부 유니코드 문자 시퀀스는 사용할 수 없습니다.  
  
### 이 오류를 해결하려면  
  
-   인코딩할 문자열에 올바른 유니코드 시퀀스만 포함되는지 확인하세요.  완전한 URI는 구성 요소와 구분 기호의 시퀀스로 구성됩니다.  꺾쇠괄호의 이름은 구성 요소를 나타내며 ":", "\/", ";" 및 "?"는 구분 기호로 사용되는 예약 문자입니다.  일반적인 형식은 다음과 같습니다.  
  
    ```javascript  
    <Scheme>:<first>/<second>;<third>?<fourth>  
    ```  
  
## 참고 항목  
 [encodeURI 함수](../../javascript/reference/encodeuri-function-javascript.md)   
 [encodeURIComponent 함수](../../javascript/reference/encodeuricomponent-function-javascript.md)