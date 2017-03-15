---
title: "MSBuild 오류 MSB2006 | Microsoft Docs"
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
  - "MSBuild.UnrecognizedElement"
helpviewer_keywords: 
  - "MSB2006"
ms.assetid: 89dc1b89-1621-46bc-9fe6-6d98cbcbebc8
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB2006
**프로젝트 파일에 \<{0}\> 루트 요소가 없습니다.**  
  
 루트 요소 이름의 철자가 정확하지 않거나 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]에서 인식할 수 없는 이름입니다.  
  
### 이 오류를 해결하려면  
  
-   요소 이름의 철자를 확인합니다.  
  
-   프로젝트 파일이 수정되었거나 손상되었는지 확인합니다.  프로젝트가 수정되거나 손상되었으면 프로젝트를 만든 버전의 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서 프로젝트를 열고 저장한 다음 다시 변환해 봅니다.  
  
## 참고 항목  
 [Project File Schema Reference](../msbuild/msbuild-project-file-schema-reference.md)   
 [추가 리소스](../msbuild/additional-msbuild-resources.md)