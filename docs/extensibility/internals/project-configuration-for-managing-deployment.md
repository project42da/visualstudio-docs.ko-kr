---
title: "프로젝트 배포를 관리 하기 위한 구성 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- project configurations, managing deployment
- projects [Visual Studio SDK], configuration for managing deployment
ms.assetid: bd5940d9-d94d-4944-beda-4ec1ab2bbde5
caps.latest.revision: "8"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 87098c362e5b37690e2ab3116ffca431d58f129d
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="project-configuration-for-managing-deployment"></a>배포를 관리 하기 위한 프로젝트 구성
배포는 실제로 디버깅 및 설치에 대 한 예상된 위치를 빌드 프로세스에서 출력 항목을 이동 하는 작업입니다. 예를 들어 웹 응용 프로그램 로컬 컴퓨터에서 구축 되며 다음 서버에 배치 될 수 있습니다.  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]에서는 두 가지 방법으로 프로젝트 배포에 포함 될 수 있습니다.  
  
-   로 배포 프로세스의 제목입니다.  
  
-   배포 프로세스의 관리자입니다.  
  
 솔루션을 배포할 수 있습니다, 전에 먼저 배포 옵션을 구성 하는 배포 프로젝트를 추가 해야 합니다. 배포 프로젝트가 아직 없는 경우 묻는 하나 선택한 경우 만들 하려면 **솔루션 배포** 에서 **빌드** 메뉴 또는 솔루션을 마우스 오른쪽 단추로 클릭 합니다. 클릭 하면 **예** 열립니다는 **새 프로젝트 추가** 포함 된 대화 상자는 **원격 배포 마법사** 프로젝트를 선택 합니다.  
  
 원격 배포 마법사 (Windows 또는 웹) 응용 프로그램 종류, 포함할 프로젝트 출력 그룹, 포함할 추가 파일 및를 배포 하려는 원격 컴퓨터에 대 한 나타납니다. 마법사의 마지막 페이지에서 선택한 옵션에 대 한 요약을 표시합니다.  
  
 배포 프로세스의 주체인 프로젝트는 다른 환경으로 이동 해야 하는 출력 항목을 생성 합니다. 이러한 출력 항목에 대 한 매개 변수로 설명는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectCfg2> 인터페이스를 해당 주 용도 위해 프로젝트에서 출력 그룹으로 바뀝니다. 구현에 관련 된 자세한 정보에 대 한 `IVsProjectCfg2`, 참조 [출력에 대 한 프로젝트 구성](../../extensibility/internals/project-configuration-for-output.md)합니다.  
  
 배포 프로세스를 관리, 배포 프로젝트, 배포 명령을 사용 하도록 설정 하 고이 명령을 선택 하면 응답 합니다. 배포 프로젝트 구현는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsDeployableProjectCfg> 인터페이스에 대 한 호출을 만들고 배포를 수행 하는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsDeployStatusCallback> 보고서에 대 한 인터페이스 상태 이벤트를 배포 합니다.  
  
 구성의 빌드 또는 배포 작업에 영향을 주는 종속성을 지정할 수 있습니다. 빌드 또는 배포 종속성은 빌드된 이거나 전이나 자체 구성 빌드 또는 배포 후 배포 하는 프로젝트입니다. 프로젝트 간의 빌드 종속성과 함께 설명 됩니다는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildDependency> 인터페이스와 종속성을 배포 하 고는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsDeployDependency> 인터페이스입니다. 자세한 내용은 참조 [만들기에 대 한 프로젝트 구성](../../extensibility/internals/project-configuration-for-building.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [구성 옵션을 관리](../../extensibility/internals/managing-configuration-options.md)   
 [만들기에 대 한 프로젝트 구성](../../extensibility/internals/project-configuration-for-building.md)   
 [출력에 대한 프로젝트 구성](../../extensibility/internals/project-configuration-for-output.md)