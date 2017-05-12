---
title: "&#39;this&#39;에 할당할 수 없습니다. | Microsoft Docs"
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
  - "VS.WebClient.Help.SCRIPT5000"
dev_langs: 
  - "JavaScript"
  - "TypeScript"
  - "DHTML"
ms.assetid: ba2b0a2b-f0f8-4698-b335-a4ab6c166671
caps.latest.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 7
---
# &#39;this&#39;에 할당할 수 없습니다.
**this**에 값을 할당하려고 했습니다.  **this**는 다음 중 하나를 참조하는 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 키워드입니다.  
  
-   현재 메서드를 실행 중인 개체  
  
-   현재 메서드가 없거나 메서드가 다른 개체에 속하지 않는 경우 전역 개체  
  
 메서드는 개체를 통해 호출된 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 함수입니다.  메서드 내에서 **this** 키워드는 메서드가 호출된 개체\(**new** 연산자로 클래스 생성자를 호출하여 생성된 개체\)에 대한 참조입니다.  
  
 메서드 내에서 **this**를 사용하여 현재 개체를 참조할 수 있지만 **this**에 새 값을 할당할 수는 없습니다.  
  
### 이 오류를 해결하려면  
  
-   **this**에 할당하지 마십시오.  인스턴스화된 개체의 속성이나 메서드에 액세스하려면 도트 연산자\(예를 들어 circle**.**radius\)를 사용하세요.  
  
    > [!NOTE]
    >  사용자가 생성한 변수의 이름을 **this**로 지정할 수 없습니다. 이 단어는 [!INCLUDE[javascript](../../javascript/includes/javascript-md.md)] 예약어입니다.  
  
## 참고 항목  
 [this 문](../../javascript/reference/this-statement-javascript.md)   
 [스크립트 문제 해결](../../javascript/advanced/troubleshooting-your-scripts-javascript.md)