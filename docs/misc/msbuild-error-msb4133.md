---
title: "MSBuild 오류 MSB4133 | Microsoft Docs"
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
  - "MSB4133"
ms.assetid: 5f18937a-fda1-4315-81f9-7cee02802a6d
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB4133
**MSB4133: 기본 도구 버전 "\<x.x.\>"이\(가\) 지정되었지만 해당 정의를 찾을 수 없습니다.**  
  
 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]가 프로젝트 파일에 `DefaultToolsVersion`으로 정의된 도구 집합을 찾을 수 없습니다.  
  
### 이 오류를 해결하려면  
  
-   `DefaultToolsVersion`이 제대로 지정되어 있고 이 도구 집합이 레지스트리나 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 구성 파일에 정의되어 있는지 확인합니다.  
  
## 참고 항목  
 <xref:Microsoft.Build.BuildEngine.Toolset>   
 [Project Element \(MSBuild\)](../msbuild/project-element-msbuild.md)   
 [추가 리소스](../msbuild/additional-msbuild-resources.md)