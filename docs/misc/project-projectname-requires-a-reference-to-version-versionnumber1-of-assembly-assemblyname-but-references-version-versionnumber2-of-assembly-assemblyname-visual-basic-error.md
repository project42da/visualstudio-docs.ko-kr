---
title: "&#39;&lt;projectname&gt;&#39; 프로젝트는 &#39;&lt;assemblyname&gt;&#39; 어셈블리의 &#39;&lt;versionnumber1&gt;&#39; 버전을 참조해야 하지만 &#39;&lt;assemblyname&gt;&#39; 어셈블리의 &#39;&lt;versionnumber2&gt;&#39; 버전 참조는 필요하지 않습니다(Visual Basic 오류). | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc32209"
  - "bc32209"
helpviewer_keywords: 
  - "BC32209"
ms.assetid: fe50736b-444f-4e40-8f80-9760ff13a153
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;projectname&gt;&#39; 프로젝트는 &#39;&lt;assemblyname&gt;&#39; 어셈블리의 &#39;&lt;versionnumber1&gt;&#39; 버전을 참조해야 하지만 &#39;&lt;assemblyname&gt;&#39; 어셈블리의 &#39;&lt;versionnumber2&gt;&#39; 버전 참조는 필요하지 않습니다(Visual Basic 오류).
프로젝트는 다른 곳에서 정의된 어셈블리를 간접 참조하지만 해당 어셈블리의 이후 버전도 직접 참조합니다.  
  
 컴파일러가 코드에서 간접 참조를 사용하도록 허용한 경우 이후 버전에는 정의되어 있으나 이전 버전에는 정의되지 않은 형식 및 프로그래밍 요소에 액세스하지 못할 수 있습니다.  
  
 **오류 ID:** BC32209  
  
### 이 오류를 해결하려면  
  
-   이전 버전의 어셈블리에 대한 간접 참조를 제거하고 이후 버전에 대한 직접 참조를 사용합니다.  
  
## 참고 항목  
 [공용 언어 런타임의 어셈블리](../Topic/Assemblies%20in%20the%20Common%20Language%20Runtime.md)   
 [NIB: 네임스페이스 및 구성 요소 참조](http://msdn.microsoft.com/ko-kr/568fa759-796b-44cd-bf5e-1cf8de6e38fd)   
 [프로젝트의 참조 관리](../ide/managing-references-in-a-project.md)   
 [NIB: 참조 관리](http://msdn.microsoft.com/ko-kr/910912ce-0dc9-4569-9274-32c44a20cb2c)   
 [NIB 방법: 참조 추가 대화 상자를 사용하여 참조 추가 또는 제거](http://msdn.microsoft.com/ko-kr/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)