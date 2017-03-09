---
title: "제네릭 메서드를 COM에 노출할 수 없습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc30943"
  - "bc30943"
helpviewer_keywords: 
  - "BC30943"
ms.assetid: 0e3bff62-f187-4864-8520-70f6be22e869
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 제네릭 메서드를 COM에 노출할 수 없습니다.
하나 이상의 제네릭 프로시저를 포함하는 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 구성 요소가 COM 구성 요소로 내보내집니다.  
  
 COM\(구성 요소 개체 모델\)은 제네릭 형식을 지원하지 않으며 상호 작용할 수 없습니다.  
  
 **오류 ID:** BC30943  
  
### 이 오류를 해결하려면  
  
-   [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 구성 요소에서 제네릭 프로시저를 제거하거나 COM interop에 사용하지 마세요.  
  
## 참고 항목  
 [Visual Basic의 제네릭 형식](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)   
 [COM Interop](/dotnet/visual-basic/programming-guide/com-interop/index)