---
title: "MSBuild 오류 MSB3253 | Microsoft Docs"
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
  - "MSB3253"
ms.assetid: d4b5eb5b-703b-4b80-aa5d-6c70ff9fe84d
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# MSBuild 오류 MSB3253
**MSB3254: 프로젝트에서 참조하는 어셈블리 \<name\>은\(는\) .NET Framework Client Profile에 들어 있지 않는 \<name2\>에 종속됩니다.**  
  
 프로젝트에 참조하는 어셈블리 또는 종속 어셈블리 중 하나가 [!INCLUDE[net_client_v35_long](../misc/includes/net_client_v35_long_md.md)]에 들어 있지 않은 다른 어셈블리에 종속되어 있습니다.  
  
 일반적으로 이 메시지는 자체적으로 외부 어셈블리를 참조하는 타사 컨트롤이나 DLL을 프로젝트에서 참조할 때 나타납니다.  예를 들어 프로젝트에서 사용하는 컨트롤이 전체 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]에 들어 있는 기능을 사용할 수 있습니다.  응용 프로그램의 대상을 [!INCLUDE[net_client_v35_long](../misc/includes/net_client_v35_long_md.md)]로 다시 지정하고 [!INCLUDE[net_v35_long](../misc/includes/net_v35_long_md.md)]가 없는 시스템에 설치하면 응용 프로그램이 [!INCLUDE[net_client_v35_long](../misc/includes/net_client_v35_long_md.md)] 부분 집합에 들어 있지 않은 기능에 액세스할 때 제대로 작동하지 않습니다.  
  
 이 "오류" 메시지는 실제로는 경고일 뿐이며 응용 프로그램은 계속 컴파일됩니다.  그러나 이후에 컨트롤이나 DLL에서 누락된 어셈블리에 있는 기능을 참조하면 문제가 발생할 수 있습니다.  
  
 [!INCLUDE[net_client_v35_long](../misc/includes/net_client_v35_long_md.md)]은 전체 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 3.5 런타임 라이브러리의 부분 집합입니다.  [!INCLUDE[net_client_v35_long](../misc/includes/net_client_v35_long_md.md)]에 대한 자세한 내용은 [.NET Framework Client Profile](../Topic/.NET%20Framework%20Client%20Profile.md)를 참조하십시오.  
  
### 이 오류를 해결하려면  
  
-   지정된 어셈블리 참조를 프로젝트에서 제거하거나 [!INCLUDE[net_client_v35_long](../misc/includes/net_client_v35_long_md.md)] 부분 집합 라이브러리 대신 전체 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]를 대상으로 지정합니다.  전체 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]를 대상으로 지정하는 방법에 대한 자세한 내용은 [방법: 한 버전의 .NET Framework를 대상으로 지정](../ide/how-to-target-a-version-of-the-dotnet-framework.md)을 참조하십시오.  
  
## 참고 항목  
 [대상 프레임워크 및 대상 플랫폼](../msbuild/msbuild-target-framework-and-target-platform.md)   
 [Project Element \(MSBuild\)](../msbuild/project-element-msbuild.md)   
 [추가 리소스](../msbuild/additional-msbuild-resources.md)