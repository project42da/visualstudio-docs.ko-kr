---
title: "웹 응용 프로그램 원격 디버깅의 필수 구성 요소 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "ASP.NET 웹 응용 프로그램 디버깅, 원격 서버"
  - "원격 디버깅, 필수 구성 요소"
  - "원격 서버, 웹 응용 프로그램 디버깅"
ms.assetid: 1cd777b5-6d20-4ca6-a0df-51653b118469
caps.latest.revision: 27
caps.handback.revision: 27
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 웹 응용 프로그램 원격 디버깅의 필수 구성 요소
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 디버거를 사용하면 로컬 컴퓨터나 원격 서버에서 웹 응용 프로그램을 투명하게 디버깅할 수 있습니다.  즉, 로컬 컴퓨터나 원격 서버에서 디버거가 같은 방식으로 작동하며 동일한 디버거 기능을 사용할 수 있습니다.  그러나 원격 디버깅이 올바르게 작동하기 위해서는 몇 가지 필수 조건이 있습니다.  
  
-   디버깅할 서버에 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 원격 디버깅 구성 요소가 설치되어 있어야 합니다.  자세한 내용은 [원격 디버깅 설정](../Topic/Set%20Up%20the%20Remote%20Tools%20on%20the%20Device.md)을 참조하십시오.  
  
-   기본적으로 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 작업자 프로세스는 ASPNET 사용자 프로세스로 실행됩니다.  따라서 이 프로세스를 디버깅하려면 [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)]이 실행되는 컴퓨터에 대한 관리자 권한이 있어야 합니다.  [!INCLUDE[vstecasp](../code-quality/includes/vstecasp_md.md)] 작업자 프로세스의 이름은 디버그 시나리오 및 IIS 버전에 따라 다릅니다.  자세한 내용은 [방법: ASP.NET 프로세스의 이름 찾기](../debugger/how-to-find-the-name-of-the-aspnet-process.md)을 참조하십시오.  
  
## 참고 항목  
 [ASP.NET 및 AJAX 응용 프로그램 디버깅](../debugger/debugging-aspnet-and-ajax-applications.md)   
 [시스템 요구 사항](../debugger/aspnet-debugging-system-requirements.md)