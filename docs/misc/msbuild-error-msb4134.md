---
title: "MSBuild 오류 MSB4134 | Microsoft Docs"
ms.custom: ""
ms.date: "11/24/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "MSB4134"
ms.assetid: 2e4e6beb-c0c9-40ef-b75c-1c16244eba10
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB4134
**MSB4134: 프로젝트를 엔진으로 로드한 다음에는 DefaultToolsVersion을 설정할 수 없습니다.**  
  
 이 오류는 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]에서 프로젝트가 이미 빌드된 후에 `DefaultToolsVersion`의 값을 변경하려고 할 경우 발생합니다.  
  
### 이 오류를 해결하려면  
  
-   프로젝트를 빌드하기 전에 `DefaultToolsVersion`의 값을 변경합니다.  
  
## 참고 항목  
 <xref:Microsoft.Build.Utilities.Task.BuildEngine%2A>   
 <xref:Microsoft.Build.Utilities.Task.BuildEngine2%2A>   
 [Project Element \(MSBuild\)](../msbuild/project-element-msbuild.md)   
 [추가 리소스](../msbuild/additional-msbuild-resources.md)