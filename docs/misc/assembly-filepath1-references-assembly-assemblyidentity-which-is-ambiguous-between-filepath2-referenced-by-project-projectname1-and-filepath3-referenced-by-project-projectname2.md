---
title: "&#39;&lt;filepath1&gt;&#39; 어셈블리가 &#39;&lt;projectname1&gt;&#39; 프로젝트에서 참조하는 &#39;&lt;filepath2&gt;와 &#39;&lt;projectname2&gt;&#39; 프로젝트에서 참조하는 &#39;&lt;filepath3&gt;&#39; 사이에서 모호한 &#39;&lt;assemblyidentity&gt;&#39; 어셈블리를 참조합니다. | Microsoft Docs"
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
  - "bc42204"
  - "vbc42204"
helpviewer_keywords: 
  - "BC42204"
ms.assetid: b0c3d2b6-2776-4981-b79e-2e36f03d4123
caps.latest.revision: 12
caps.handback.revision: 12
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;filepath1&gt;&#39; 어셈블리가 &#39;&lt;projectname1&gt;&#39; 프로젝트에서 참조하는 &#39;&lt;filepath2&gt;와 &#39;&lt;projectname2&gt;&#39; 프로젝트에서 참조하는 &#39;&lt;filepath3&gt;&#39; 사이에서 모호한 &#39;&lt;assemblyidentity&gt;&#39; 어셈블리를 참조합니다.
'\<filepath1\>' 어셈블리가 '\<projectname1\>' 프로젝트에서 참조하는 '\<filepath2\>와 '\<projectname2\>' 프로젝트에서 참조하는 '\<filepath3\>' 사이에서 모호한 '\<assemblyidentity\>' 어셈블리를 참조합니다. '\<filepath2\>'가 사용됩니다. 두 어셈블리가 동일하면 대상이 같도록 참조를 변경하세요.  
  
 어셈블리가 둘 이상의 파일 참조가 있는 다른 어셈블리의 형식에 액세스합니다.  
  
 컴파일러는 서로 다른 위치에 있는 파일이 동일한 어셈블리의 동일한 버전을 유지한다고 보장할 수 없습니다. 따라서 파일 참조가 모호하므로 컴파일러가 하나를 선택해야 합니다.  
  
 *어셈블리 ID*에는 어셈블리 이름, 버전, 공개 키\(있는 경우\) 및 문화권이 포함됩니다. 이 정보는 어셈블리를 고유하게 식별합니다.  
  
 이 메시지는 기본적으로 경고입니다. 경고를 숨기거나 오류로 처리하는 방법에 대한 자세한 내용은 [Visual Basic에서 경고 구성](../ide/configuring-warnings-in-visual-basic.md)을 참조하세요.  
  
 **오류 ID:** BC42204  
  
### 이 오류를 해결하려면  
  
1.  어떤 파일이 어셈블리에 대해 가장 좋은 선택을 나타내는지 결정합니다. 최신 버전, 파일의 접근성 및 적절할 때 업데이트할 가능성과 같은 조건을 사용할 수 있습니다.  
  
2.  선택한 파일에 대해 동일한 파일 경로를 사용하도록 모든 파일 참조를 이 어셈블리로 변경합니다.  
  
## 참고 항목  
 [빌드에 없음: 어셈블리](http://msdn.microsoft.com/ko-kr/6c5c7b30-fa78-4f40-b908-120d0743b0e6)   
 [공용 언어 런타임의 어셈블리](../Topic/Assemblies%20in%20the%20Common%20Language%20Runtime.md)   
 [어셈블리의 이점](../Topic/Assembly%20Benefits.md)   
 [프로젝트의 참조 관리](../ide/managing-references-in-a-project.md)   
 [NIB: 참조 관리](http://msdn.microsoft.com/ko-kr/910912ce-0dc9-4569-9274-32c44a20cb2c)   
 [NIB 방법: 참조 추가 대화 상자를 사용하여 참조 추가 또는 제거](http://msdn.microsoft.com/ko-kr/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)