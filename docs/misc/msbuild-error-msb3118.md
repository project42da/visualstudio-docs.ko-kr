---
title: "MSBuild 오류 MSB3118 | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "MSBuild.GenerateManifest.UseApplicationTrustInvalidFrameworkVersion"
helpviewer_keywords: 
  - "MSB3118"
ms.assetid: 9bf5b430-0cfb-4da5-a7f7-04d69f20cce1
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB3118
**MSB3118: 응용 프로그램 신뢰를 사용하도록 응용 프로그램이 설정되었으나 TargetFrameworkVersion이 v3.5가 아닙니다.**  
  
 이 오류는 <xref:Microsoft.Build.Tasks.GenerateApplicationManifest.UseApplicationTrust%2A> 속성을 `True`로 설정하고 <xref:Microsoft.Build.Tasks.GenerateApplicationManifest.TargetFrameworkVersion%2A> 속성을 `v3.5`보다 낮은 버전\(예: `v2.0`\)으로 설정한 경우 발생합니다.  
  
### 이 오류를 해결하려면  
  
-   <xref:Microsoft.Build.Tasks.GenerateApplicationManifest.TargetFrameworkVersion%2A> 속성을 `v3.5` 이상으로 설정합니다.  
  
## 참고 항목  
 <xref:Microsoft.Build.Tasks.Deployment.ManifestUtilities.ApplicationManifest.UseApplicationTrust%2A>   
 <xref:Microsoft.Build.Tasks.GenerateApplicationManifest.UseApplicationTrust%2A>   
 <xref:Microsoft.Build.Tasks.GenerateApplicationManifest.TargetFrameworkVersion%2A>   
 <xref:Microsoft.Build.Tasks.Deployment.ManifestUtilities.ApplicationManifest.HostInBrowser%2A>   
 [프로젝트 디자이너, 게시 페이지](../ide/reference/publish-page-project-designer.md)   
 [MSBuild 오류 MSB3116](../misc/msbuild-error-msb3116.md)   
 [MSBuild 오류 MSB3117](../misc/msbuild-error-msb3117.md)   
 [MSBuild 오류 MSB3119](../misc/msbuild-error-msb3119.md)   
 [MSBuild 오류 MSB3174](../misc/msbuild-error-msb3174.md)   
 [MSBuild 오류 MSB3185](../misc/msbuild-error-msb3185.md)