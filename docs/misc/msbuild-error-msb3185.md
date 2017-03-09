---
title: "MSBuild 오류 MSB3185 | Microsoft Docs"
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
  - "MSBuild.GenerateManifest.NoEntryPoint"
helpviewer_keywords: 
  - "MSB3185"
ms.assetid: 032c63c5-d662-42ba-84e1-e3ccca8cee05
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB3185
**MSB3185: 매니페스트에 EntryPoint를 지정하지 않았습니다.**  
  
 이 오류는 매니페스트에서 진입점을 지정하지 않은 경우 발생합니다.  이 오류는 응용 프로그램 매니페스트와 배포 매니페스트에 모두 적용될 수 있습니다.  
  
### 이 오류를 해결하려면  
  
-   GenerateApplicationManifest 작업을 사용하는 경우 유효한 진입점을 제공하거나 TargetFrameworkVersion 속성을 "v3.5" 이상으로 설정해야 합니다.  응용 프로그램 매니페스트의 경우 유효한 진입점은 .exe 파일입니다.  
  
-   GenerateDeploymentManifest 작업을 사용하는 경우 매니페스트에서 유효한 진입점을 제공해야 합니다.  배포 매니페스트의 경우 유효한 진입점은 응용 프로그램 매니페스트입니다.  
  
## 참고 항목  
 <xref:Microsoft.Build.Tasks.Deployment.ManifestUtilities.ApplicationManifest.HostInBrowser%2A>   
 <xref:Microsoft.Build.Tasks.GenerateApplicationManifest.TargetFrameworkVersion%2A>   
 [프로젝트 디자이너, 게시 페이지](../ide/reference/publish-page-project-designer.md)   
 [\<PackageFiles\> 요소](../deployment/packagefiles-element-bootstrapper.md)   
 [MSBuild 오류 MSB3116](../misc/msbuild-error-msb3116.md)   
 [MSBuild 오류 MSB3117](../misc/msbuild-error-msb3117.md)   
 [MSBuild 오류 MSB3118](../misc/msbuild-error-msb3118.md)   
 [MSBuild 오류 MSB3174](../misc/msbuild-error-msb3174.md)