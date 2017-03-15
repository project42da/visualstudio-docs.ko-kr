---
title: "MSBuild 오류 MSB2009 | Microsoft Docs"
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
  - "MSBuild.UnrecognizedAttribute"
helpviewer_keywords: 
  - "MSB2009"
ms.assetid: 34fd83b4-dead-49e5-b1ee-b23dc5a95244
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB2009
**'\<element name\>' 요소의 '\<attribute name\>' 특성이 잘못되었습니다.**  
  
 특성 이름의 철자가 정확하지 않거나 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]에서 인식할 수 없는 이름입니다.  
  
### 이 오류를 해결하려면  
  
-   특성 이름의 철자를 확인합니다.  
  
-   프로젝트 파일이 수정되었거나 손상되었는지 확인합니다.  프로젝트가 수정되거나 손상되었으면 프로젝트를 만든 버전의 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서 프로젝트를 열고 저장한 다음 다시 변환해 봅니다.  
  
## 참고 항목  
 [Project File Schema Reference](../msbuild/msbuild-project-file-schema-reference.md)