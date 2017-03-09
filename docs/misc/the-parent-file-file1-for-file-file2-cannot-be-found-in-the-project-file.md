---
title: "The parent file, &#39;file1&#39;, for file &#39;file2&#39; cannot be found in the project file | Microsoft Docs"
ms.custom: ""
ms.date: "10/29/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.tasklisterror.projfile_missing_dependency"
ms.assetid: 1902c0b5-d09d-49b9-8f71-e325f7b9cfd7
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# The parent file, &#39;file1&#39;, for file &#39;file2&#39; cannot be found in the project file
프로젝트 시스템에서 파일에 해당하는 노드를 찾을 수 없습니다.  
  
 `<File>` 노드에 `DependentUpon` 특성을 추가하면 종속 파일이 프로젝트 파일에 남아 있습니다.  예를 들면 다음과 같습니다.  
  
```  
<File  
    RelPath = "Form1.resx"  
    SubType = "Code"  
    BuildAction = "EmbeddedResource"  
    DependentUpon="Form1.vb"  
/>  
```  
  
 그러면 프로젝트 계층에서 Form1.resx가 Form1.vb 아래에 나타납니다.  
  
 이 오류는 주로 프로젝트 파일을 직접 편집했을 때 발생합니다.  
  
### 이 오류를 해결하려면  
  
-   프로젝트 파일을 편집하고 업데이트합니다.  
  
     해당 파일은 프로젝트에 추가되지만 종속성은 유지되지 않습니다.  
  
## 참고 항목  
 [NIB: Project Properties \(Visual Studio\)](http://msdn.microsoft.com/ko-kr/eb4c97ed-f667-4850-98d0-6e2a4d21bbca)