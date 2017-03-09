---
title: "MSBuild 오류 MSB3252 | Microsoft Docs"
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
  - "MSB3252"
helpviewer_keywords: 
  - "MSB3252"
ms.assetid: 4e6982b8-84b3-4d21-94e1-05cc10bf1393
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB3252
**MSB3252: 프로젝트에 \<name\> 어셈블리에 대한 참조가 있습니다.  이 어셈블리가 .NET Framework Client Profile의 일부가 아닙니다.  이 참조가 없으면 컴파일 또는 런타임 오류가 발생할 수 있습니다.**  
  
 [!INCLUDE[net_client_v35_long](../misc/includes/net_client_v35_long_md.md)]의 일부가 아닌 어셈블리 또는 종속 어셈블리의 멤버를 호출했습니다.  따라서 호출을 확인할 수 없고 응용 프로그램을 컴파일할 수 없습니다.  
  
 [!INCLUDE[net_client_v35_long](../misc/includes/net_client_v35_long_md.md)]에 대한 자세한 내용은 [.NET Framework Client Profile](../Topic/.NET%20Framework%20Client%20Profile.md)를 참조하십시오.  
  
### 이 오류를 해결하려면  
  
-   지정된 어셈블리 참조를 프로젝트에서 제거하거나 [!INCLUDE[net_client_v35_long](../misc/includes/net_client_v35_long_md.md)] 부분 집합 라이브러리 대신 전체 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]를 대상으로 지정합니다.  전체 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]를 대상으로 지정하는 방법에 대한 자세한 내용은 [방법: 한 버전의 .NET Framework를 대상으로 지정](../ide/how-to-target-a-version-of-the-dotnet-framework.md)을 참조하십시오.  
  
## 참고 항목  
 [대상 프레임워크 및 대상 플랫폼](../msbuild/msbuild-target-framework-and-target-platform.md)   
 [Project Element \(MSBuild\)](../msbuild/project-element-msbuild.md)   
 [추가 리소스](../msbuild/additional-msbuild-resources.md)