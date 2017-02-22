---
title: "구성 옵션 개요 | Microsoft Docs"
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
  - "프로젝트 구성"
  - "구성 옵션에 대 한 구성 옵션"
ms.assetid: f4ad4dd3-b39e-42df-ad89-d403cdf24a2b
caps.latest.revision: 10
caps.handback.revision: 10
ms.author: "gregvanl"
manager: "ghogen"
---
# 구성 옵션 개요
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

프로젝트에 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 디버깅, 실행 및/또는 배포 된 빌드할 수 있는 여러 구성을 지원할 수 있습니다. 구성은 빌드 형식을 설명 하는 속성, 일반적으로 컴파일러 스위치 및 파일 위치 명명된 된 집합입니다. 기본적으로 새 솔루션에는 두 가지 구성, 디버그 및 릴리스 포함 됩니다. 이러한 구성은 특정 솔루션 및/또는 프로젝트 요구 사항에 맞게 수정할 또는 해당 기본 설정을 사용 하 여 적용할 수 있습니다. 일부 패키지는 두 가지 방법으로 작성할 수 있습니다: ActiveX 편집기로 또는 내부 구성 요소입니다. 그러나 여러 구성을 지원 하기 위해 프로젝트 필요가 없습니다. 사용할 수 있는 하나의 구성만 있으면 해당 구성은 모든 솔루션 구성에 매핑됩니다.  
  
 일반적으로 두 부분으로 구성 구성-구성 이름 (예: 디버그 또는 릴리스) 및 플랫폼 설정 합니다. 구성의 플랫폼 이름을 구성 대상 API 등을 설정 하는 환경 또는 운영 체제 플랫폼을 식별 합니다. 사용자의 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] ; 플랫폼을 만들 수 없습니다 VSPackage 허용 하는 프로젝트 중에서 선택 해야 합니다. 패키지 작성자에 의해 설정 된 모든 조건에 따라 패키지를 개발 하는 동안 만든 제공 플랫폼 사용자 설치 VSPackage 원하는 모든 플랫폼 이름을 수 노출 하는 경우. 사용자 수 속성 페이지 인스턴스화될 때 VSPackage를 통해 사용할 수 있게 하는 플랫폼 목록에서 선택 합니다.  
  
 일부 프로젝트 플랫폼의 개념을 지원 하므로 플랫폼 이름은 선택적입니다. 구성 플랫폼 이름이 없습니다, 문자열 "해당 없음" UI에 표시 됩니다.  
  
 각 솔루션에는 자체 집합이 구성 중 하나만 한 번에 활성화 될 수 있습니다. 솔루션 구성은 각 프로젝트에서 둘 이상의 구성의 집합입니다. "개 미만의" 규정 솔루션 구성에서 프로젝트를 제외 하는 옵션 때문입니다. 사용자는 원하는 사용자 지정 솔루션 구성을 만들 수 있습니다.  
  
 다음 표에서 프로젝트에 대 한 일반적인 구성을 설치 합니다. 행은 구성 이름과 플랫폼 이름 가진 열으로 표시 됩니다.  
  
|구성 이름|플랫폼-Win32|플랫폼-w i n 64|  
|------------------------|----------------------|----------------------|  
|디버그|\< debug Win32 설정>|\< Win64 디버그 설정>|  
|릴리스|\<: 릴리스 Win32 설정>|\< 릴리스 Win64 설정>|  
|MyConfig|N/A|\< MyConfig Win64 설정>|  
  
> [!NOTE]
>  "Win32" 플랫폼을 대상으로 하는 프로젝트에서 Win32를 지원 하지 않는 한 제외 하는 "MyConfig" 솔루션 구성을 만들 수 없습니다.  
  
 해당 솔루션에 작성, 실행, 디버깅 또는 배포 된 프로젝트 구성의 집합을 선택 하는 솔루션에 대 한 활성 구성을 변경 합니다. 예를 들어 활성 솔루션 구성에서 릴리스 디버그로 변경 하면 해당 솔루션 내의 모든 프로젝트는 솔루션의 디버그 구성에 표시 된 프로젝트의 구성을 사용 하 여 자동으로 작성 됩니다. 프로젝트의 구성을 않는다면 일반적으로 명명 된 디버그 사용자가 수동으로 변경 환경의 구성 관리자에서 있습니다.  
  
 각 프로젝트에 대해 저장 된 솔루션 구성 속성 프로젝트 이름, 프로젝트 구성 이름, 표시 여부을 작성 하거나 배포 하기 위해 플래그 및 플랫폼 이름을 포함 합니다. 자세한 내용은 참조 [솔루션 구성](../../extensibility/internals/solution-configuration.md)합니다.  
  
 사용자 확인 하 고 계층 구조 (솔루션 탐색기)에서 솔루션을 선택 하 여 속성 페이지를 열고 솔루션 구성 매개 변수를 설정할 수 있습니다. 마찬가지로, 볼 수 있으며 솔루션 탐색기에서 프로젝트를 선택 하 고 해당 프로젝트에 대 한 속성 페이지를 열면 하 여 프로젝트 구성 매개 변수를 설정.  
  
 사용자 한 프로젝트를 사용 하 여 릴리스 구성 설정 및 나머지 모든 디버그 구성 설정을 사용 하 여 필요한 경우 빌드할 수도 있습니다. 자세한 내용은 참조 [건물에 대 한 프로젝트 구성](../../extensibility/internals/project-configuration-for-building.md)합니다.  
  
 다음 다이어그램을 지 원하는 솔루션 및 프로젝트 구성을 인터페이스는 구현 하는 방법을 보여 줍니다.  
  
 ![구성 인터페이스 그래픽](../../extensibility/internals/media/vsconfiginterfaces.png "vsConfigInterfaces")  
구성 인터페이스  
  
 이전 다이어그램에 관련 된 참고 사항:  
  
-   `IDispatch` 구성 개체에 대 한 옵션으로 표시 됩니다. 특히, 찾아보기 개체에서 구성 인터페이스를 선택 사항입니다.  
  
-   `IVsDebuggableProjectCfg` 선택적 구성 개체에 표시 되어 있지만 디버깅 지원에 필요 합니다.  
  
-   `IVsProjectCfg2` 구성 개체의 경우 선택 사항으로 표시 하지만 지원 그룹화 하는 출력을 위해 필요 합니다.  
  
-    `Config Provider` 개체는 선택적 개체로 표시 되어 있지만를 구현 하는 옵션입니다. 프로젝트 개체 또는 별도 개체에 개체를 구현할 수 있습니다.  
  
-   `IVsCfgProvider2` 지원 되는 플랫폼 및 구성 편집에 대 한 필요 합니다. `IVsCfgProvider` 해당 기능을 구현 하지 않는 경우에 충분 합니다.  
  
-   동일한 클래스 가능한 별도 개체 결합 될 수 있는 대로 다이어그램에 표시 된 이러한 개체 중 일부는 특정 디자인 요구 사항에 기반 합니다. 그러나이 섹션의 다른 항목에서 개체와 해당 개체와 연결 된 인터페이스 살펴봅니다 다이어그램에서 설명 하는 시나리오에 따라.  
  
-   특정 개체를 개별적으로 구현 됩니다. 예를 들어, 프로젝트 및 솔루션 구축 별도 스레드 및 빌드에 대 한 구성을 설명 하는 개체에서 빌드 생활을 별도로 관리 하는 개체에서 발생 합니다.  
  
 참조에 대 한 자세한 내용은 구성 개체 인터페이스 및 위 다이어그램의 구성 공급자 개체 인터페이스 [프로젝트 구성 개체](../../extensibility/internals/project-configuration-object.md)합니다. 또한 [건물에 대 한 프로젝트 구성](../../extensibility/internals/project-configuration-for-building.md) 구성 작성기 및 빌드 종속성 개체 인터페이스에 대 한 자세한 정보를 제공 하 고 [배포 관리를 위한 프로젝트 구성](../../extensibility/internals/project-configuration-for-managing-deployment.md) 추가로 구성 배포자 및 배포 종속성 개체에 연결 된 인터페이스에 설명 합니다. 마지막으로, [출력에 대 한 프로젝트 구성](../../extensibility/internals/project-configuration-for-output.md) 출력 그룹 및 출력 개체 인터페이스 및 구성에 종속 된 속성 보기 및 설정에 대 한 속성 페이지의 사용에 설명 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgProvider2>   
 [빌드를 위한 프로젝트 구성](../../extensibility/internals/project-configuration-for-building.md)   
 [솔루션 구성](../../extensibility/internals/solution-configuration.md)