---
title: "사용 하 고 서비스를 제공 합니다. | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "예제 [Visual Studio SDK] 서비스"
  - "Visual Studio에서 서비스"
  - "서비스"
ms.assetid: c0b415ba-b825-4da0-9faf-8a60a663e302
caps.latest.revision: 41
caps.handback.revision: 41
ms.author: "gregvanl"
manager: "ghogen"
---
# 사용 하 고 서비스를 제공 합니다.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

서비스는 두 개의 Vspackage 간의 계약입니다. 하나의 VSPackage를 사용 하는 다른 VSPackage에 대 한 인터페이스의 특정 집합을 제공 합니다. 예를 들어 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 제공는 <xref:Microsoft.VisualStudio.Shell.Interop.SVsActivityLog> 그것을 제공 하는 VSPackage를 로드 합니다. 이 서비스는 제공 된 <xref:Microsoft.VisualStudio.Shell.Interop.IVsActivityLog> 활동 로그에 쓰는 데 사용할 수 있는 인터페이스를 합니다. 자세한 내용은 [방법: 작업 로그를 사용 하 여](../extensibility/how-to-use-the-activity-log.md)을 참조하세요.  
  
 Vspackage 직접 사용 하 여 서비스를 제공할 수는 <xref:Microsoft.VisualStudio.Shell.Interop.IProfferService> 인터페이스...  
  
 Visual Studio에서는 다음과 같은 중요 한 서비스를 제공합니다.  
  
|IDE 서비스|설명|  
|-------------|--------|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsShell>|IDE에 대 한 액세스는 기본 기능, Vspackage를 레지스트리에와 처리 서비스를 제공 합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsUIShell>|기본적인 창 및 도구 및 문서 창을 작성 하는 기능과 같은 IDE에 UI 관련 기능을 제공 합니다.|  
|<xref:Microsoft.VisualStudio.Shell.Interop.SVsSolution>|프로젝트를 열거 하 고 새 프로젝트를 만들고 프로젝트 변경 내용을 모니터링 하는 기능과 같은 기본 솔루션 관련 기능을 제공 합니다.|  
  
## 단원 내용  
 [서비스 Essentials](../extensibility/internals/service-essentials.md)  
 Visual Studio 서비스의 중요 한 요소를 표시합니다.  
  
 [방법: 서비스 가져오기](../extensibility/how-to-get-a-service.md)  
 요청 하는 방법에 설명 \(소비\) 서비스.  
  
 [방법: 서비스를 제공 합니다.](../extensibility/how-to-provide-a-service.md)  
 서비스를 제공 하는 방법을 설명 합니다.  
  
 [방법: Visual Studio 비동기 서비스를 제공 합니다.](../extensibility/how-to-provide-an-asynchronous-visual-studio-service.md)  
 비동기 서비스를 제공 하는 방법에 설명 합니다.  
  
 [방법: 서비스 문제 해결](../extensibility/how-to-troubleshoot-services.md)  
 일반적인 문제에 설명 하 고 해당 하는 솔루션을 제공 합니다.  
  
## 관련 단원  
 [Visual Studio SDK](../extensibility/visual-studio-sdk.md)