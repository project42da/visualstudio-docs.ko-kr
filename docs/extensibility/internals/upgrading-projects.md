---
title: "프로젝트 업그레이드 | Microsoft Docs"
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
  - "Vspackage를 업그레이드합니다."
  - "응용 프로그램, 전략 업그레이드"
  - "Vspackage, 업그레이드 지원"
ms.assetid: e01cb44a-8105-4cf4-8223-dfae65f8597a
caps.latest.revision: 12
caps.handback.revision: 12
ms.author: "gregvanl"
manager: "ghogen"
---
# 프로젝트 업그레이드
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

프로젝트 모델에의 한 버전에서 변경 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 옆에 있는 새 버전에서 실행할 수 있도록 프로젝트 및 솔루션 업그레이드 해야 할 수 있습니다.  [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] 업그레이드 지원에서는 프로젝트를 구현 하는 데 사용할 수 있는 인터페이스를 제공 합니다.  
  
## 업그레이드 전략  
 업그레이드를 지원 하기 위해 시스템 구현 프로젝트 정의 하 고 한 업그레이드 전략을 구현 해야 합니다.  전략을 결정 하는 나란히\-\(SxS\) 백업, 복사본 백업, 또는 둘 다를 지원할 수 있습니다.  
  
-   SxS 백업 프로젝트 장소에 적절 한 파일 이름 접미사, 예를 들어, 추가 ".old" 업그레이드 해야 하는 파일만 복사 하는 것입니다.  
  
-   프로젝트 프로젝트의 모든 항목을 사용자가 제공한 백업 위치에 복사 하도록 백업 복사본을 의미 합니다.  해당 파일에서 원래 프로젝트 위치에 다음 업그레이드 됩니다.  
  
## 작업을 업그레이드 하는 방법  
 솔루션의 이전 버전에서 만든 경우 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 솔루션 파일을 업그레이드 해야 하는 경우 확인 하려면 IDE 검사 최신 버전에서 열립니다.  업그레이드 요구 되는 경우는  **업그레이드 마법사** 업그레이드 프로세스를 통해 사용자를 안내 수 자동으로 실행 됩니다.  
  
 솔루션 업그레이드 해야 하는 경우 각 프로젝트 공장 업그레이드 전략에 대해 쿼리 합니다.  전략 프로젝트 공장 SxS 백업 또는 복사본 백업을 지원 하는지 여부를 결정 합니다.  정보를 보낼 수는  **업그레이드 마법사**, 백업에 대 한 필요한 정보를 수집 하 고 적용할 수 있는 옵션을 제공 합니다.  
  
### 다중 프로젝트 솔루션  
 솔루션에 여러 프로젝트가 포함 되어 때 SxS 백업을 지 원하는 c \+ \+ 프로젝트 및 웹 프로젝트만 복사 백업 지원, 프로젝트 공장 업그레이드 전략 협상 해야 같은 업그레이드 전략 다른 경우.  
  
 솔루션의 각 프로젝트 공장에 대 한 쿼리 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgradeViaFactory>.  그런 다음 호출 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgradeViaFactory.UpgradeProject_CheckOnly%2A> 글로벌 프로젝트 파일 업그레이드 해야 하는지 확인 하 고 지원 되는 업그레이드 전략을 결정할 수 있습니다.  해당  **업그레이드 마법사** 다음 호출 됩니다.  
  
 사용자가 마법사를 완료 한 후 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgradeViaFactory.UpgradeProject%2A> 실제 업그레이드를 수행 하려면 각 프로젝트 공장에 호출 됩니다.  백업을 사용 하려면 IVsProjectUpgradeViaFactory 메서드를 제공 합니다.는 <xref:Microsoft.VisualStudio.Shell.Interop.SVsUpgradeLogger> 서비스 업그레이드 작업의 세부 정보를 기록 합니다.  이 서비스를 캐시할 수 없습니다.  
  
 관련 된 모든 전역 파일을 업데이트 한 후 각 프로젝트 공장 프로젝트를 인스턴스화할 수 있습니다.  프로젝트 구현을 지원 해야 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgrade>.  <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgrade.UpgradeProject%2A> 관련 프로젝트 항목을 모두 업그레이드 하려면 메서드가 호출 되 고 있습니다.  
  
> [!NOTE]
>  <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgradeViaFactory.UpgradeProject%2A> SVsUpgradeLogger 서비스 메서드를 제공 하지 않습니다.  이 서비스를 호출 하 여 얻을 수 있습니다 <xref:Microsoft.VisualStudio.OLE.Interop.IServiceProvider.QueryService%2A>.  
  
## 최선의 구현 방법  
 사용은 <xref:Microsoft.VisualStudio.Shell.Interop.SVsQueryEditQuerySave> 파일을 편집 하기 전에 편집할 수 및이 저장 하기 전에 저장할 수 있는 경우 확인 하는 서비스입니다.  이 백업에 도움이 됩니다 및 업그레이드 구현 소스 제어 아래에 있는 프로젝트 파일, 파일 사용 권한 부족, 등을 처리 합니다.  
  
 사용은 <xref:Microsoft.VisualStudio.Shell.Interop.SVsUpgradeLogger> 백업의 모든 단계 동안 서비스 및 업그레이드를 성공 또는 실패를 업그레이드 프로세스에 정보를 제공 합니다.  
  
 백업 하 고 프로젝트를 업그레이드 하는 방법에 대 한 자세한 내용은 vsshell2.idl에서 Ivsprojectupgrade에 대 한 의견을 참조 하십시오.  
  
## 참고 항목  
 [프로젝트](../../extensibility/internals/projects.md)   
 [사용자 지정 프로젝트 업그레이드](../../misc/upgrading-custom-projects.md)   
 [프로젝트 항목 업그레이드](../../misc/upgrading-project-items.md)