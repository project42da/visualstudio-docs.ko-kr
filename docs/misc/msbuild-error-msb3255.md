---
title: "MSBuild 오류 MSB3255 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "MSB3255"
ms.assetid: baac844e-a662-4421-bed1-2bc98f2e1cdf
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB3255
**MSB3255: 대상 프레임워크 디렉터리 또는 InstalledAssemblySubsetTables에 지정된 위치에서 대상 프레임워크 하위 집합 파일을 찾을 수 없습니다.**  
  
 이 오류는 <xref:Microsoft.Build.Tasks.ResolveAssemblyReference.FullTargetFrameworkSubsetNames%2A> 속성에 이름이 전달되었지만 해당 이름을 갖는 부분 집합을 찾을 수 없을 때 발생합니다.  
  
 [!INCLUDE[net_client_v35_long](../misc/includes/net_client_v35_long_md.md)]은 전체 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 3.5 런타임 라이브러리의 부분 집합입니다.  [!INCLUDE[net_client_v35_long](../misc/includes/net_client_v35_long_md.md)]에 대한 자세한 내용은 [.NET Framework Client Profile](../Topic/.NET%20Framework%20Client%20Profile.md)를 참조하십시오.  
  
 절차  
  
### 이 오류를 해결하려면  
  
-   부분 집합 파일의 복사본을 대상 프레임워크 폴더 또는 <xref:Microsoft.Build.Tasks.ResolveAssemblyReference.InstalledAssemblySubsetTables%2A>에 지정된 위치 중 하나에 배치합니다.  
  
## 참고 항목  
 [Project Element \(MSBuild\)](../msbuild/project-element-msbuild.md)   
 [추가 리소스](../msbuild/additional-msbuild-resources.md)