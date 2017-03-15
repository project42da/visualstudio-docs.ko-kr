---
title: "&#39;Microsoft.VisualBasic.ComClassAttribute&#39;는 제네릭 또는 제네릭 형식에 중첩된 클래스에 적용할 수 없습니다. | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc31527"
  - "bc31527"
helpviewer_keywords: 
  - "BC31527"
ms.assetid: ea125bff-d020-4933-b277-6e24943eea88
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Microsoft.VisualBasic.ComClassAttribute&#39;는 제네릭 또는 제네릭 형식에 중첩된 클래스에 적용할 수 없습니다.
클래스가 <xref:Microsoft.VisualBasic.ComClassAttribute>를 사용하여 선언되지만 이 클래스는 제네릭이거나 제네릭 클래스 또는 구조체에 포함되어 있습니다.  
  
 COM interop에 적합하려면 .NET Framework 클래스가 다음 요구 사항을 충족해야 합니다.  
  
-   `Public`이어야 하고 해당하는 모든 컨테이너가 `Public`이어야 하며 하나 이상의 `Public` 멤버를 노출해야 합니다.  
  
-   *추상*이어서는 안 됩니다. 즉, `MustInherit`로 선언되지 않아야 합니다.  
  
-   제네릭이 아니어야 하고 제네릭 컨테이너 형식 내에서 선언되지 않아야 합니다.  
  
 **오류 ID:** BC31527  
  
### 이 오류를 해결하려면  
  
-   제네릭이 되지 않도록 클래스의 선언을 변경하고 포함하는 요소가 제네릭이 아닌지 확인합니다.  
  
     또는  
  
-   클래스 또는 포함하는 요소가 제네릭이어야 하는 경우 클래스 선언에서 <xref:Microsoft.VisualBasic.ComClassAttribute>를 제거합니다. COM에 노출할 수 없습니다.  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.ComClassAttribute>   
 [COM Interop](/dotnet/visual-basic/programming-guide/com-interop/index)   
 [Visual Basic의 제네릭 형식](/dotnet/visual-basic/programming-guide/language-features/data-types/generic-types)