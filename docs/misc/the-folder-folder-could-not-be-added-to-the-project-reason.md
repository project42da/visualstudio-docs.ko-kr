---
title: "The folder &#39;folder&#39; could not be added to the project. &lt;reason&gt; | Microsoft Docs"
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
  - "vs.tasklisterror.projfile_no_add_folder"
ms.assetid: 3f6a5aa7-17cc-4e78-93b7-96e0970e111e
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# The folder &#39;folder&#39; could not be added to the project. &lt;reason&gt;
.vbproj 또는 .csproj 파일에서 읽은 폴더를 프로젝트에 추가할 수 없습니다.  이유는 다음과 같습니다.  
  
-   이름이 잘못되었습니다.  
  
-   경로 내에 파일이 있습니다.  예를 들어, Folder1\\Folder2\\Folder3이라는 프로젝트의 상대 경로를 사용하는데 상대 경로가 Folder1\\Folder2인 파일이 있습니다.  
  
-   항목이 이미 있습니다.  프로젝트 파일에 폴더가 두 번 나열된 경우가 이에 해당합니다.  
  
 이 오류는 주로 프로젝트 파일을 직접 편집했을 때 발생합니다.  
  
 **이 오류를 해결하려면**  
  
-   프로젝트 파일에서 영향을 받는 폴더 노드를 제거합니다.  
  
     이 진단 정보가 표시된 폴더 아래에 있는 폴더와 파일은 프로젝트에 추가되지 않습니다.  
  
## 참고 항목  
 [프로젝트 파일](/visual-cpp/ide/project-files)   
 [NIB: Project Properties \(Visual Studio\)](http://msdn.microsoft.com/ko-kr/eb4c97ed-f667-4850-98d0-6e2a4d21bbca)