---
title: "방법: GetGlobalService 사용 | Microsoft Docs"
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
  - "서비스, GetGlobalService"
ms.assetid: 4cdf5ab5-9f09-4caf-9011-2dcb2c62f1b7
caps.latest.revision: 14
caps.handback.revision: 14
manager: "douge"
---
# 방법: GetGlobalService 사용
도구 창에서 서비스를 준비 하거나 원하는 서비스에 대 한 알 수 없는 서비스 공급자와 배치 된 그렇지 아직 배치 된 컨테이너를 제어 하는 경우가 있습니다.  예를 들어 컨트롤 내에서 작업 로그를 작성 하는 좋습니다.  이러한 문제 및 기타 시나리오에 대 한 자세한 내용은 참조 하십시오. [방법: 서비스 문제 해결](../extensibility/how-to-troubleshoot-services.md).  
  
 대부분의 얻을 수 있습니다 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 서비스를 호출 하는 정적 <xref:Microsoft.VisualStudio.Shell.Package.GetGlobalService%2A> 방법입니다.  
  
 <xref:Microsoft.VisualStudio.Shell.Package.GetGlobalService%2A>파생 된 Vspackage를 처음으로 초기화 되는 캐시 된 서비스 공급자를 사용 하 여 <xref:Microsoft.VisualStudio.Shell.Package> 배치 됩니다.  이 조건을 충족 되 그렇지는 null 서비스에 대 한 준비를 보장 해야 합니다.  
  
 다행히도, <xref:Microsoft.VisualStudio.Shell.Package.GetGlobalService%2A> 대부분의 작동 합니다.  
  
-   있는 VSPackage 다른 Vspackage만 하 라고 하는 서비스를 제공 하는 경우 서비스를 요청 하 여 VSPackage 서비스 로드를 제공 하 여 VSPackage 전에 사이 팅 되어.  
  
-   가 있는 VSPackage 도구 창을 만들면 도구 창을 만들기 전에 있는 VSPackage 사이 팅 되어 있습니다.  
  
-   컨트롤 컨테이너 만들어지기 전에 컨트롤 컨테이너는 Vspackage로 만든 도구 창에서 호스팅되는 경우에 VSPackage 사이 팅 되어.  
  
### 서비스에서 도구 창 또는 컨트롤 컨테이너에서 얻을 수  
  
-   이 코드에는 생성자, 도구 창, 또는 컨트롤 컨테이너에 삽입 합니다.  
  
     [!code-vb[UseGetGlobalService#1](../misc/codesnippet/VisualBasic/how-to-use-getglobalservice_1.vb)]
     [!code-cs[UseGetGlobalService#1](../misc/codesnippet/CSharp/how-to-use-getglobalservice_1.cs)]  
  
     이 코드 SVsActivityLog 서비스를 얻고 캐스팅에 <xref:Microsoft.VisualStudio.Shell.Interop.IVsActivityLog> 활동 로그에 기록 하는 데 사용 하는 인터페이스입니다.  예제를 보려면 [방법: 작업 로그를 사용 하 여](../extensibility/how-to-use-the-activity-log.md)을 참조하십시오.  
  
## 참고 항목  
 [방법: 서비스 문제 해결](../extensibility/how-to-troubleshoot-services.md)   
 [사용 하 고 서비스를 제공 합니다.](../extensibility/using-and-providing-services.md)   
 [서비스 Essentials](../extensibility/internals/service-essentials.md)