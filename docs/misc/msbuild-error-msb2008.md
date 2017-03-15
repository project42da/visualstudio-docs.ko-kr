---
title: "MSBuild 오류 MSB2008 | Microsoft Docs"
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
  - "MSBuild.UnrecognizedChildElement"
helpviewer_keywords: 
  - "MSB2008"
ms.assetid: 3c2afda0-a116-4b2f-af0c-c0f0d1541325
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB2008
**이 Visual Studio 프로젝트 시스템에서 "{0}" 프로젝트를 변환할 수 없습니다.  C\# 및 VB 클라이언트 프로젝트만 변환할 수 있습니다.**  
  
 유효한 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 및 [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] 프로젝트만 [!INCLUDE[vstecmsbuild](../extensibility/internals/includes/vstecmsbuild_md.md)]를 사용하여 변환될 수 있습니다.  
  
### 이 오류를 해결하려면  
  
-   프로젝트가 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 또는 [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] 프로젝트인 경우 프로젝트 파일이 수정되었거나 손상되었는지 확인합니다.  프로젝트가 수정되거나 손상되었으면 프로젝트를 만든 버전의 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서 프로젝트를 열고 저장한 다음 다시 변환해 봅니다.  
  
-   프로젝트가 [!INCLUDE[vbprvb](../code-quality/includes/vbprvb_md.md)] 또는 [!INCLUDE[csprcs](../data-tools/includes/csprcs_md.md)] 프로젝트가 아닌 경우 적절한 도구를 사용하여 변환합니다.  
  
## 참고 항목  
 [추가 리소스](../msbuild/additional-msbuild-resources.md)