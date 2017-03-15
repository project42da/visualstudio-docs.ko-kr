---
title: "&#39;&lt;typename&gt;&#39;의 &#39;Microsoft.VisualBasic.ComClassAttribute&#39;에 대한 &#39;InterfaceId&#39; 및 &#39;EventsId&#39; 매개 변수에는 같은 값을 사용할 수 없습니다. | Microsoft Docs"
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
  - "bc32507"
  - "vbc32507"
helpviewer_keywords: 
  - "BC32507"
ms.assetid: 762e2990-e578-492d-b8ee-11658b6069fc
caps.latest.revision: 11
caps.handback.revision: 11
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;typename&gt;&#39;의 &#39;Microsoft.VisualBasic.ComClassAttribute&#39;에 대한 &#39;InterfaceId&#39; 및 &#39;EventsId&#39; 매개 변수에는 같은 값을 사용할 수 없습니다.
`COMClassAttribute` 특성 블록은 생성 이벤트와 마찬가지로 인터페이스에 대한 GUID\(Globally Unique IDentifier\)를 지정합니다. 두 식별자를 모두 제공하는 경우 서로 달라야 합니다. 클래스 식별자와도 달라야 합니다.  
  
 GUID는 16바이트로 구성되며, 그중에서 처음 8바이트는 숫자이고 마지막 8바이트는 이진입니다. uuidgen.exe와 같은 Microsoft 유틸리티에서 생성되며 고유성이 보장됩니다.  
  
 **오류 ID:** BC32507  
  
### 이 오류를 해결하려면  
  
1.  COM 개체에 대한 인터페이스 및 생성 이벤트를 식별하는 데 필요한 올바른 GUID를 확인합니다.  
  
2.  `COMClassAttribute` 특성 블록에 제공되는 GUID 문자열이 올바르게 복사되었는지 확인합니다.  
  
## 참고 항목  
 [빌드에 없음: Visual Basic에서 사용되는 특성](http://msdn.microsoft.com/ko-kr/22231318-8a40-49af-9245-e0aab723563b)   
 [빌드에 없음: 특성 적용](http://msdn.microsoft.com/ko-kr/2b1703ed-4437-49b3-bc0b-568094324f47)   
 [ComClassAttribute 클래스](http://msdn.microsoft.com/ko-kr/5c2f0835-9210-47dc-bc59-5c1769953574)