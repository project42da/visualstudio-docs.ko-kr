---
title: "MSBuild 오류 MSB4140 | Microsoft Docs"
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
  - "MSB4140"
ms.assetid: 13546558-4ed4-44c2-89a6-f69a2b43ed07
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB4140
**MSB4140: 기본 ToolsVersion이 레지스트리나 구성 파일에 지정되어 있지 않습니다.**  
  
 프로젝트에서 기본 `ToolsVersion` 값을 지정하지 않습니다.  따라서 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]에서는 어떤 값을 사용해야 하는지 알지 못합니다.  
  
### 이 오류를 해결하려면  
  
-   `DefaultToolsVersion` 값이 도구 집합이 정의된 레지스트리나 구성 파일\(예 msbuild.exe.config\)에 지정되어 있는지 확인합니다.  
  
## 참고 항목  
 [표준 및 사용자 지정 도구 집합 구성](../msbuild/standard-and-custom-toolset-configurations.md)   
 [Project Element \(MSBuild\)](../msbuild/project-element-msbuild.md)   
 [추가 리소스](../msbuild/additional-msbuild-resources.md)