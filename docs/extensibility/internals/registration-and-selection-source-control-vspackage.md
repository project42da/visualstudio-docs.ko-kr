---
title: 등록 및 선택 (소스 제어 VSPackage) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- registration, source control packages
- source control packages, registration
ms.assetid: 7d21fe48-489a-4f55-acb5-73da64c4e155
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 1d7bcdb8f930430ac00335777e2c088ce52a34bb
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="registration-and-selection-source-control-vspackage"></a>등록 및 선택 (소스 제어 VSPackage)
에 노출 하려면 VSPackage를 등록 해야 하는 소스 제어는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다. 둘 이상의 소스 제어 VSPackage를 등록 하는 경우 적절 한 시간에 로드 하는 VSPackage 선택할 수 있습니다. 참조 [Vspackage](../../extensibility/internals/vspackages.md) Vspackage 및 등록 하는 방법에 대 한 자세한 내용은 합니다.  
  
## <a name="registering-a-source-control-package"></a>소스 제어 패키지를 등록 하는 중  
 원본 제어 패키지를 등록 하는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 환경 지원 되는 기능에 대 한 하 고 쿼리를 찾을 수 있습니다. 명령 또는 기능 필요 하거나 명시적으로 요청 된 경우에 패키지의 인스턴스 생성 하는 지연 로드 체계에 따라입니다.  
  
 HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\VisualStudio 버전별 레지스트리 키에 정보를 저장 하는 Vspackage\\*X.Y*여기서 *X* 주 버전 번호 이며 *Y* 부 버전 번호입니다. 이 방법은 여러 버전의 side-by-side-설치를 지원 하기 위해 기능을 제공 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다.  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] UI (사용자 인터페이스) 소스 제어 Vspackage 뿐만 아니라 여러 설치한 소스 제어 플러그 인 (소스 제어 어댑터 패키지)를 통해 중에서 선택 영역을 지원 합니다. 있을 수 있습니다 하나만 활성 소스 제어 플러그 인 또는 VSPackage 한 번에. 그러나 아래 설명과 같이 IDE 자동 솔루션을 기반으로 패키지를 교환 메커니즘을 통해 소스 제어 플러그 인 및 Vspackage 간의 전환을 허용 합니다. 이 선택 메커니즘을 사용 하도록 설정 하려면 소스 제어 VSPackage 안되며 몇 가지 요구 사항이 있습니다.  
  
### <a name="registry-entries"></a>레지스트리 항목  
 소스 제어 패키지 항목이 세 개인 guid가 필요합니다.  
  
-   패키지 GUID: 소스 제어 구현 (이 섹션의 ID_Package 라고 함)를 포함 하는 패키지에 대 한 주 GUID입니다.  
  
-   소스 제어 GUID: 소스 제어에 Visual Studio 소스 제어 스텁을 등록 하는 데 사용 되는 VSPackage에 대 한 GUID 이므로 명령 UI 컨텍스트 GUID로도 사용 됩니다. 소스 제어 서비스 GUID GUID 소스 제어에서 등록 되어 있습니다. 예제에서는 소스 제어 GUID ID_SccProvider 라고 합니다.  
  
-   원본 제어 서비스 GUID: 개인 서비스 (이 섹션의 SID_SccPkgService 라고 함)는 Visual Studio에서 사용 하는 GUID입니다. 이 외에도 소스 제어 패키지 Vspackage, 도구 창에 대 한 다른 Guid를 정의 하 고 만들어야 합니다.  
  
 다음 레지스트리 항목은 소스 제어 VSPackage에서 이루어져야 합니다.  
  
|키 이름|항목|  
|--------------|-------------|  
|`HKEY_LOCAL_MACHINE\   SOFTWARE\     Microsoft\       VisualStudio\         X.Y\           SourceControlProviders\`|(기본값) = rg_sz: {ID_SccProvider}|  
|`HKEY_LOCAL_MACHINE\   SOFTWARE\     Microsoft\       VisualStudio\         X.Y\           SourceControlProviders\             {ID_SccProvider}\`|(기본값) = rg_sz:\<패키지의 이름 ><br /><br /> 서비스 = rg_sz: {SID_SccPkgService}|  
|`HKEY_LOCAL_MACHINE\   SOFTWARE\     Microsoft\       VisualStudio\         X.Y\           SourceControlProviders\             {ID_SccProvider}\               Name\`|(기본값) = rg_sz: #\<지역화 된 이름에 대 한 리소스 ID ><br /><br /> 패키지 rg_sz =: {ID_Package}|  
|`HKEY_LOCAL_MACHINE\   SOFTWARE\     Microsoft\       VisualStudio\         X.Y\           SolutionPersistence\             <PackageName>\`<br /><br /> (사항에 유의 키 이름이 `SourceCodeControl`에서 이미 사용 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 항목으로 사용할 수 없는 \<PackageName >.)|(기본값) = rg_sz: {ID_Package}|  
  
## <a name="selecting-a-source-control-package"></a>소스 제어 패키지를 선택합니다.  
 여러 가지 소스 제어 플러그 인 API 기반 플러그 인 및 소스 제어 Vspackage를 동시에 등록 될 수 있습니다. 소스 제어 플러그 인 또는 VSPackage를 선택 하는 프로세스를 확인 해야 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 플러그 인을 로드 또는 적절 한 시간에 VSPackage 불필요 한 구성 요소를 로드 하 여 필요한 될 때까지 연기할 수 있습니다. 또한 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 메뉴 항목과 대화 상자, 도구 모음을 포함 하는 다른 비활성 Vspackage에서 모든 UI를 제거 하 고 현재 VSPackage에 대 한 UI를 표시 해야 합니다.  
  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 다음 작업 중 하나를 수행 하는 경우 소스 제어 VSPackage를 로드 합니다.  
  
-   (소스 제어에서 솔루션은) 하는 경우 솔루션이 열릴 수 있습니다.  
  
     솔루션 또는 소스 제어에서 프로젝트를 열 때 IDE는 VSPackage를 로드 해당 솔루션에 대 한 지정 된 소스 제어를 하면 됩니다.  
  
-   소스 제어 VSPackage의 메뉴 명령 중 하나를 실행 합니다.  
  
 VSPackage는 실제로 되도록 하려는 경우에 필요한 모든 구성 요소를 로드 해야 하는 소스 제어 사용 (그렇지 않으면이 라고 지연된 로드).  
  
### <a name="automatic-solution-based-vspackage-swapping"></a>자동 솔루션 기반 VSPackage 교환  
 소스 제어 Vspackage를 수동으로 바꿀 수 있습니다를 통해는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] **옵션** 대화 상자는 **소스 제어** 범주입니다. 자동 솔루션을 기반으로 패키지를 교환 하는 특정 솔루션에 대 한 지정 된 소스 제어 패키지를 해당 솔루션을 열 때 자동으로 활성으로 설정 되 고 있다는 것을 의미 합니다. 모든 소스 제어 패키지를 구현 해야 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProvider.SetActive%2A> 및 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSccProvider.SetInactive%2A>합니다. [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 전환 둘 다 처리 소스 제어 플러그 인 (소스 제어 플러그 인 API 구현) 및 소스 Vspackage를 제어 합니다.  
  
 소스 제어 어댑터 패키지는 모든 소스 제어 플러그 인 API를 기반으로 전환 하는 데 사용은 플러그 인 합니다. 중간 소스 제어 어댑터 패키지도 전환 하 고 어떤 소스 제어 플러그 인을 결정 하는 프로세스를 사용자에 게는 활성 또는 비활성으로 설정 되어 있어야 합니다. 소스 제어 플러그 인 활성화 된 경우에 항상 어댑터 패키지 활성화 되어 있습니다. 두 소스 제어 플러그 인 금액 단순히을 로드 하 고 플러그 인 DLL 언로드를 전환 합니다. 그러나 소스 제어 VSPackage 전환할에서는 적절 한 VSPackage를 로드 IDE와의 상호 작용 합니다.  
  
 소스 제어 VSPackage는 솔루션을 열 때 솔루션 파일에는 VSPackage에 대 한 레지스트리 키가 호출 됩니다. 솔루션을 열면 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 레지스트리 값을 찾아서 적절 한 소스 제어 VSPackage를 로드 합니다. 모든 소스 제어 Vspackage 위에 설명 된 레지스트리 항목이 있어야 합니다. 소스 제어에서 사용 중인 솔루션 연결 된 특정 소스 제어 VSPackage 것으로 표시 되어 있습니다. 소스 제어 Vspackage를 구현 해야 합니다는 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionPersistence> 자동 솔루션 기반 VSPackage 교환 수 있도록 합니다.  
  
### <a name="visual-studio-ui-for-package-selection-and-switching"></a>Visual Studio 패키지 선택 및 전환에 대 한 UI  
 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 제공 하는 소스 제어 VSPackage에 대 한 UI 및 플러그 인 선택에는 **옵션** 대화 상자는 **소스 제어** 범주입니다. 현재 소스 제어 플러그 인을 선택 하는 사용자 또는 VSPackage 수 있습니다. 드롭다운 목록에 있습니다.  
  
-   모든 소스 제어 패키지 설치  
  
-   소스 제어 플러그 인 설치 된 모든  
  
-   "None" 옵션을 소스 코드 제어를 해제  
  
 현재 소스 제어 선택에 대 한 UI에만 표시 됩니다. VSPackage 선택 이전 VSPackage에 대 한 UI를 숨깁니다 및 새 UI를 표시 합니다. 활성 VSPackage 사용자 단위로 선택 되어 있습니다. 사용자의 복사본이 여러 개 있으면 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 동시에 연, 각각 서로 다른 활성 VSPackage를 사용할 수 있습니다. 각 사용자의 별도 인스턴스를 가질 수 여러 사용자가 동일한 컴퓨터에 로그온 하는 경우 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 각각 다른 액티브 VSPackage 엽니다. 때의 여러 인스턴스 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 마지막 열려 있는 솔루션은 다시 시작 시 활성 설정할 VSPackage의 기본 소스 제어에 대 한 활성 상태 였던 VSPackage 소스 제어 사용자가 닫힙니다.  
  
 이전 버전과 달리 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], IDE 다시 시작 되는 소스 제어 Vspackage를 전환 하려면 유일한 방법은 더 이상. 자동으로 VSPackage 선택이 됩니다. 패키지를 전환 합니다. Windows 사용자 권한 (관리자 또는 고급 사용자)이 필요 합니다.  
  
## <a name="see-also"></a>참고 항목  
 <xref:Microsoft.VisualStudio.Shell.Interop.IVsSolutionPersistence>   
 [기능](../../extensibility/internals/source-control-vspackage-features.md)   
 [소스 제어 플러그 인 만들기](../../extensibility/internals/creating-a-source-control-plug-in.md)   
 [VSPackage](../../extensibility/internals/vspackages.md)