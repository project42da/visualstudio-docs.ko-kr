---
title: "&#39;Microsoft.VisualBasic.ComClassAttribute&#39;는 &#39;Public&#39;으로 선언되지 않았으므로 &#39;&lt;classname&gt;&#39;에 적용할 수 없습니다. | Microsoft Docs"
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
  - "bc32509"
  - "vbc32509"
helpviewer_keywords: 
  - "BC32509"
ms.assetid: ac46851f-53ab-4ce6-87b1-4c4d29508527
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Microsoft.VisualBasic.ComClassAttribute&#39;는 &#39;Public&#39;으로 선언되지 않았으므로 &#39;&lt;classname&gt;&#39;에 적용할 수 없습니다.
클래스가 <xref:Microsoft.VisualBasic.ComClassAttribute>로 선언되었지만 해당 선언이 `Public`을 지정하지 않습니다.  
  
 COM interop에 적합하려면 .NET Framework 클래스가 다음 요구 사항을 충족해야 합니다.  
  
-   `Public`이어야 하고 해당하는 모든 컨테이너가 `Public`이어야 하며 하나 이상의 `Public` 멤버를 노출해야 합니다.  
  
-   *추상*이어서는 안 됩니다. 즉, `MustInherit`로 선언되지 않아야 합니다.  
  
-   제네릭이 아니어야 하고 제네릭 컨테이너 형식 내에서 선언되지 않아야 합니다.  
  
 **오류 ID:** BC32509  
  
### 이 오류를 해결하려면  
  
-   `Public` 키워드를 클래스 선언에 추가합니다.  
  
     또는  
  
-   클래스 또는 그 포함 요소가 `Public`일 수 없는 경우 클래스 선언에서 <xref:Microsoft.VisualBasic.ComClassAttribute>를 제거합니다. COM에 노출할 수 없습니다.  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.ComClassAttribute>   
 [COM Interop](/dotnet/visual-basic/programming-guide/com-interop/index)   
 [Public](/dotnet/visual-basic/language-reference/modifiers/public)