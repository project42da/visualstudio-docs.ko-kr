---
title: "프로젝트 만들기에 대 한 구성 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- projects [Visual Studio SDK], configuration for building
- project configurations, building
ms.assetid: 2c83615d-fa4d-4b9f-b315-7a69b3000da0
caps.latest.revision: "11"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: f89736c448570157711c15d2d86091d91e1f30d6
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="project-configuration-for-building"></a>만들기에 대 한 프로젝트 구성
지정된 된 솔루션에 대 한 솔루션 구성 목록에는 솔루션 구성 대화 상자에서 관리 됩니다.  
  
 사용자가 각각 고유한 이름이 있는 추가 솔루션 구성을 만들 수 있습니다. 새 솔루션 구성에서 사용자가 만든 없는 해당 이름이 있는 경우 IDE는 프로젝트 또는 디버그에 해당 구성 이름에 기본값입니다. 필요한 경우 특정 요구 사항에 맞게 선택을 변경할 수 있습니다. 프로젝트에 새 솔루션 구성의 이름과 일치 하는 구성을 지원 하는 경우이 동작에만 예외가입니다. 예를 들어 Project1 및 Project2 솔루션을 포함 합니다. Project1은 디버그, 정품 및 MyConfig1 프로젝트 구성에 있습니다. Project2는 디버그, 정품 및 MyConfig2 프로젝트 구성에 있습니다.  
  
 사용자가 만든 MyConfig2 이라는 새 솔루션 구성을 Project1는 기본적으로 디버그 구성을 솔루션 구성에 바인딩합니다. 또한 Project2 기본적으로 해당 MyConfig2 구성을 솔루션 구성에 바인딩합니다.  
  
> [!NOTE]
>  바인딩은 대/소문자 구분입니다.  
  
 사용자가 선택할 때의 **다중 선택** 항목 환경 구성 드롭 다운 목록에서 사용 가능한 구성 목록을 제공 하는 대화 상자를 표시 합니다.  
  
 ![여러 구성을](../../extensibility/internals/media/vsmultiplecfgs.gif "vsMultipleCfgs")  
여러 구성  
  
 이 대화 상자에서 사용자는 하나 또는 여러 개의 구성을 선택할 수 있습니다. 선택 하면 속성 페이지 대화 상자에 표시 되는 속성 값 선택한 구성에 대 한 값의 교집합을 반영 합니다.  
  
 참조 [솔루션 구성](../../extensibility/internals/solution-configuration.md) 추가 및 솔루션 및 프로젝트에 대 한 구성을 이름 바꾸기와 관련 된 정보입니다.  
  
 프로젝트 종속성 및 빌드 순서는 독립 솔루션 구성: 즉,만 설정할 수 있습니다 모든 솔루션의 프로젝트에 대 한 종속성을 하나 트리를 구성 합니다. 솔루션 또는 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 하나를 선택 하 고 **프로젝트 종속성** 또는 **프로젝트 빌드 순서** 열립니다 옵션는 **프로젝트 종속성** 대화 상자. 열 수도 있습니다는 **프로젝트** 메뉴.  
  
 ![프로젝트 종속성](../../extensibility/internals/media/vsprojdependencies.gif "vsProjDependencies")  
프로젝트 종속성  
  
 프로젝트 종속성 프로젝트 빌드 순서를 결정 합니다. 대화 상자에서 빌드 순서 탭을 사용 하 여 솔루션 내에서 프로젝트를 작성 되 고 종속성 탭을 사용 하 여 빌드 순서를 수정 하 여 정확한 순서를 확인 합니다.  
  
> [!NOTE]
>  로 지정 된 명시적 종속성으로 인해 환경에 의해 추가 된 목록에 확인란이 선택 되어 있지만 흐리게 표시 하는 프로젝트는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildDependency> 또는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsDeployDependency> , 인터페이스를 만들고 변경할 수 없습니다. 예를 들어에서 프로젝트 참조를 추가할는 [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] 다른 프로젝트에 프로젝트 참조를 삭제 하 여 제거 될 수 있는 빌드 종속성을 자동으로 추가 합니다. 이렇게 종속성 루프가 생성 하기 때문에 해당 확인란 선택 취소 되어 있고 흐리게 표시 하는 프로젝트를 선택할 수 없습니다 (예를 들어 Project1: Project2에 따라 달라진 다는 및 Project2 Project1 종속 것) 빌드가 중단 것입니다.  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]빌드 프로세스의 일반적인 컴파일 및 빌드 단일 명령으로 호출 되는 링크 작업에 포함 됩니다. 다른 두 개의 빌드 프로세스 지원 될 수 있습니다: 이전 빌드 및 구성의 출력 항목에 변경 되었는지 여부를 결정 하는 최신 검사에서 모든 출력 항목을 삭제할 정리 작업을 합니다.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectCfg2>해당 개체를 반환 <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildableProjectCfg> (에서 반환 된 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectCfg2.get_CfgType%2A>) 빌드 프로세스에서 관리할 수 있습니다. 를 실행 하는 동안 빌드 작업의 상태를 보고 하려면 구성을 확인에 대 한 호출 <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildStatusCallback>는 환경에서 구현 된 인터페이스 및 빌드 상태 이벤트에 관심 있는 다른 모든 개체.  
  
 작성 되 면 구성 설정은 디버거의 제어를 받으며 실행 될 수 있는지 여부를 결정 하 사용할 수 있습니다. 구성을 구현 <xref:Microsoft.VisualStudio.Shell.Interop.IVsDebuggableProjectCfg> 디버깅을 지원할 수 있습니다.  
  
 프로젝트 종속성을 구현한 후 자동화 모델을 통해 종속성을 프로그래밍 방식으로 조작할 수 있습니다. 호출 하면 <xref:EnvDTE.SolutionBuild.BuildDependencies%2A> 자동화 모델에서입니다. 솔루션 빌드 관리자 구성 및 해당 속성을 직접 조작 허용 VSIP API 레벨 인터페이스가 없는 사용할 수 있습니다.  
  
 또한 프로젝트 종속성 창에 표를 제공할 수 있습니다. 자세한 내용은 참조 [속성 눈금 표시](../../extensibility/internals/properties-display-grid.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [구성 옵션을 관리](../../extensibility/internals/managing-configuration-options.md)   
 [배포를 관리 하기 위한 프로젝트 구성](../../extensibility/internals/project-configuration-for-managing-deployment.md)   
 [출력에 대한 프로젝트 구성](../../extensibility/internals/project-configuration-for-output.md)