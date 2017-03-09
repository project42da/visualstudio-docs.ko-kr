---
title: "&#39;&lt;typename&gt;&#39;이 포함된 &lt;assemblyname&gt; 어셈블리 버전 &lt;laterversionnumber&gt;에 대한 간접 참조를 만듭니다. | Microsoft Docs"
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
  - "vbc32207"
  - "bc32207"
helpviewer_keywords: 
  - "BC32207"
ms.assetid: a3de74b5-bedd-4e36-b379-485e4b3903f7
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;&lt;typename&gt;&#39;이 포함된 &lt;assemblyname&gt; 어셈블리 버전 &lt;laterversionnumber&gt;에 대한 간접 참조를 만듭니다.
'\<typename\>'이 포함된 \<assemblyname\> 어셈블리 버전 \<laterversionnumber\>에 대한 간접 참조를 만듭니다. 이 프로젝트는 \<assemblyname\> 버전 \<earlierversionnumber\>의 이전 버전을 참조합니다. '\<typename\>'을 사용하려면 \<assemblyname\> 참조를 \<laterversionnumber\> 버전 이상으로 바꿔야 합니다.  
  
 식이 동일한 어셈블리의 이전 버전을 참조하는 다른 프로젝트를 간접적으로 참조합니다.  
  
 일반적으로 어셈블리의 가장 최근 버전만 사용해야 합니다.  
  
 **오류 ID:** BC32207  
  
### 이 오류를 해결하려면  
  
1.  해당 형식 이름을 사용하여 동일한 어셈블리를 참조하는 프로젝트를 확인합니다.  
  
2.  다른 프로젝트에서 참조하는 어셈블리 버전을 확인하고 동일한 버전을 참조하도록 프로젝트를 변경합니다.  
  
## 참고 항목  
 [프로젝트의 참조 관리](../ide/managing-references-in-a-project.md)   
 [NIB 방법: 참조 추가 대화 상자를 사용하여 참조 추가 또는 제거](http://msdn.microsoft.com/ko-kr/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)   
 [끊어진 참조 문제 해결](../ide/troubleshooting-broken-references.md)