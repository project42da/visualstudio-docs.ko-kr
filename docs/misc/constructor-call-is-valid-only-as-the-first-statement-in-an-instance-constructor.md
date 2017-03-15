---
title: "인스턴스 생성자의 첫째 문으로만 생성자를 호출할 수 있습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc30282"
  - "bc30282"
helpviewer_keywords: 
  - "BC30282"
ms.assetid: c51b172f-fbd7-4ef5-8276-01a4bf6ed35b
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 인스턴스 생성자의 첫째 문으로만 생성자를 호출할 수 있습니다.
`New()` 호출이 생성자의 첫 번째 문 다음에 발생합니다. 한 생성자가 다른 생성자를 명시적으로 호출하는 경우 `Sub New()` 문 다음의 첫 번째 문에서 호출해야 합니다.  
  
 **오류 ID:** BC30282  
  
### 이 오류를 해결하려면  
  
-   `New()` 호출을 제거하거나 생성자의 시작 부분으로 이동합니다.  
  
## 참고 항목  
 [빌드에 없음: 생성자 및 소멸자 사용](http://msdn.microsoft.com/ko-kr/548eebe1-86c4-4377-b2f5-447cb8be3d90)