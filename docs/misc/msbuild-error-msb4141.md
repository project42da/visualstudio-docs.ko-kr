---
title: "MSBuild 오류 MSB4141 | Microsoft Docs"
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
  - "MSB4141"
ms.assetid: 0d190884-e64d-4d6b-817d-ce4644788fce
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB4141
**MSB4141: ToolsVersion "\<x.x\>"에 대해 MSBuildToolsPath가 지정되지 않았습니다.**  
  
 `MSBuildToolsPath`에 대해 사용자 지정 도구 집합은 정의되어 있지만 값은 지정되어 있지 않습니다.  
  
### 이 오류를 해결하려면  
  
-   레지스트리나 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)] 구성 파일에 사용자 지정 도구 집합을 정의할 때 올바른 `MSBuildToolsPath` 값을 지정합니다.  
  
## 참고 항목  
 [표준 및 사용자 지정 도구 집합 구성](../msbuild/standard-and-custom-toolset-configurations.md)   
 [Project Element \(MSBuild\)](../msbuild/project-element-msbuild.md)   
 [추가 리소스](../msbuild/additional-msbuild-resources.md)