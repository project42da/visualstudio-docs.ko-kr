---
title: "방법: DTE 개체에서 서비스 가져오기 | Microsoft Docs"
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
  - "서비스, DTE 개체에서"
ms.assetid: c26a51d4-86f0-454b-9625-5443e55eec7d
caps.latest.revision: 13
caps.handback.revision: 13
manager: "douge"
---
# 방법: DTE 개체에서 서비스 가져오기
서비스에 액세스할 수 있는 모든 프로그램에서 얻을 수 있는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 자동화 <xref:EnvDTE.DTEClass> 개체입니다.  예를 들어, 액세스할 수는 <xref:Microsoft.VisualStudio.Shell.Interop.SVsActivityLog> DTE 개체를 통해 마법사에서 서비스 합니다.  이 서비스 활동 로그에 쓸 수 있습니다.  자세한 내용은 [방법: 작업 로그를 사용 하 여](../extensibility/how-to-use-the-activity-log.md)를 참조하십시오.  
  
 DTE 개체가 구현 하는 <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider>를 사용할 수 있는 서비스에 대 한 쿼리를 사용 하 여 관리 되는 코드에서를 <xref:Microsoft.VisualStudio.Shell.ServiceProvider.GetService%2A>.  
  
### 서비스에서 DTE 개체를 가져오려면  
  
1.  만드는 다음 코드를 <xref:Microsoft.VisualStudio.Shell.ServiceProvider> DTE 개체 및 호출에서 <xref:Microsoft.VisualStudio.Shell.ServiceProvider.GetService%2A> 의 형식으로 <xref:Microsoft.VisualStudio.Shell.Interop.SVsActivityLog> 서비스.  서비스 인터페이스로 캐스팅 된 <xref:Microsoft.VisualStudio.Shell.Interop.IVsActivityLog>, 활동 로그에 항목을 기록 하려면 사용 됩니다.  자세한 정보 사항에 대 한 내용은 활동 로그에 기록 하는 [방법: 작업 로그를 사용 하 여](../extensibility/how-to-use-the-activity-log.md).  
  
     [!code-cs[GetAServiceFromTheDTEObject#1](../misc/codesnippet/CSharp/how-to-get-a-service-from-the-dte-object_1.cs)]
     [!code-vb[GetAServiceFromTheDTEObject#1](../misc/codesnippet/VisualBasic/how-to-get-a-service-from-the-dte-object_1.vb)]  
  
## 참고 항목  
 [사용 하 고 서비스를 제공 합니다.](../extensibility/using-and-providing-services.md)   
 [서비스 Essentials](../extensibility/internals/service-essentials.md)