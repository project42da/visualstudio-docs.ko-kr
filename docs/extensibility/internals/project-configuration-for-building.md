---
title: "빌드를 위한 프로젝트 구성 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "프로젝트 [Visual Studio SDK] 건물에 대 한 구성"
  - "프로젝트 구성, 구축"
ms.assetid: 2c83615d-fa4d-4b9f-b315-7a69b3000da0
caps.latest.revision: 11
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 11
---
# 빌드를 위한 프로젝트 구성
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

지정된 된 솔루션에 대 한 솔루션 구성 목록은 솔루션 구성 대화 상자에서 관리 됩니다.  
  
 사용자 각각 고유한 이름이 있는 추가 솔루션 구성을 만들 수 있습니다. 사용자는 새 솔루션 구성 만들면 해당 이름이 있는 경우 IDE 프로젝트 또는 디버그에 해당 구성 이름에 기본값입니다. 필요한 경우 특정 요구 사항에 맞게 선택을 변경할 수 있습니다. 프로젝트에서 새 솔루션 구성의 이름과 일치 하는 구성을 지원 하는 경우이 동작에만 예외가입니다. 예를 들어, 프로젝트 1 및 Project2는 솔루션에 포함 되어 있습니다. 프로젝트 1을 디버그, 소매 및 MyConfig1 프로젝트 구성에 있습니다. Project2는 디버그, 소매 및 MyConfig2 프로젝트 구성에 있습니다.  
  
 사용자가 만든 MyConfig2 이라는 새 솔루션 구성을 프로젝트 1는 기본적으로 디버그 구성을 솔루션 구성에 바인딩합니다. 또한 Project2 기본적으로 MyConfig2 구성을 솔루션 구성에 바인딩합니다.  
  
> [!NOTE]
>  바인딩은 대\/소문자 구분입니다.  
  
 사용자가 선택 하는 경우는 **다중 선택** 항목 환경 구성 드롭다운 목록에서 사용 가능한 구성 목록을 제공 하는 대화 상자를 표시 합니다.  
  
 ![여러 구성](~/docs/extensibility/internals/media/vsmultiplecfgs.gif "vsMultipleCfgs")  
여러 구성  
  
 이 대화 상자에서 사용자가 하나 또는 여러 개의 구성을 선택할 수 있습니다. 선택 하면 속성 페이지 대화 상자에 표시 되는 속성 값 선택한 구성에 대 한 값의 교집합을 반영 합니다.  
  
 참조 [솔루션 구성](../../extensibility/internals/solution-configuration.md) 추가 하 고 솔루션 및 프로젝트에 대 한 구성을 이름 바꾸기와 관련 된 정보입니다.  
  
 프로젝트 종속성 및 빌드 순서는 독립 솔루션 구성: 즉,만 설정할 수 있습니다 모든 솔루션에서 프로젝트에 대해 하나의 종속성 트리를 구성 합니다. 솔루션 또는 프로젝트를 마우스 오른쪽 단추로 클릭 하 고 하나를 선택 하는 **프로젝트 종속성** 또는 **프로젝트 빌드 순서** 열립니다 옵션은 **프로젝트 종속성** 대화 상자입니다. 열 수도 있습니다는 **프로젝트** 메뉴.  
  
 ![프로젝트 종속성](~/docs/extensibility/internals/media/vsprojdependencies.gif "vsProjDependencies")  
프로젝트 종속성  
  
 프로젝트 종속성 프로젝트 빌드 순서를 결정 합니다. 대화 상자에서 빌드 순서 탭을 사용 하 여 솔루션 내의 프로젝트 빌드는 및의 종속 관계 탭을 사용 하 여 빌드 순서를 수정 하 여 정확한 순서를 확인 합니다.  
  
> [!NOTE]
>  지정 하는 명시적 종속성으로 인해 환경에 의해 추가 된 목록에서 확인란이 선택 되어 있지만 흐리게 표시 하는 프로젝트는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildDependency> 또는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsDeployDependency> 인터페이스를 만들고 변경할 수 없습니다. 예를 들어,에서 프로젝트 참조에 추가 된 [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)] 다른 프로젝트에 프로젝트 참조를 삭제 하 여 제거 될 수 있는 빌드 종속성을 자동으로 추가 합니다. 이렇게 종속성 루프를 만드는 것 때문에 해당 확인란 선택 취소 되어 있고 흐리게 표시 하는 프로젝트를 선택할 수 없습니다 \(예를 들어 프로젝트 1은 Project2, 종속 되며 Project2 프로젝트 1에 종속 됩니다.\), 빌드가 중단 것입니다.  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 빌드 프로세스는 일반적인 컴파일 및 단일 빌드 명령으로 호출 되는 링크 작업에 포함 됩니다. 다른 두 개의 빌드 프로세스도 지원 될 수 있습니다: 정리 작업을 이전 빌드 및 구성의 출력 항목 변경 되었는지 여부를 결정 하는 최신 검사에서 모든 출력 항목을 삭제 합니다.  
  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectCfg2> 해당 개체를 반환 <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildableProjectCfg> \(에서 반환 된 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectCfg2.get_CfgType%2A>\) 빌드 프로세스를 관리할 수 있습니다. 를 실행 하는 동안 빌드 작업의 상태를 보고 하려면 구성을 확인에 대 한 호출 <xref:Microsoft.VisualStudio.Shell.Interop.IVsBuildStatusCallback>, 환경에 의해 구현 되는 인터페이스 및 빌드 상태 이벤트에 관심 있는 다른 개체입니다.  
  
 작성 되 면 구성 설정은 디버거의 제어에서 실행할 수 있는지 여부를 확인 하려면 사용할 수 있습니다. 구성을 구현 <xref:Microsoft.VisualStudio.Shell.Interop.IVsDebuggableProjectCfg> 디버깅을 지원 합니다.  
  
 프로젝트 종속성을 구현한 후 자동화 모델을 통해 종속성을 프로그래밍 방식으로 조작할 수 있습니다. 호출 하면 <xref:EnvDTE.SolutionBuild.BuildDependencies%2A> 자동화 모델에서입니다. 솔루션 빌드 관리자 구성 및 해당 속성을 직접 조작 허용 하는 VSIP API 수준 인터페이스가 없는 사용할 수 있습니다.  
  
 또한 프로젝트 종속성 창에서 표를 제공할 수 있습니다. 자세한 내용은 [눈금 표시 속성](../../extensibility/internals/properties-display-grid.md)을 참조하세요.  
  
## 참고 항목  
 [구성 옵션 관리](../../extensibility/internals/managing-configuration-options.md)   
 [배포를 관리 하기 위한 프로젝트 구성](../../extensibility/internals/project-configuration-for-managing-deployment.md)   
 [출력에 대 한 프로젝트 구성](../../extensibility/internals/project-configuration-for-output.md)