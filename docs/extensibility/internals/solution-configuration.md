---
title: "솔루션 구성 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: solution configurations
ms.assetid: f22cfc75-3e31-4e0d-88a9-3ca99539203b
caps.latest.revision: "13"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 129f86fae5de5501d72b0cdbe5e261717e60e780
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="solution-configuration"></a>솔루션 구성
솔루션 구성 솔루션 수준 속성을 저장 합니다. 직접 실행의 동작에서 **시작** (F5) 키 및 **빌드** 명령입니다. 기본적으로 이들이 명령은 빌드하고 디버그 구성을 시작 합니다. 두 명령 모두 솔루션 구성의 컨텍스트에서 실행 됩니다. 즉, 사용자를 시작 및 빌드 설정을 통해 구성 된 모든 활성 솔루션 f5 키를 예상할 수 있도록 합니다. 환경이 빌드 및 실행 하는 데 있어 프로젝트 대신 솔루션을 위해 최적화 하도록 설계 되었습니다.  
  
 Visual Studio 표준 도구 모음 시작 단추 및 솔루션 구성 드롭다운 목록에서 시작 단추 오른쪽을 포함합니다. 이 목록에는 f 5를 누를 때 시작 되도록 구성을 선택 하거나 자신의 솔루션 구성 만들기, 기존 구성을 편집 하거나 사용자 수 있습니다.  
  
> [!NOTE]
>  없는 확장성 인터페이스를 작성 하거나 편집할 솔루션 구성 있습니다. 사용 해야 `DTE.SolutionBuilder`합니다. 그러나 솔루션 빌드를 관리 하기 위한 확장 Api는. 자세한 내용은 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionBuildManager2>을 참조하세요.  
  
 프로젝트 형식에서 지 원하는 솔루션 구성을 구현 하는 방법은 다음과 같습니다.  
  
-   프로젝트  
  
     현재 솔루션에 있는 프로젝트의 이름을 표시 합니다.  
  
-   구성  
  
     프로젝트 형식에 따라 지원 되는 구성의 목록을 제공 하 고 구현 속성 페이지에 표시 하려면 <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgProvider2>합니다.  
  
     구성 열이 솔루션 구성에서 빌드할 수 있도록 프로젝트 구성의 이름을 표시 하 고 화살표 단추를 클릭 하면 프로젝트 구성의 모든를 나열 합니다. 환경에서 <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgProvider2.GetCfgNames%2A> 메서드 데이터를이 목록을 입력 합니다. 경우는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgProvider2.GetCfgProviderProperty%2A> 메서드 나타냅니다는 프로젝트만 지원 구성 편집, 새로 만들기 또는 구성 머리글 아래에서 편집 선택도 표시 됩니다. 메서드를 호출 하는 대화 상자를 시작 하는 각 선택이 항목은 `IVsCfgProvider2` 프로젝트의 구성을 편집 하는 인터페이스입니다.  
  
     프로젝트 구성을 지원 하지 않고, 구성 열 None를 표시 하며을 사용할 수 없습니다.  
  
-   플랫폼  
  
     선택한 프로젝트 구성, 빌드 및 모든 프로젝트에 대 한 사용 가능한 플랫폼 화살표 단추를 클릭할 때 나열 되는 플랫폼을 표시 합니다. 환경에서 <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgProvider2.GetPlatformNames%2A> 메서드 데이터를이 목록을 입력 합니다. 경우는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsCfgProvider2.GetCfgProviderProperty%2A> 메서드 나타냅니다는 프로젝트만 지원 플랫폼 편집, 새로 만들기 또는 편집 선택 플랫폼 제목 아래에 표시 됩니다. 호출 하는 대화 상자를 시작 하는 각 선택이 항목 `IVsCfgProvider2` 프로젝트의 사용 가능한 플랫폼을 편집 하는 메서드.  
  
     프로젝트 플랫폼을 지원 하지 않으면 해당 프로젝트에 대 한 플랫폼 열의 None를 표시 하며을 사용할 수 없습니다.  
  
-   빌드  
  
     현재 솔루션 구성에서 프로젝트를 빌드할 여부를 지정 합니다. 선택 하지 않은 프로젝트는 솔루션 수준의 빌드 명령이 포함 프로젝트 종속성 든 관계 없이 호출 되는 경우에 작성 되지 않았습니다. 빌드할 선택 되지 않은 프로젝트 디버깅, 실행, 패키지 및 솔루션을 배포에 포함 됩니다.  
  
-   배포  
  
     시작 또는 배포 명령을 선택한 솔루션 빌드 구성에 사용할 경우 프로젝트를 배포할 수 있는지 여부를 지정 합니다. 이 필드에 대 한 확인란을 구현 하 여 배포 지 원하는 경우 사용할 수는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsDeployableProjectCfg> 인터페이스를 해당 <xref:Microsoft.VisualStudio.Shell.Interop.IVsProjectCfg2> 개체입니다.  
  
 새 솔루션 구성을 추가 하 고 나면는 사용자가 빌드 및/또는 해당 구성을 시작 하려면 표준 도구 모음의 솔루션 구성 드롭다운 목록 상자에서 선택할 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [구성 옵션을 관리](../../extensibility/internals/managing-configuration-options.md)   
 [만들기에 대 한 프로젝트 구성](../../extensibility/internals/project-configuration-for-building.md)   
 [프로젝트 구성 개체](../../extensibility/internals/project-configuration-object.md)