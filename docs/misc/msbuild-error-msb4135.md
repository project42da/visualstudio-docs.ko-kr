---
title: "MSBuild 오류 MSB4135 | Microsoft Docs"
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
  - "MSB4135"
ms.assetid: 9192f772-ad13-42f7-b53f-c5e31846fa5f
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB4135
**MSB4135: 레지스트리 키 "'\<key\>'" 또는 하위 키 '  \<key\>'에서 도구 집합 정보를 읽는 동안 오류가 발생했습니다.**  
  
 레지스트리에 정의된 사용자 지정 도구 집합 정보를 읽을 수 없습니다.  
  
### 이 오류를 해결하려면  
  
-   레지스트리에 사용자 지정 도구 집합을 정의한 경우 이러한 도구 집합이 올바른 레지스트리 형식으로 되어 있고 해당 `ToolsVersion` 이름과 `MSBuildBinPath` 또는 `MSBuildToolsPath` 값이 올바른지 확인합니다.  
  
## 참고 항목  
 [표준 및 사용자 지정 도구 집합 구성](../msbuild/standard-and-custom-toolset-configurations.md)   
 [Project Element \(MSBuild\)](../msbuild/project-element-msbuild.md)   
 [추가 리소스](../msbuild/additional-msbuild-resources.md)