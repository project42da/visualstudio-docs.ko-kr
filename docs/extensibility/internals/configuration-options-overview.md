---
title: "구성 옵션 개요 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- project configurations
- configuration options, about configuration options
ms.assetid: f4ad4dd3-b39e-42df-ad89-d403cdf24a2b
caps.latest.revision: "10"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 0edfe84e26a9331b8c40ec24b00387768bdbba82
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="configuration-options-overview"></a>옵션 구성 개요
프로젝트에 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 디버깅, 실행, 및/또는 배포 된 빌드할 수 있는 여러 구성을 지원할 수 있습니다. 구성에는 컴파일러 스위치와 파일 위치 속성의 명명된 된 집합 설명 하는 경우 빌드 형식입니다. 기본적으로 새 솔루션 디버그 및 릴리스 구성을 포함 됩니다. 이러한 구성은 특정 프로젝트 및/또는 솔루션 요구 사항에 맞게 수정할 또는 해당 기본 설정을 사용 하 여 적용할 수 있습니다. 두 가지 방법으로 일부 패키지를 빌드할 수 있습니다: ActiveX 편집기로 또는 내부 구성 요소로 합니다. 그러나 여러 구성을 지원 하기 위해 프로젝트 필요가 없습니다. 사용할 수 있는 하나의 구성만 있으면 해당 구성은 솔루션 구성의 모든 열로 매핑됩니다.  
  
 일반적으로 두 부분으로 구성 구성-구성 이름 (예: 디버그 또는 릴리스) 및 플랫폼 설정 합니다. 구성의 플랫폼 이름을 구성 대상 API와 같은 설정 하는 환경 또는 운영 체제 플랫폼을 식별 합니다. 사용자가 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 플랫폼; 만들 수 없습니다 허용 하는 VSPackage 프로젝트 중에서 선택 해야 합니다. 패키지 작성자에 의해 설정 된 모든 조건에 따라 때 만든 패키지를 개발 하는 동안 제공 플랫폼 사용자 설치, VSPackage 원하는 모든 플랫폼 이름을 발생할 수 있습니다. 사용자 수의 속성 페이지를 인스턴스화할 때 VSPackage를 통해 사용할 수 있게 하는 플랫폼 목록에서 선택 합니다.  
  
 일부 프로젝트 플랫폼의 개념을 지원 하므로 플랫폼 이름은 선택적입니다. 구성에 플랫폼 이름을 없는 경우 "n"/ 문자열 UI에 표시 됩니다.  
  
 각 솔루션은 고유한 구성 중 하나만 한 번에 활성화할 수 있습니다. 솔루션 구성은 집합이 각 프로젝트에서 둘 이상의 구성 합니다. "최대" stipulation 솔루션 구성에서 프로젝트를 제외 하는 옵션 때문입니다. 사용자가 자신의 사용자 지정 솔루션 구성을 만들 수 있습니다.  
  
 다음 표에서 프로젝트에 대 한 일반적인 구성을 설치를 보여 줍니다. 행은 구성 이름과 플랫폼 이름 가진 열으로 표시 됩니다.  
  
|구성 이름|플랫폼-Win32|플랫폼-Win64|  
|------------------------|----------------------|----------------------|  
|디버그|\<디버그 Win32 설정 >|\<디버그 Win64 설정 >|  
|릴리스|\<릴리스 Win32 설정 >|\<Win64 설정을 해제 합니다. >|  
|MyConfig|N/A|\<MyConfig Win64 설정 >|  
  
> [!NOTE]
>  "Win32" 플랫폼을 대상으로 하는 프로젝트에서 Win32를 지원 하지 않는 한 제외 된 "MyConfig" 솔루션 구성을 만들 수 없습니다.  
  
 해당 솔루션에 작성, 실행, 디버깅 또는 배포 된 프로젝트 구성 집합을 선택 하는 솔루션에 대 한 활성 구성을 변경 합니다. 예를 들어 릴리스와에서 디버그로 활성 솔루션 구성을 변경한 경우 해당 솔루션 내의 모든 프로젝트는 솔루션의 디버그 구성에 표시 된 프로젝트 구성을 사용 하 여 자동으로 작성 됩니다. 프로젝트의 구성을 아니라면 일반적으로 명명 된 디버그 사용자가 변경한 수동 환경의 구성 관리자에서 합니다.  
  
 각 프로젝트에 대해 저장 된 솔루션 구성 속성에는 프로젝트 이름, 프로젝트 구성 이름, 표시 여부을 작성 하거나 배포 하기 위해 플래그 및 플랫폼 이름을 포함 합니다. 자세한 내용은 참조 [솔루션 구성](../../extensibility/internals/solution-configuration.md)합니다.  
  
 사용자가 볼 수 있으며 계층 (솔루션 탐색기)에서 솔루션을 선택 하 여 속성 페이지 열기 솔루션 구성 매개 변수를 설정. 마찬가지로, 보고 하 고 솔루션 탐색기에서 프로젝트를 선택 하 여 해당 프로젝트에 대 한 속성 페이지 열기 프로젝트 구성 매개 변수를 설정할 수 있습니다.  
  
 사용자를 사용 하 여 릴리스 구성 설정 및 나머지 모든 디버그 구성 설정으로 필요한 경우 한 프로젝트를 빌드할 수도. 자세한 내용은 참조 [만들기에 대 한 프로젝트 구성](../../extensibility/internals/project-configuration-for-building.md)합니다.  
  
 다음 다이어그램에서는 솔루션 및 프로젝트 구성이 지원 인터페이스는 구현 하는 방법을 보여 줍니다.  
  
 ![구성 인터페이스 그래픽](../../extensibility/internals/media/vsconfiginterfaces.gif "vsConfigInterfaces")  
구성 인터페이스  
  
 위의 다이어그램에 관련 된 몇 가지 참고 사항:  
  
-   `IDispatch`구성 개체에 대 한 옵션으로 표시 되어 있습니다. 특히, 찾아보기 개체에서 구성 인터페이스 하기로 선택 사항입니다.  
  
-   `IVsDebuggableProjectCfg`구성 개체의 경우 선택 사항으로 표시 되어 있지만 디버깅 지원에 필요 합니다.  
  
-   `IVsProjectCfg2`구성 개체의 경우 선택 사항으로 표시 되지만 지원 그룹화 하는 출력을 위해 필요 합니다.  
  
-   `Config Provider` 개체는 선택적 개체로 표시 되어 있지만 옵션에는 기본 클래스를 구현할 수 있는 위치입니다. 프로젝트 개체 또는 별도 개체에 개체를 구현할 수 있습니다.  
  
-   `IVsCfgProvider2`지원 되는 플랫폼 및 구성 편집에 대 한 필요 합니다. `IVsCfgProvider`해당 기능을 구현 하지 않는 경우에 충분 합니다.  
  
-   동일한 클래스 필요한 별도 개체를 결합할 수 있는 대로 다이어그램에 표시 된 이러한 개체 중 일부 요구 사항을 기반으로 특정 디자인 합니다. 그러나이 섹션의 다른 항목에서는 개체와 해당 개체와 연결 된 인터페이스 살펴봅니다 다이어그램에 제시 된 시나리오에 따라.  
  
-   특정 개체를 개별적으로 구현 됩니다. 예를 들어 프로젝트 및 솔루션 구성 별도 스레드와 빌드에 대 한 구성을 설명 하는 개체에서 빌드 생활 편의 별도로 관리 하는 개체에서 발생 합니다.  
  
 구성 개체 인터페이스 및 위 다이어그램의 구성 공급자 개체 인터페이스에 자세한 내용은 참조 하십시오. [프로젝트 구성 개체](../../extensibility/internals/project-configuration-object.md)합니다. 또한 [만들기에 대 한 프로젝트 구성](../../extensibility/internals/project-configuration-for-building.md) 구성 작성기 및 빌드 종속성 개체 인터페이스에 더 많은 정보를 제공 하 고 [배포 관리를 위한 프로젝트 구성을](../../extensibility/internals/project-configuration-for-managing-deployment.md) 배포자 구성 및 배포 종속성 개체에 연결 된 인터페이스에 자세히 설명 합니다. 마지막으로, [출력에 대 한 프로젝트 구성](../../extensibility/internals/project-configuration-for-output.md) 을 보고 구성 종속성 속성을 설정할 속성 페이지를 사용 하 여 출력 그룹 및 출력 개체 인터페이스에 설명 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgProvider2>   
 [만들기에 대 한 프로젝트 구성](../../extensibility/internals/project-configuration-for-building.md)   
 [솔루션 구성](../../extensibility/internals/solution-configuration.md)