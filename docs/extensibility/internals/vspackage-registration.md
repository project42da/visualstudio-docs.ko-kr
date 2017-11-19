---
title: "VSPackage 등록 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- registration, VSPackages
- VSPackages, registering
ms.assetid: ecd20da8-b04b-4141-a8f4-a2ef91dd597a
caps.latest.revision: "18"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.openlocfilehash: 263e2adf69aa479974a07dbb2acc2d4cd8f2a0dd
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="vspackage-registration"></a>VSPackage 등록
Vspackage 조언을 해야 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 은 설치 되어 있고 해야 로드할 수 있습니다. 이 프로세스는 레지스트리에서 정보를 작성 하 여 수행 됩니다. 설치 관리자의 일반적인 작업입니다.  
  
> [!NOTE]
>  VSPackage 개발 자체 등록을 사용 하는 동안이 허용 되는 좋습니다. 그러나 [!INCLUDE[vsipprvsip](../../extensibility/includes/vsipprvsip_md.md)] 파트너 설치의 일부로 자체 등록을 사용 하 여 해당 제품을 제공할 수 없습니다.  
  
 Windows Installer 패키지에 대 한 레지스트리 항목 레지스트리 테이블에서 일반적으로 수행 됩니다. 또한 레지스트리 테이블의 파일 확장명을 등록할 수 있습니다. 그러나 Windows Installer ProgId (프로그래밍 id), 클래스, 확장명 및 동사 테이블을 통해 기본 제공 지원을 제공합니다. 자세한 내용은 참조 [데이터베이스 테이블](http://msdn.microsoft.com/library/aa368259\(VS.85\).aspx)합니다.  
  
 레지스트리 항목은 선택한-나란히 전략을 적절 한 구성 요소와 연결 해야 합니다. 예를 들어, 공유 파일에 대 한 레지스트리 항목은 해당 파일의 Windows Installer 구성 요소와 연결 해야 합니다. 마찬가지로, 버전별 파일에 대 한 레지스트리 항목은 해당 파일의 구성 요소와 연결 해야 합니다. 그렇지 않은 경우 설치 또는 제거 VSPackage의 특정 버전에 대해 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 다른 버전에서는 VSPackage를 손상 시킬 수 있습니다. 자세한 내용은 참조 [Visual Studio의 여러 버전을 지 원하는](../../extensibility/supporting-multiple-versions-of-visual-studio.md)  
  
> [!NOTE]
>  등록을 관리 하는 가장 쉬운 방법은 개발자 등록 및 설치 시 등록에 대 한 동일한 파일에 동일한 데이터를 사용 하는 것입니다. 예를 들어 일부 설치 관리자 개발 도구는 빌드 시 형식의.reg 파일을 사용할 수 있습니다. 개발자가 자신의 일상 개발을 위한.reg 파일을 유지 하 고 디버깅을 동일한 파일 수는 설치 관리자에 자동으로 포함 합니다. 자동으로 등록 데이터를 공유할 수 없습니다, 설치 프로그램의 사본을 등록 데이터를 최신 확인 해야 합니다.  
  
## <a name="registering-unmanaged-vspackages"></a>관리 되지 않는 Vspackage를 등록 하는 중  
 (Visual Studio 패키지 템플릿을에서 생성 된 항목 포함)는 관리 되지 않는 Vspackage ATL 스타일.rgs 파일을 사용 하 여 등록 정보를 저장 합니다. .Rgs 파일 형식은 ATL에 특정 하며로 일반적으로 사용 될 수 없습니다-제작 도구는 설치 하는 것입니다. VSPackage 설치 관리자에 대 한 등록 정보를 별도로 유지 되어야 합니다. 예를 들어 개발자가 파일을 보관할 수.reg 형태로 표시.rgs 동기화 파일 변경. .Reg 파일을 개발 작업에 대 한 RegEdit와 병합 또는 설치 관리자에서 사용할 수 있습니다.  
  
## <a name="registering-managed-vspackages"></a>관리 되는 Vspackage를 등록 하는 중  
 RegPkg 도구는 등록 특성을 관리 되는 VSPackage에서 읽고 하거나 정보를 쓸 수는 레지스트리 또는 설치 프로그램을 통해 사용할 수 있는 쓰기.reg 서식 파일에 직접 합니다.  
  
> [!NOTE]
>  RegPkg 도구 재배포 가능 패키지는 및 사용자의 시스템에 VSPackage를 등록 하는 데 사용할 수 없습니다.  
  
## <a name="why-vspackages-should-not-self-register-at-install-time"></a>이유 Vspackage 등록 하지 않아야 자체 설치 중에  
 VSPackage 설치 관리자 자체 등록 되지는지 않습니다. 얼핏 보기에 자체 VSPackage에서에서 VSPackage의 레지스트리 값을 유지 같아는 것이 좋습니다. 개발자가 일상적인 작업을 위해 사용할 수 있는 레지스트리 값이 필요 하 고 테스트 하는 것 별도 설치 관리자에서 레지스트리 데이터의 복사본을 유지 관리 하지 않아도 제공 합니다. 설치 관리자 사용 VSPackage 자체 레지스트리 값을 쓸 수 있습니다.  
  
 이론적으로 확인 된, 하는 동안 자체 등록에 사용할 수 없는 VSPackage 설치 하는 몇 가지 결점이 있습니다.  
  
-   올바르게 설치, 제거, 설치 롤백 및 지원 제거 롤백 RegPkg를 호출 하 여 셀프 등록 하는 모든 관리 되는 VSPackage에 대 한 4 개의 사용자 지정 작업을 제작 하는 데 필요 합니다.  
  
-   네 번째 사용자 지정 작업 RegSvr32 또는 RegPkg의 지원 되는 모든 버전에 대 한 호출을 제작 하는 프로그램-병렬 지원에 접근 필요할 수 있습니다 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다.  
  
-   다른 기능 또는 응용 프로그램에서 자동으로 등록된 키가 사용 됩니다 하는 경우 보면서의 방법이 있으면 서 자체 등록 된 모듈을 설치 안전 하 게 롤백할 수 없습니다.  
  
-   셀프 등록 된 Dll 경우가 존재 하지 않거나 잘못 된 버전 보조 Dll에 연결 합니다. 반면, Windows Installer는 시스템의 현재 상태에 의존 하지 않고 레지스트리 테이블을 사용 하 여 Dll을 등록할 수 있습니다.  
  
-   형식 라이브러리와 같은 네트워크 리소스에 대 한 액세스 구성 요소가 모두 소스에서 실행으로 지정 하 고 SelfReg 표에 나와 자동 등록 코드를 정의할 수 있습니다. 이 인해 관리자는 설치 중에 실패 하는 구성 요소 설치 수 있습니다.  
  
## <a name="see-also"></a>참고 항목  
 [Windows Installer](http://msdn.microsoft.com/library/cc185688\(VS.85\).aspx)   
 [관리 되는 패키지 등록](http://msdn.microsoft.com/en-us/f69e0ea3-6a92-4639-8ca9-4c9c210e58a1)