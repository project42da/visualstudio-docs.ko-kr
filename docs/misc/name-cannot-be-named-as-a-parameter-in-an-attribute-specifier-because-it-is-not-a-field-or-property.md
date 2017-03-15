---
title: "&#39;&lt;name&gt;&#39;은 필드 또는 속성이 아니므로 특성 지정자에서 매개 변수로 명명할 수 없습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "10/25/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc32010"
  - "bc32010"
helpviewer_keywords: 
  - "BC32010"
ms.assetid: bfa68729-71ea-410e-bef1-83a7dab44d2a
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;name&gt;&#39;은 필드 또는 속성이 아니므로 특성 지정자에서 매개 변수로 명명할 수 없습니다.
특성 블록은 특성의 비가변 멤버에 대한 값을 설정합니다. 값은 필드 또는 속성과 같은 가변 멤버에만 할당할 수 있습니다.  
  
 **오류 ID:** BC32010  
  
### 이 오류를 해결하려면  
  
1.  특성 및 멤버 이름의 철자가 정확한지 확인합니다.  
  
2.  멤버가 비가변인 경우 특성 블록에서 인수를 제거합니다.  
  
## 참고 항목  
 [빌드에 없음: 특성 적용](http://msdn.microsoft.com/ko-kr/2b1703ed-4437-49b3-bc0b-568094324f47)