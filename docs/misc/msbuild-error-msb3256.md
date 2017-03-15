---
title: "MSBuild 오류 MSB3256 | Microsoft Docs"
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
  - "MSB3256"
ms.assetid: 809ccd0a-78cd-4bf5-83a8-2fb51815ea27
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB3256
**MSB3256: 재배포 목록에서 읽어온 어셈블리가 없습니다.  TargetFramework 하위 집합 제외 목록을 생성할 수 없습니다.**  
  
 재배포 가능 항목의 목록\(재배포 목록\)을 찾을 수 없습니다.  
  
 .NET Framework 하위 집합에서 제외할 어셈블리 목록을 생성하기 위해서는 두개의 파일이 필요 합니다. 하나는 .NET Framework의 재배포 가능 항목 이름을 포함하는 FrameworkList.xml라는 "재배포 목록" 이고, 다른 하나는 .NET Framework의 항목 이름을 포함하는 client.xml 라는 "하위 목록" 입니다.  하위 집합 정의는 두 목록 모두를 필요로 하기 때문에, 만약 재배포 목록이 없는 경우, .NET Framework 하위 집합은 지정될 수 없습니다.  
  
 [!INCLUDE[net_client_v35_long](../misc/includes/net_client_v35_long_md.md)]은 전체 [!INCLUDE[net_v35_short](../misc/includes/net_v35_short_md.md)] 런타임 라이브러리의 부분 집합입니다.  [!INCLUDE[net_client_v35_long](../misc/includes/net_client_v35_long_md.md)]에 대한 자세한 내용은 [.NET Framework Client Profile](../Topic/.NET%20Framework%20Client%20Profile.md)를 참조하십시오.  
  
### 이 오류를 해결하려면  
  
-   FrameworkList.xml이라는 유효한 재배포 목록을 제공하거나 전체 [!INCLUDE[net_v35_short](../misc/includes/net_v35_short_md.md)] 재배포 가능 라이브러리를 대상으로 지정합니다.  전체 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]를 대상으로 지정하는 방법에 대한 자세한 내용은 [방법: 한 버전의 .NET Framework를 대상으로 지정](../ide/how-to-target-a-version-of-the-dotnet-framework.md)을 참조하십시오.  
  
## 참고 항목  
 [대상 프레임워크 및 대상 플랫폼](../msbuild/msbuild-target-framework-and-target-platform.md)   
 [Project Element \(MSBuild\)](../msbuild/project-element-msbuild.md)   
 [추가 리소스](../msbuild/additional-msbuild-resources.md)