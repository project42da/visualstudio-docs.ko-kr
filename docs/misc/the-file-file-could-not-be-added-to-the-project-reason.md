---
title: "&#39;file&#39; 파일을 프로젝트에 추가할 수 없습니다. &lt;이유&gt; | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.tasklisterror.projfile_no_add_file"
ms.assetid: 8bd70556-596a-4e24-a71c-a340604ee93d
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# &#39;file&#39; 파일을 프로젝트에 추가할 수 없습니다. &lt;이유&gt;
vbproj 또는 .csproj file 파일에서 읽은 파일을 프로젝트에 추가할 수 없습니다. 이유는 다음과 같습니다.  
  
-   파일 이름이 잘못되었습니다.  
  
-   경로 내에 파일이 있습니다. 예를 들어 File1\\File2.txt인 프로젝트 상대 경로를 사용하는데 상대 경로가 File1\\File2.txt인 폴더도 있습니다.  
  
-   항목이 이미 있습니다. 프로젝트 파일에 파일이 두 번 나열된 경우가 이에 해당합니다.  
  
-   링크가 이미 있습니다.[!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 및 [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] 프로젝트 시스템에서는 같은 이름의 링크를 프로젝트마다 하나씩만 만들 수 있습니다. 따라서 프로젝트의 A 폴더와 B 폴더에 file.vb에 대한 링크를 동시에 만들 수 없습니다.  
  
 이 오류는 주로 프로젝트 파일을 직접 편집했을 때 발생합니다.  
  
 이 진단 정보가 표시된 파일은 프로젝트에 추가되지 않습니다.  
  
## 참고 항목  
 [프로젝트 파일](/visual-cpp/ide/project-files)   
 [NIB: 프로젝트의 항목 관리](http://msdn.microsoft.com/ko-kr/762e606b-7f44-4b66-97a1-e30a703654a0)