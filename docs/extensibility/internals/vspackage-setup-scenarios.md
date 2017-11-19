---
title: "VSPackage 설치 시나리오 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: VSPackages, deployment considerations
ms.assetid: d2928498-f27c-46b4-a9cd-cba41fd85a10
caps.latest.revision: "21"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 2128d4c2659d7e6e389384c4bf7e133a4fb32e47
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="vspackage-setup-scenarios"></a>VSPackage 설치 시나리오
유연성을 위해 VSPackage 설치 관리자를 디자인 하는 것이 유용 합니다. 예를 들어, 보안 패치를 나중에 해제 해야 할 수 있습니다 또는 철저 한-side-by-side 버전 관리를 지원 해야 하는 비즈니스 전략을 변경할 수 있습니다.  
  
 [Visual Studio의 여러 버전을 지 원하는](../../extensibility/supporting-multiple-versions-of-visual-studio.md), 장점 및 지원-나란히 설치 문제에 대 한 읽을 수 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] VSPackage의 공유 또는 나란히 설치 합니다. 즉,-나란히 Vspackage 유연 하 게 가장의 새로운 기능을 지원 하기 위해 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다.  
  
 이 항목에서 설명 하는 시나리오만 선택 사항 아니지만 권장된 모범 사례와 표시 됩니다.  
  
## <a name="components-privacy-and-sharing"></a>구성 요소, 개인 정보 보호 및 공유  
  
##### <a name="make-your-components-independent"></a>구성 요소를 독립적으로 확인  
 식별 하 고 구성 요소를 채울 후에 할당 된 `GUID`, 구성 요소를 배포 하 고, 해당 구성을 변경할 수 없습니다. 결과 구성 요소는 새 구성 요소를 새 해야 구성 요소의 컴퍼지션을 바꾸면 `GUID`합니다. 각 구성 요소 독립적이 고 self-reliant 장치로 하 여 버전 관리 시 뛰어난 유연성 제공 되어 이러한 팩트를 제공 합니다. 구성 요소에 적용 되는 규칙에 대 한 자세한 내용은 참조 [구성 요소 코드를 변경](http://msdn.microsoft.com/library/aa367849\(VS.85\).aspx) 및 [하면 구성 요소 규칙을 구분?](http://msdn.microsoft.com/library/aa372795\(VS.85\).aspx)합니다.  
  
##### <a name="do-not-mix-shared-and-private-resources-in-a-component"></a>구성 요소에서 공유 및 전용 리소스를 혼합 하지 마십시오  
 참조 횟수는 구성 요소 수준에서 발생합니다. 따라서 하나의 구성 요소에 공유 및 전용 리소스를 혼합 하면 대상을 또한 공유 리소스를 덮어쓰지 않고 실행 파일을 같은 전용 리소스를 업데이트할 수 있습니다. 이 시나리오는 이전 버전과 호환성 문제 만들고-side-by-side 기능을 만들지 못하도록 제한 합니다.  
  
 VSPackage를 등록 하려면 레지스트리 값을 사용 하는 예를 들어는 [!INCLUDE[vsipsdk](../../extensibility/includes/vsipsdk_md.md)] 에 유지 하면 구성 요소와 VSPackage를 등록 하는 데 하나에서 별도 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다. 공유 파일 또는 레지스트리 값에는 아직 다른 구성 요소에서 이동합니다.  
  
## <a name="scenario-1-shared-vspackage"></a>시나리오 1: 공유 VSPackage  
 이 시나리오에서는 공유 VSPackage (여러 버전의 지원 단일 이진 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)])는 Windows Installer 패키지 제공 됩니다. 각 버전을 등록 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 사용자가 선택할 수 있는 기능에 의해 제어 됩니다. 또한 구분 기능에 할당 하면, 각 구성 요소를 선택할 수 있음을 개별적으로 설치 또는 제거, VSPackage의 여러 버전에 통합 하는 컨트롤에 사용자를 두면 앞 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다. (참조 [Windows Installer 기능](http://msdn.microsoft.com/library/aa372840\(VS.85\).aspx) 기능을 사용 하 여 Windows Installer 패키지에 대 한 자세한 내용은.)  
  
 ![VS 공유 VSPackage 그래픽](../../extensibility/internals/media/vs_sharedpackage.gif "VS_SharedPackage")  
공유 VSPackage 설치 관리자  
  
 그림에 나와 있는 것 처럼 공유 구성 요소는 항상 설치 Feat_Common 기능의 일부를 구성 합니다. Feat_VS2002 및 Feat_VS2003 기능을 표시 하 여 사용자가 선택할 수 설치 시의 어떤 버전으로 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 통합 하기 위해 VSPackage를 원합니다. 사용자 사용 하 여 Windows Installer 유지 관리 모드를 추가 기능에는 경우 추가 또는 제거의 서로 다른 버전의 VSPackage 등록 정보를 제거 하거나 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다.  
  
> [!NOTE]
>  각 기능의 표시 열을 0으로 설정 숨겨집니다. 예: 1, 낮은 수준의 열 값, 하면 항상 설치 됩니다. 자세한 내용은 참조 [INSTALLLEVEL 속성](http://msdn.microsoft.com/library/aa369536\(VS.85\).aspx) 및 [기능 테이블](http://msdn.microsoft.com/library/aa368585.aspx)합니다.  
  
## <a name="scenario-2-shared-vspackage-update"></a>시나리오 2: 공유 VSPackage 업데이트  
 이 시나리오에서 시나리오 1의에서 VSPackage 설치 관리자의 업데이트 된 버전이 제공 됩니다. 설명을 위해이 업데이트는에 대 한 지원을 추가 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], 간단 보안 패치 또는 버그 수정 서비스 팩 수 있지만 합니다. 최신 구성 요소 설치에 대 한 Windows Installer 규칙 변경 되지 않은 구성 요소는 시스템에 다시 복사 하지는 필요 합니다. 이 경우 버전 1.0 이미 사용 하는 시스템 업데이트 된 구성 Comp_MyVSPackage.dll 덮어쓰기 하 고 Comp_VS2005_Reg 해당 구성 요소와 Feat_VS2005 새로운 기능을 추가 하는 사용자가 됩니다.  
  
> [!CAUTION]
>  VSPackage의 여러 버전에서 공유 될 때마다 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], 이전 버전의 이전 버전과 호환성을 유지 하는 VSPackage의 후속 릴리스에서 반드시 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다. 이전 버전과 호환성을 유지할 수 없는 경우-병렬, 개인 Vspackage를 사용 해야 합니다. 자세한 내용은 참조 [Visual Studio의 여러 버전을 지 원하는](../../extensibility/supporting-multiple-versions-of-visual-studio.md)합니다.  
  
 ![VS 공유 VS 패키지 업데이트 이미지](../../extensibility/internals/media/vs_sharedpackageupdate.gif "VS_SharedPackageUpdate")  
VSPackage의 업데이트 설치 관리자를 공유합니다.  
  
 이 시나리오에서는 새 VSPackage 설치 관리자 부분적 업그레이드에 대 한 Windows Installer 지원 활용 하기 위해 제공 합니다. 사용자가 단순히 버전 1.1을 설치 하 고 버전 1.0을 업그레이드 합니다. 반면에 버전 1.0 시스템에 있을 필요는 없습니다. 동일한 설치 관리자 버전 1.0이 없는 시스템에 버전 1.1을 설치 합니다. 이런이 방식으로 부분적 업그레이드를 제공 하는 장점이 업그레이드 설치 관리자와 정품 설치 관리자를 개발 작업을 수행 하는 데 필요한 된다는 점입니다. 한 명의 설치 관리자는 두 작업 모두를 수행합니다. 보안 수정 프로그램 또는 서비스 팩을 사용할 수 대신 Windows Installer 패치 활용. 자세한 내용은 참조 [패치 적용 및 업그레이드](http://msdn.microsoft.com/library/aa370579\(VS.85\).aspx)합니다.  
  
## <a name="scenario-3-side-by-side-vspackage"></a>시나리오 3:-나란히 VSPackage  
 이 시나리오에서는 두 명의 VSPackage 설치 관리자-Visual Studio.NET 2003의 각 버전에 대해 하나씩 및 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다. 각 설치 관리자 설치 병렬 여 또는 private로 VSPackage (특히 작성 및 설치의 특정 버전에 대 한 하나 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]). 각 VSPackage 고유 구성 요소입니다. 따라서 각 처리할 수 있습니다 개별적으로 패치 또는 유지 관리를 해제 합니다. VSPackage DLL 버전 별로 이제 이기 때문에 동일한 구성 요소는 DLL로 등록 정보를 포함 하도록 안전 합니다.  
  
 ![VS 쪽 &#45; 여 &#45; 쪽 VS 패키지 그래픽](../../extensibility/internals/media/vs_sbys_package.gif "VS_SbyS_Package")  
나란히 VSPackage 설치 관리자  
  
 각 설치 관리자에는 두 명의 설치 관리자 간에 공유 되는 코드가 포함 되어 있습니다. 공유 코드 공통 위치에 설치 된 경우 두.msi 파일을 설치는 공유 코드 한 번만 설치 합니다. 두 번째 설치 관리자만 구성 요소에서 참조 횟수를 증가 시킵니다. 참조 횟수를 사용 하면는 Vspackage 중 하나를 제거 하는 경우 공유 코드는 다른 VSPackage에 대 한 유지 됩니다. 두 번째 VSPackage도 제거 되는 공유 코드 제거 됩니다.  
  
## <a name="scenario-4-side-by-side-vspackage-update"></a>시나리오 4:-나란히 VSPackage 업데이트  
 이 시나리오에서는 VSPackage에 대 한 [!INCLUDE[vsprvslong](../../code-quality/includes/vsprvslong_md.md)] 발생 하면 보안상에서 취약점 해야 할 업데이트 합니다. 시나리오 2와 같이 새 설치 위치에 이미 수정에 나오는 보안 프로그램을 배포할 수 있을 뿐만 아니라 보안 픽스를 포함 하는 기존 설치를 업데이트 하는 새.msi 파일을 만들 수 있습니다.  
  
 이 경우 VSPackage는 전역 어셈블리 캐시 (GAC)에 설치 된 관리 되는 VSPackage를입니다. 보안 픽스를 포함 하도록 다시 작성할 때 어셈블리 버전 번호의 수정 버전 번호 부분을 변경 해야 합니다. 등록 정보 새 어셈블리 버전 번호를 덮어쓰면 해당 데이터베이스는 이전 버전에 대 한 일으키는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 고정된 어셈블리를 로드 합니다.  
  
 ![VS 쪽 &#45; 여 &#45; 쪽 VS 패키지 업데이트 그래픽](../../extensibility/internals/media/vs_sbys_packageupdate.gif "VS_SbyS_PackageUpdate")  
나란히 VSPackage에 대 한 업데이트 설치 관리자  
  
 **참고** side-by-side-어셈블리의 배포에 대 한 자세한 내용은 참조 하십시오. [배포를 단순화 하 고.NET Framework와 함께 DLL 지옥 해결](http://msdn.microsoft.com/library/ms973843.aspx)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [Windows Installer](http://msdn.microsoft.com/library/cc185688\(VS.85\).aspx)   
 [여러 버전의 Visual Studio 지원](../../extensibility/supporting-multiple-versions-of-visual-studio.md)