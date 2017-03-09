---
title: "디자이너에서 생성된 형식 &#39;&lt;type&gt;&#39;의 &#39;&lt;constructor&gt;&#39;가 InitializeComponent 메서드를 호출해야 합니다. | Microsoft Docs"
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
  - "vbc40054"
  - "bc40054"
helpviewer_keywords: 
  - "BC40054"
ms.assetid: beac93b0-d427-4df6-9582-fd69c7a53673
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 디자이너에서 생성된 형식 &#39;&lt;type&gt;&#39;의 &#39;&lt;constructor&gt;&#39;가 InitializeComponent 메서드를 호출해야 합니다.
디자이너에서 생성한 형식의 생성자가 해당 형식의 `InitializeComponent` 메서드를 호출하지 않습니다.  
  
 디자이너에서 생성한 형식의 각 생성자는 해당 형식의 `InitializeComponent` 메서드를 호출해야 합니다.  
  
 **오류 ID:** BC40054  
  
### 이 오류를 해결하려면  
  
-   생성자에서 `InitializeComponent` 메서드에 호출을 추가합니다.  
  
## 참고 항목  
 <xref:Microsoft.VisualBasic.CompilerServices.DesignerGeneratedAttribute>   
 [빌드에 없음: 생성자 및 소멸자 사용](http://msdn.microsoft.com/ko-kr/548eebe1-86c4-4377-b2f5-447cb8be3d90)