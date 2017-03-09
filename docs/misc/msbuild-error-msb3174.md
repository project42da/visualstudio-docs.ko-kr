---
title: "MSBuild 오류 MSB3174 | Microsoft Docs"
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
  - "MSBuild.GenerateManifest.InvalidValue"
helpviewer_keywords: 
  - "MSB3174"
ms.assetid: 6f9a040c-7f21-40fd-bf74-03f99f265e79
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB3174
**MSB3174: '\<file\>'의 값이 잘못되었습니다.**  
  
 이 오류는 빌드 프로세스에서 매니페스트 파일의 형식을 검사하는 동안 일반적인 문제를 발견한 경우 발생합니다.  오류 메시지에는 매니페스트 파일 이름이 표시됩니다.  
  
 다음 매개 변수 중 하나라도 잘못 설정하면 이 오류 메시지가 발생합니다.  나열된 각 매개 변수는 <xref:Microsoft.Build.Tasks.GenerateApplicationManifest.TargetFrameworkVersion%2A> 또는 <xref:Microsoft.Build.Tasks.GenerateDeploymentManifest.MinimumRequiredVersion%2A>과 같은 <xref:Microsoft.Build.Tasks.GenerateApplicationManifest> 또는 <xref:Microsoft.Build.Tasks.GenerateDeploymentManifest> 속성입니다.  
  
 작업이 <xref:Microsoft.Build.Tasks.GenerateApplicationManifest>인 경우 다음 요구 사항이 적용됩니다.  
  
|Parameter|요구 사항|  
|---------------|-----------|  
|<xref:Microsoft.Build.Tasks.GenerateManifestBase.AssemblyName%2A>|올바른 파일 이름이어야 합니다.|  
|<xref:Microsoft.Build.Tasks.GenerateManifestBase.AssemblyVersion%2A>|요구 사항은 <xref:System.Version.%23ctor%2A>에 대한 요구 사항과 같습니다.  모든 8진수는 0보다 커야 합니다.  4개의 8진수를 모두 지정해야 합니다.  빈 문자열을 사용할 수 있습니다.|  
|<xref:Microsoft.Build.Tasks.GenerateApplicationManifest.ClrVersion%2A>|요구 사항은 <xref:System.Version.%23ctor%2A>에 대한 요구 사항과 같습니다.  모든 8진수는 0보다 커야 합니다.  4개의 8진수를 모두 지정해야 합니다.  빈 문자열을 사용할 수 있습니다.|  
|<xref:Microsoft.Build.Tasks.GenerateApplicationManifest.OSVersion%2A>|요구 사항은 <xref:System.Version.%23ctor%2A>에 대한 요구 사항과 같습니다.  모든 8진수는 0보다 커야 합니다.  4개의 8진수를 모두 지정해야 합니다.  빈 문자열을 사용할 수 있습니다.|  
|<xref:Microsoft.Build.Tasks.GenerateManifestBase.Platform%2A>|**AnyCPU**, **x86**, **x64** 또는 **Itanium**이어야 합니다.  빈 문자열을 사용할 수 있습니다.|  
|<xref:Microsoft.Build.Tasks.GenerateApplicationManifest.ManifestType%2A>|**Native** 또는 **ClickOnce**여야 합니다.|  
|<xref:Microsoft.Build.Tasks.GenerateManifestBase.TargetCulture%2A>|빈 문자열이 될 수 있습니다.  두 자리 소문자 언어 코드로 지정되는 중립 문화권이 될 수도 있습니다\(일본어의 경우 "jp"\).  그렇지 않으면 이 값에 대한 요구 사항은 <xref:System.Globalization.CultureInfo.%23ctor%2A>에 대한 요구 사항과 같습니다.|  
|<xref:Microsoft.Build.Tasks.GenerateApplicationManifest.TargetFrameworkVersion%2A>|v*\#*.*\#* 형식이어야 합니다.  v2.0 이상이어야 합니다.  빈 문자열을 사용할 수 있습니다.|  
  
 작업이 <xref:Microsoft.Build.Tasks.GenerateDeploymentManifest>인 경우 다음 요구 사항이 적용됩니다.  
  
|Parameter|요구 사항|  
|---------------|-----------|  
|<xref:Microsoft.Build.Tasks.GenerateManifestBase.AssemblyName%2A>|올바른 파일 이름이어야 합니다.|  
|<xref:Microsoft.Build.Tasks.GenerateManifestBase.AssemblyVersion%2A>|요구 사항은 <xref:System.Version.%23ctor%2A>에 대한 요구 사항과 같습니다.  모든 8진수는 0보다 커야 합니다.  4개의 8진수를 모두 지정해야 합니다.  빈 문자열을 사용할 수 있습니다.|  
|<xref:Microsoft.Build.Tasks.GenerateDeploymentManifest.MinimumRequiredVersion%2A>|요구 사항은 <xref:System.Version.%23ctor%2A>에 대한 요구 사항과 같습니다.  모든 8진수는 0보다 커야 합니다.  빈 문자열을 사용할 수 있습니다.|  
|<xref:Microsoft.Build.Tasks.GenerateManifestBase.Platform%2A>|**AnyCPU**, **x86**, **x64** 또는 **Itanium**이어야 합니다.  빈 문자열을 사용할 수 있습니다.|  
|<xref:Microsoft.Build.Tasks.GenerateManifestBase.TargetCulture%2A>|빈 문자열이 될 수 있습니다.  두 자리 소문자 언어 코드로 지정되는 중립 문화권이 될 수도 있습니다\(일본어의 경우 "jp"\).  그렇지 않으면 이 값에 대한 요구 사항은 <xref:System.Globalization.CultureInfo.%23ctor%2A>에 대한 요구 사항과 같습니다.|  
|<xref:Microsoft.Build.Tasks.GenerateDeploymentManifest.UpdateMode%2A>|**Foreground** 또는 **Background**여야 합니다.  빈 문자열을 사용할 수 있습니다.|  
|<xref:Microsoft.Build.Tasks.GenerateDeploymentManifest.UpdateUnit%2A>|**Hours**, **Days** 또는 **Weeks**여야 합니다.  빈 문자열을 사용할 수 있습니다.|  
  
## 참고 항목  
 <xref:Microsoft.Build.Tasks.Deployment.ManifestUtilities.ApplicationManifest.HostInBrowser%2A>   
 <xref:Microsoft.Build.Tasks.GenerateApplicationManifest.TargetFrameworkVersion%2A>   
 [제품 및 패키지 스키마 참조](../deployment/product-and-package-schema-reference.md)   
 [프로젝트 디자이너, 게시 페이지](../ide/reference/publish-page-project-designer.md)   
 [MSBuild 오류 MSB3116](../misc/msbuild-error-msb3116.md)   
 [MSBuild 오류 MSB3117](../misc/msbuild-error-msb3117.md)   
 [MSBuild 오류 MSB3118](../misc/msbuild-error-msb3118.md)   
 [MSBuild 오류 MSB3185](../misc/msbuild-error-msb3185.md)