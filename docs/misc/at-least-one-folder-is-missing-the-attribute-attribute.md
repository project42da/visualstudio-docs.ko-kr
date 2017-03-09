---
title: "At least one folder is missing the &#39;attribute&#39; attribute | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.tasklisterror.projfile_missing_fold_attrib"
ms.assetid: 3a0498a9-df61-47d8-a228-f88f4f138df8
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# At least one folder is missing the &#39;attribute&#39; attribute
.vbproj 또는 .csproj 파일에서 읽은 폴더 노드에 프로젝트 시스템이 필요로 하는 특정 특성이 없습니다.  현재 이러한 특성은 프로젝트 폴더에서 특정 폴더가 놓일 위치를 지정하는 **RelPath** 특성 하나뿐입니다.  
  
 이 오류는 주로 프로젝트 파일을 직접 편집했을 때 발생합니다.  
  
 **이 오류를 해결하려면**  
  
-   프로젝트 파일에서 영향을 받는 폴더 노드를 제거합니다.  또한 폴더가 디스크에 남아 있으면 솔루션 탐색기 도구에서 모든 파일 표시 단추를 클릭하여 이 모드를 표시하도록 전환하고 해당 폴더를 마우스 오른쪽 단추로 클릭한 다음 **프로젝트에 포함**을 선택합니다.  
  
     특성이 없는 폴더는 프로젝트에 추가되지 않습니다.  
  
## 참고 항목  
 [프로젝트 파일](/visual-cpp/ide/project-files)   
 [NIB: Project Properties \(Visual Studio\)](http://msdn.microsoft.com/ko-kr/eb4c97ed-f667-4850-98d0-6e2a4d21bbca)