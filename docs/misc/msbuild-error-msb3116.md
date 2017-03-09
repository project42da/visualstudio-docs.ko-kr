---
title: "MSBuild 오류 MSB3116 | Microsoft Docs"
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
  - "MSBuild.GenerateManifest.HostInBrowserNotOnlineOnly"
helpviewer_keywords: 
  - "MSB3116"
ms.assetid: bf04c587-d0e2-4d68-bbff-da9a985ea70e
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB3116
**MSB3116: 응용 프로그램이 브라우저에서 호스팅하도록 표시되었으나 동시에 온라인 및 오프라인으로 사용할 수 있도록 표시되었습니다.  응용 프로그램을 온라인으로만 사용할 수 있도록 변경하십시오.**  
  
 WPF 웹 브라우저 응용 프로그램을 배포하는 경우 <xref:Microsoft.Build.Tasks.Deployment.ManifestUtilities.ApplicationManifest.HostInBrowser%2A> 속성을 `True`로 설정해야 합니다.  <xref:Microsoft.Build.Tasks.Deployment.ManifestUtilities.ApplicationManifest.HostInBrowser%2A>가 `True`로 설정된 경우 설치를 온라인으로만 사용할 수 있도록 <xref:Microsoft.Build.Tasks.Deployment.ManifestUtilities.DeployManifest.Install%2A> 속성을 `False`로 설정해야 합니다.  두 번째 조건이 만족되지 않는 경우 이 오류 메시지가 표시됩니다.  
  
### 이 오류를 해결하려면  
  
-   <xref:Microsoft.Build.Tasks.Deployment.ManifestUtilities.DeployManifest.Install%2A> 속성을 `False`으로 설정합니다.  
  
## 참고 항목  
 <xref:Microsoft.Build.Tasks.Deployment.ManifestUtilities.ApplicationManifest.HostInBrowser%2A>   
 <xref:Microsoft.Build.Tasks.Deployment.ManifestUtilities.DeployManifest.Install%2A>   
 [프로젝트 디자이너, 게시 페이지](../ide/reference/publish-page-project-designer.md)