---
title: "배포를 관리 하기 위한 프로젝트 구성 | Microsoft Docs"
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
  - "배포를 관리 하는 프로젝트 구성"
  - "프로젝트 [Visual Studio SDK], 배포를 관리 하기 위한 구성"
ms.assetid: bd5940d9-d94d-4944-beda-4ec1ab2bbde5
caps.latest.revision: 8
caps.handback.revision: 8
ms.author: "gregvanl"
manager: "ghogen"
---
# 배포를 관리 하기 위한 프로젝트 구성
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

배포 디버깅 및 설치에 대 한 예상된 위치를 출력 항목을 빌드 프로세스에서 물리적으로 이동 하는 작업입니다.  예를 들어, 웹 응용 프로그램을 로컬 시스템에 구축 및 표시 다음 서버에 배치할 수 있습니다.  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]프로젝트 배포에 관련 된 수 있는 두 가지 방법 지원 합니다.  
  
-   배포 프로세스의 제목으로 합니다.  
  
-   구축 프로세스 관리자는 합니다.  
  
 솔루션 배포 하기 전에 배포 옵션을 구성 하려면 배포 프로젝트를 먼저 추가 해야 합니다.  배포 프로젝트를 이미 존재 하지 않는 경우를 선택 하면 하나를 만들 것인지 묻습니다 있습니다  **솔루션 배포** 에서  **빌드** 메뉴 또는 마우스 오른쪽 단추로 솔루션입니다.  클릭 하면  **예** 열립니다는  **새 프로젝트 추가** 대화 상자를 사용 여  **원격 배포 마법사** 프로젝트 선택.  
  
 원격 배포 마법사에 포함할 프로젝트 출력 그룹, 포함 시킬 추가 파일, 원격 컴퓨터에 배포 하려는 응용 프로그램 \(Windows 또는 웹\)의 형식을 묻는 메시지가 나타납니다.  마법사의 마지막 페이지에서 선택한 옵션의 요약을 표시합니다.  
  
 배포 프로세스의 대상이 되는 프로젝트는 다른 환경으로 이동 해야 하는 출력 항목을 생성 합니다.  이러한 항목에 대 한 매개 변수로 설명 되어 출력에서 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectCfg2> 인터페이스를 갖는 주요 목적 프로젝트 출력 그룹을 허용 하는 경우.  구현에 관련 된 자세한 내용은 `IVsProjectCfg2`를 참조 하십시오 [출력에 대 한 프로젝트 구성](../../extensibility/internals/project-configuration-for-output.md).  
  
 배포 프로세스를 관리 하는 배포 프로젝트를 배포 명령을 사용 하 고이 명령을 선택 하면 응답 합니다.  배포 프로젝트를 구현는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsDeployableProjectCfg> 배포를 수행 하 고 호출 하는 인터페이스는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsDeployStatusCallback> 를 보고 인터페이스 상태 이벤트를 배포 합니다.  
  
 구성 빌드 또는 배포 작업에 영향을 주는 종속성을 지정할 수 있습니다.  배포 종속성 중 하나가 작성 하거나 전이나에서는 구성 빌드 또는 배포 후 배포 된 프로젝트입니다.  프로젝트 간 의존 관계를 빌드 설명 되어 있는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildDependency> 인터페이스 및 종속성을 배포는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsDeployDependency> 인터페이스입니다.  자세한 내용은 [빌드를 위한 프로젝트 구성](../../extensibility/internals/project-configuration-for-building.md)를 참조하십시오.  
  
## 참고 항목  
 [구성 옵션 관리](../../extensibility/internals/managing-configuration-options.md)   
 [빌드를 위한 프로젝트 구성](../../extensibility/internals/project-configuration-for-building.md)   
 [출력에 대 한 프로젝트 구성](../../extensibility/internals/project-configuration-for-output.md)