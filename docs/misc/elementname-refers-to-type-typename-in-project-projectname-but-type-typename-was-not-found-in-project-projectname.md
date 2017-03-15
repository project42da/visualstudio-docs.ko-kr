---
title: "&#39;&lt;elementname&gt;&#39;은 &#39;&lt;projectname&gt;&#39; 프로젝트의 &#39;&lt;typename&gt;&#39; 형식을 참조하지만 &#39;&lt;typename&gt;&#39; 형식이 &#39;&lt;projectname&gt;&#39; 프로젝트에 없습니다. | Microsoft Docs"
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
  - "vbc30960"
  - "bc30960"
helpviewer_keywords: 
  - "BC30960"
ms.assetid: 4ed4bff5-c670-46f6-8360-7287444d50e5
caps.latest.revision: 6
caps.handback.revision: 6
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;elementname&gt;&#39;은 &#39;&lt;projectname&gt;&#39; 프로젝트의 &#39;&lt;typename&gt;&#39; 형식을 참조하지만 &#39;&lt;typename&gt;&#39; 형식이 &#39;&lt;projectname&gt;&#39; 프로젝트에 없습니다.
식이 다른 프로젝트에서 참조된 클래스, 구조체, 모듈 또는 인터페이스에 액세스하지만 해당 프로젝트에 지정된 형식이 포함되어 있지 않습니다.  
  
 이 오류는 프로젝트가 동일한 솔루션의 다른 프로젝트를 간접적으로 참조하는 경우에 발생합니다. 일반적으로 프로젝트는 다른 프로젝트를 참조하는 어셈블리를 참조합니다. 어셈블리가 다른 프로젝트의 지정된 형식에 액세스하는 경우 형식에 대한 간접 참조가 설정됩니다. 그러나 다른 프로젝트에 형식이 없는 경우 이 오류가 생성됩니다.  
  
 **오류 ID:** BC30960  
  
### 이 오류를 해결하려면  
  
-   해당 형식이 더 이상 정의되어 있지 않으면 액세스하려는 문을 제거하거나 바꿉니다. 해당 형식에 대한 간접 참조를 제공하는 어셈블리에서도 동일하게 변경해야 할 수 있습니다.  
  
-   해당 형식이 다른 위치에 정의되어 있으면 정의하는 프로젝트 또는 어셈블리를 직접 참조합니다.  
  
## 참고 항목  
 [NIB: 네임스페이스 및 구성 요소 참조](http://msdn.microsoft.com/ko-kr/568fa759-796b-44cd-bf5e-1cf8de6e38fd)   
 [프로젝트의 참조 관리](../ide/managing-references-in-a-project.md)   
 [NIB: 참조 관리](http://msdn.microsoft.com/ko-kr/910912ce-0dc9-4569-9274-32c44a20cb2c)   
 [NIB 방법: 참조 추가 대화 상자를 사용하여 참조 추가 또는 제거](http://msdn.microsoft.com/ko-kr/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)