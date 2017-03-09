---
title: "MSBuild 오류 MSB4132 | Microsoft Docs"
ms.custom: ""
ms.date: "11/23/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "MSB4132"
ms.assetid: 4ac265a7-0f8d-4fec-ba6e-cd70cbd5d89e
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB4132
**MSB4132: 도구 버전 "'\<버전\>'"을\(를\) 인식할 수 없습니다.**  
  
 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]에서는 지정된 `ToolsVersion` 값에 해당하는 도구 집합을 찾을 수 있습니다.  
  
### 이 오류를 해결하려면  
  
-   MSBuild **\/ToolsVersion** 스위치를 사용할 때 프로젝트 태그나 명령줄에서 올바른 `ToolsVersion` 값을 지정합니다.  
  
## 참고 항목  
 <xref:Microsoft.Build.Tasks.MSBuild.ToolsVersion%2A>   
 [추가 리소스](../msbuild/additional-msbuild-resources.md)