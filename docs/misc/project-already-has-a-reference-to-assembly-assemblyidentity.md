---
title: "프로젝트에 이미 &lt;assemblyidentity&gt; 어셈블리에 대한 참조가 있습니다. | Microsoft Docs"
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
  - "bc32208"
  - "vbc32208"
helpviewer_keywords: 
  - "BC32208"
ms.assetid: a9f73a2c-5135-4315-bf2c-710ef216095d
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 프로젝트에 이미 &lt;assemblyidentity&gt; 어셈블리에 대한 참조가 있습니다.
프로젝트에 이미 \<assemblyidentity\> 어셈블리에 대한 참조가 있습니다. '\<filepath\>'에 대한 두 번째 참조를 추가할 수 없습니다.  
  
 프로젝트는 동일한 어셈블리에 대한 참조를 여러 개 만듭니다.  
  
 어셈블리 ID에는 어셈블리 이름, 버전, 공개 키\(있는 경우\) 및 문화권이 포함됩니다.  
  
 이 오류는 원래 참조와 다른 파일 경로를 통해 어셈블리의 다른 복사본을 참조한 경우 발생할 수 있습니다.  
  
 **오류 ID:** BC32208  
  
### 이 오류를 해결하려면  
  
-   두 번째 참조를 제거합니다. 동일한 어셈블리를 참조하므로 필요하지 않습니다.  
  
## 참고 항목  
 [프로젝트의 참조 관리](../ide/managing-references-in-a-project.md)   
 [NIB 방법: 참조 추가 대화 상자를 사용하여 참조 추가 또는 제거](http://msdn.microsoft.com/ko-kr/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)   
 [끊어진 참조 문제 해결](../ide/troubleshooting-broken-references.md)