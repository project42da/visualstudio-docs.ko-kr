---
title: "MSBuild 오류 MSB3254 | Microsoft Docs"
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
  - "MSB3254"
ms.assetid: cb9636b2-d9b3-466d-959c-14c7c8017a78
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB3254
**MSB3254: \<name\> 파일은 읽어올 수 없으므로 무시됩니다.  이 파일을 InstalledAssemblySubsetTables에 전달했거나 TargetFrameworkDirectories에서 \<name\> 폴더를 검색하여 찾았습니다.**  
  
 이 오류는 [!INCLUDE[net_client_v35_long](../misc/includes/net_client_v35_long_md.md)] XML 파일인 client.xml을 읽을 수 없을 때 발생합니다.  손상, 잠금 또는 기타 문제로 인해 파일을 읽을 수 없습니다.  
  
 [!INCLUDE[net_client_v35_long](../misc/includes/net_client_v35_long_md.md)]은 전체 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 3.5 런타임 라이브러리의 부분 집합입니다.  [!INCLUDE[net_client_v35_long](../misc/includes/net_client_v35_long_md.md)]에 대한 자세한 내용은 [.NET Framework Client Profile](../Topic/.NET%20Framework%20Client%20Profile.md)를 참조하십시오.  
  
 절차  
  
### 이 오류를 해결하려면  
  
-   파일에 대한 전체 사용 권한과 전체 액세스 권한이 있는지 확인하거나 [!INCLUDE[net_client_v35_long](../misc/includes/net_client_v35_long_md.md)] 재배포 가능 런타임 라이브러리를 다시 설치하여 손상된 파일을 대체합니다.  
  
## 참고 항목  
 [Project Element \(MSBuild\)](../msbuild/project-element-msbuild.md)   
 [추가 리소스](../msbuild/additional-msbuild-resources.md)