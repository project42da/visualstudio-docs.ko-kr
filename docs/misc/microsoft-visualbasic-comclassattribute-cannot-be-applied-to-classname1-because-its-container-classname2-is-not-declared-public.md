---
title: "해당 컨테이너 &#39;&lt;classname2&gt;&#39;가 &#39;Public&#39;으로 선언되지 않았으므로 &#39;Microsoft.VisualBasic.ComClassAttribute&#39;를 &#39;&lt;classname1&gt;&#39;에 적용할 수 없습니다. | Microsoft Docs"
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
  - "vbc32504"
  - "bc32504"
helpviewer_keywords: 
  - "BC32504"
ms.assetid: 4138b639-88d6-4b51-afcd-c92a1be36f1c
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 해당 컨테이너 &#39;&lt;classname2&gt;&#39;가 &#39;Public&#39;으로 선언되지 않았으므로 &#39;Microsoft.VisualBasic.ComClassAttribute&#39;를 &#39;&lt;classname1&gt;&#39;에 적용할 수 없습니다.
`COMClassAttribute` 특성 블록을 사용하는 클래스가 `Public`이 아닌 클래스 내부에서 선언되었습니다. 클래스를 COM 개체로 노출해야 하는 경우 전체 포함 계층 구조를 `Public` 액세스 권한으로 선언해야 합니다.  
  
 **오류 ID:** BC32504  
  
### 이 오류를 해결하려면  
  
-   포함하는 모든 클래스를 `Public`으로 선언하거나 `COMClassAttribute` 특성 블록을 제거합니다.  
  
## 참고 항목  
 [빌드에 없음: Visual Basic에서 사용되는 특성](http://msdn.microsoft.com/ko-kr/22231318-8a40-49af-9245-e0aab723563b)   
 [빌드에 없음: 특성 적용](http://msdn.microsoft.com/ko-kr/2b1703ed-4437-49b3-bc0b-568094324f47)   
 [ComClassAttribute 클래스](http://msdn.microsoft.com/ko-kr/5c2f0835-9210-47dc-bc59-5c1769953574)   
 [Public](/dotnet/visual-basic/language-reference/modifiers/public)