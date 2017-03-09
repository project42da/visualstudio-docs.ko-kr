---
title: "이 식에는 &#39;System.Void&#39; 형식의 배열을 사용할 수 없습니다. | Microsoft Docs"
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
  - "vbc31428"
  - "bc31428"
helpviewer_keywords: 
  - "BC31428"
ms.assetid: 21d77b56-585f-4107-b7ec-21933ba58017
caps.latest.revision: 5
caps.handback.revision: 5
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 이 식에는 &#39;System.Void&#39; 형식의 배열을 사용할 수 없습니다.
대입문 또는 선언의 식은 <xref:System.Void> 형식의 배열을 지정합니다.  
  
 <xref:System.Void> 구조체는 .NET Framework에서 내부적으로, 그리고 Visual C\# 및 Visual C\+\+에서 특별하게 사용되는 특수화된 형식입니다. 값을 반환하지 않는 메서드에 대한 반환 값 형식을 나타냅니다. Visual Basic에서는 값이 반환되지 않을 때 `Sub` 프로시저를 사용하고 값이 반환될 때 `Function` 프로시저를 사용합니다.  
  
 <xref:System.Void> 형식의 배열은 의미가 없으며 모든 컨텍스트에서 허용되지 않습니다.  
  
 **오류 ID:** BC31428  
  
### 이 오류를 해결하려면  
  
1.  배열을 지정하는 괄호를 제거합니다.  
  
2.  런타임 형식을 <xref:System.Void>와 비교할 특별한 이유가 없다면 이에 대한 참조도 함께 제거합니다.  
  
## 참고 항목  
 <xref:System.Void>