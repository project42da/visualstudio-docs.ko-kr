---
title: "MSBuild 오류 MSB3117 | Microsoft Docs"
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
  - "MSBuild.GenerateManifest.HostInBrowserInvalidFrameworkVersion"
helpviewer_keywords: 
  - "MSB3117"
ms.assetid: 18aec642-6000-4626-bf75-f3547769c780
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB3117
**MSB3117: 응용 프로그램이 브라우저에서 호스팅하도록 설정되었으나 TargetFrameworkVersion이 v2.0으로 설정되었습니다.**  
  
 <xref:Microsoft.Build.Tasks.Deployment.ManifestUtilities.ApplicationManifest.HostInBrowser%2A> 속성을 `True`로 설정하여 WPF 웹 브라우저 응용 프로그램이 배포되었으나 TargetFrameworkVersion이 `v2.0` 또는 `v3.0`으로 설정되었습니다.  이 설정을 사용하는 경우 <xref:Microsoft.Build.Tasks.GenerateApplicationManifest.TargetFrameworkVersion%2A> 속성 값도 `v3.5` 이상으로 설정해야 합니다.  
  
### 이 오류를 해결하려면  
  
-   <xref:Microsoft.Build.Tasks.GenerateApplicationManifest.TargetFrameworkVersion%2A> 속성 값을 `v3.5` 이상으로 설정합니다.  
  
## 참고 항목  
 <xref:Microsoft.Build.Tasks.Deployment.ManifestUtilities.ApplicationManifest.HostInBrowser%2A>   
 <xref:Microsoft.Build.Tasks.GenerateApplicationManifest.TargetFrameworkVersion%2A>   
 [프로젝트 디자이너, 게시 페이지](../ide/reference/publish-page-project-designer.md)   
 [MSBuild 오류 MSB3116](../misc/msbuild-error-msb3116.md)   
 [MSBuild 오류 MSB3118](../misc/msbuild-error-msb3118.md)   
 [MSBuild 오류 MSB3174](../misc/msbuild-error-msb3174.md)   
 [MSBuild 오류 MSB3185](../misc/msbuild-error-msb3185.md)