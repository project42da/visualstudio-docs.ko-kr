---
title: "프로젝트 항목 업그레이드 | Microsoft Docs"
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
  - "프로젝트 항목 업그레이드"
  - "프로젝트[Visual Studio SDK], 항목 업그레이드"
  - "프로젝트 항목[Visual Studio], 업그레이드"
ms.assetid: 8af29dd4-eaf1-4b3c-b602-198e1a3dff23
caps.latest.revision: 14
caps.handback.revision: 14
manager: "douge"
---
# 프로젝트 항목 업그레이드
추가 또는 관리 항목은 내부 프로젝트 시스템을 구현 하지 않는 경우 프로젝트 업그레이드 프로세스에 참여 해야 합니다.  Crystal Reports를 프로젝트 시스템에 추가할 수 있는 항목의 예입니다.  
  
 일반적으로 프로젝트 항목 구현자는 이미 완전히 인스턴스화된와 업그레이드 된 프로젝트 참조는 프로젝트 및 어떤 다른 프로젝트 속성은 업그레이드 여부를 결정 하는 게 필요한 때문에 활용 합니다.  
  
### 프로젝트 업그레이드 알림을 받으려면  
  
1.  설정에서 <xref:Microsoft.VisualStudio.Shell.Interop.UIContextGuids80.SolutionOrProjectUpgrading> 프로젝트 항목 구현에서 플래그 \(vsshell80.idl에서 정의 됨\)입니다.  그러면 프로젝트가 자동으로 VSPackage 로드 시기는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 셸 결정 프로젝트 시스템의 업그레이드입니다.  
  
2.  조언의 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEventsProjectUpgrade> 통해 인터페이스는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolution2.AdviseSolutionEvents%2A> 메서드.  
  
3.  <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEventsProjectUpgrade> 인터페이스 시스템 구현 프로젝트 업그레이드 작업을 완료 하 고 업그레이드 된 새 프로젝트가 생성 된 후 발생 합니다.  시나리오에 따라는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEventsProjectUpgrade> 인터페이스 후 발생 되는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3.OnAfterOpenSolution%2A>, the <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3.OnAfterOpenProject%2A>, 나는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionEvents3.OnAfterLoadProject%2A> 메서드.  
  
### 프로젝트 항목 파일을 업그레이드 하기  
  
1.  프로젝트 항목 구현에 주의 깊게 파일 백업 프로세스를 관리 해야 합니다.  이 나란히 백업에 대 한, 특히 적용 됩니다 위치는 `fUpgradeFlag` 의 매개 변수는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectUpgradeViaFactory.UpgradeProject%2A> 메서드가 설정 되어 <xref:Microsoft.VisualStudio.Shell.Interop.__VSPPROJECTUPGRADEVIAFACTORYFLAGS>, ".old"로 지정 되 면 파일을 따라 백업 파일이 배치 되는 위치.  이라고 프로젝트를 업그레이드 하 여 시스템 시간 보다 오래 된 백업된 파일을 지정할 수 있습니다.  이 방지 하려면 특정 단계를 수행 하지 않으면 또한, 이들은 덮어쓸 수 있습니다.  
  
2.  당시에 프로젝트 항목을 프로젝트 업그레이드에 대 한 알림을 가져옵니다의  **Visual Studio 변환 마법사** 여전히 표시 됩니다.  따라서 메서드를 사용 해야 합니다을 <xref:Microsoft.VisualStudio.Shell.Interop.IVsUpgradeLogger> 업그레이드 메시지는 마법사에 UI를 제공 하는 인터페이스입니다.  
  
## 참고 항목  
 [Visual Studio Conversion Wizard](http://msdn.microsoft.com/ko-kr/4acfd30e-c192-4184-a86f-2da5e4c3d83c)   
 [사용자 지정 프로젝트 업그레이드](../misc/upgrading-custom-projects.md)