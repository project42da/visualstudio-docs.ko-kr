---
title: "특성 지정자 문이 종결되지 않았습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc32035"
  - "bc32035"
helpviewer_keywords: 
  - "BC32035"
ms.assetid: a0ddd673-4170-4bea-9c22-777d7bf21dfd
caps.latest.revision: 10
caps.handback.revision: 10
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 특성 지정자 문이 종결되지 않았습니다.
특성 지정자 문이 종결되지 않았습니다. 줄 연속 문자를 사용하여 다음 문에 특성을 적용하세요.  
  
 특성 블록이 소스 코드 줄에서 단독으로 사용되었습니다. 선언문의 시작 부분에 특성을 적용해야 하며 해당 문의 일부여야 합니다.  
  
 **오류 ID:** BC32035  
  
### 이 오류를 해결하려면  
  
-   선언문이 다음 줄에 있는 경우 특성 블록 뒤에 공백과 밑줄\(`_`\)을 추가하여 소스 코드 줄을 결합합니다.  
  
-   특성 블록과 연결된 선언문이 없는 경우 선언문을 제공하거나 특성 블록을 제거합니다.  
  
-   전체 어셈블리 또는 현재 어셈블리 모듈에 특성을 적용해야 하는 경우 특성 블록을 별도의 소스 코드 줄에 유지합니다. 꺾쇠 괄호 안의 특성 이름\(`< >`\) 앞에 `Assembly:` 또는 `Module:`을 추가하고 특성 블록 뒤에 공백이나 밑줄을 추가하지 않습니다. 또한 이 특성 블록은 소스 파일의 시작 부분에 있어야 합니다.  
  
## 참고 항목  
 [빌드에 없음: 특성 적용](http://msdn.microsoft.com/ko-kr/2b1703ed-4437-49b3-bc0b-568094324f47)   
 [방법: 코드에서 문 분리 및 결합](../Topic/How%20to:%20Break%20and%20Combine%20Statements%20in%20Code%20\(Visual%20Basic\).md)