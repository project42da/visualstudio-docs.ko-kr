---
title: "&#39;Microsoft.VisualBasic.ComClassAttribute&#39;는 기본 속성으로 0을 예약하므로 &#39;System.Runtime.InteropServices.DispIdAttribute&#39; 값을 &#39;&lt;typename&gt;&#39;에 적용할 수 없습니다. | Microsoft Docs"
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
  - "vbc32505"
  - "bc32505"
helpviewer_keywords: 
  - "BC32505"
ms.assetid: a7d5b948-2d72-48b1-8baf-bfaae36b0128
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;Microsoft.VisualBasic.ComClassAttribute&#39;는 기본 속성으로 0을 예약하므로 &#39;System.Runtime.InteropServices.DispIdAttribute&#39; 값을 &#39;&lt;typename&gt;&#39;에 적용할 수 없습니다.
<xref:System.Runtime.InteropServices.DispIdAttribute> 특성 블록에서 DISPID 값을 0으로 지정했는데 이 값은 `COMClassAttribute`에서 적용할 클래스 기본 속성을 나타내기 위해 예약되어 있습니다.  
  
 DISPID\(디스패치 식별자\)는 COM에서 `IDispatch:Invoke` 메서드에 대한 인수로서 COM 개체에서 노출하는 메서드와 속성에 액세스하는 데 사용됩니다.  
  
 **오류 ID:** BC32505  
  
### 이 오류를 해결하려면  
  
-   <xref:System.Runtime.InteropServices.DispIdAttribute>에서 0보다 큰 DISPID 값을 지정합니다.  
  
## 참고 항목  
 <xref:System.Runtime.InteropServices.DispIdAttribute>   
 [빌드에 없음: Visual Basic에서 사용되는 특성](http://msdn.microsoft.com/ko-kr/22231318-8a40-49af-9245-e0aab723563b)   
 [빌드에 없음: 특성 적용](http://msdn.microsoft.com/ko-kr/2b1703ed-4437-49b3-bc0b-568094324f47)   
 [ComClassAttribute 클래스](http://msdn.microsoft.com/ko-kr/5c2f0835-9210-47dc-bc59-5c1769953574)