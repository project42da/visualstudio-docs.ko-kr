---
title: "&#39;&lt;projectname&gt;&#39; 프로젝트에는 &#39;&lt;assemblyname&gt;&#39; 어셈블리의 &#39;&lt;versionnumber1&gt;&#39; 버전에 대한 참조가 필요한데 해당 프로젝트가 &#39;&lt;assemblyname&gt;&#39; 어셈블리의 &#39;&lt;versionnumber2&gt;&#39; 버전을 참조합니다(Visual Basic 경고). | Microsoft Docs"
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
  - "vbc42203"
  - "bc42203"
helpviewer_keywords: 
  - "BC42203"
ms.assetid: 26a3fa34-ec5d-4817-a947-3959446a924a
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;projectname&gt;&#39; 프로젝트에는 &#39;&lt;assemblyname&gt;&#39; 어셈블리의 &#39;&lt;versionnumber1&gt;&#39; 버전에 대한 참조가 필요한데 해당 프로젝트가 &#39;&lt;assemblyname&gt;&#39; 어셈블리의 &#39;&lt;versionnumber2&gt;&#39; 버전을 참조합니다(Visual Basic 경고).
'\<projectname\>' 프로젝트에는 '\<assemblyname\>' 어셈블리의 '\<versionnumber1\>' 버전에 대한 참조가 필요한데 해당 프로젝트가 '\<assemblyname\>' 어셈블리의 '\<versionnumber2\>' 버전을 참조합니다. '\<versionnumber1\>' 버전에 대한 참조를 내보냈습니다.  
  
 프로젝트가 다른 곳에서 정의된 어셈블리를 간접적으로 참조하지만 해당 프로젝트가 해당 어셈블리의 이전 버전을 직접적으로 참조하기도 합니다.  
  
 이전 버전이 아닌 이후 버전에서 정의된 형식 및 프로그래밍 요소에 대한 액세스를 수용하기 위해 컴파일러는 액세스를 확인할 때 이후 버전에 대한 간접 참조를 사용합니다.  
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Visual Basic에서 경고 구성](../ide/configuring-warnings-in-visual-basic.md)을 참조하세요.  
  
 **오류 ID:** BC42203  
  
### 이 오류를 해결하려면  
  
-   이전 버전의 어셈블리에 대한 직접 참조를 제거하거나 이후 버전을 참조하도록 변경합니다.  
  
## 참고 항목  
 [공용 언어 런타임의 어셈블리](../Topic/Assemblies%20in%20the%20Common%20Language%20Runtime.md)   
 [NIB: 네임스페이스 및 구성 요소 참조](http://msdn.microsoft.com/ko-kr/568fa759-796b-44cd-bf5e-1cf8de6e38fd)   
 [프로젝트의 참조 관리](../ide/managing-references-in-a-project.md)   
 [NIB: 참조 관리](http://msdn.microsoft.com/ko-kr/910912ce-0dc9-4569-9274-32c44a20cb2c)   
 [NIB 방법: 참조 추가 대화 상자를 사용하여 참조 추가 또는 제거](http://msdn.microsoft.com/ko-kr/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)