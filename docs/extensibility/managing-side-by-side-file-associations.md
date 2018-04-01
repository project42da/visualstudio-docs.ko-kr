---
title: 나란히 파일 연결 관리 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: ''
ms.topic: article
helpviewer_keywords:
- verbs, setting default
ms.assetid: 9b6df3bc-d15c-4a5d-9015-948a806193b7
caps.latest.revision: 17
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload:
- vssdk
ms.openlocfilehash: 7d0a6f8ec88a49b785b771aef51dc25b5646ffda
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="managing-side-by-side-file-associations"></a>나란히 파일 연결 관리
파일 연결을 제공 하는 VSPackage를 함께-설치를 처리 하는 방법을 결정 해야 특정 버전의 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 파일을 호출 해야 합니다. 호환 되지 않는 파일 형식 복합 문제입니다.  
  
 사용자가 새 버전의 데이터 손실 없이 기존 파일을 새 버전에 로드 될 수 있도록 이전 버전과 호환 되도록 제품을 기대 합니다. 이상적으로 VSPackage 모두 로드 하 고 저장할 수 이전 버전의 파일 형식입니다. true가 아닐 경우에 파일 형식을 VSPackage의 새 버전으로 업그레이드를 제공 해야 합니다. 이 방식의 단점은 이전 버전에서 업그레이드 된 파일을 열 수 없습니다.  
  
 이 문제를 방지 하려면 파일 형식은 호환 되지 않는 경우 확장을 변경할 수 있습니다. 예를 들어 VSPackage의 버전 1 확장과.mypkg10, 버전 2 확장을 사용할 수 있습니다 사용할 수.mypkg20 합니다. 이러한 차이는 VSPackage 특정 파일을 식별 합니다. 사용자가 이전 확장명과 연결 되어 있는 프로그램의 목록에 새 Vspackage를 추가 하면 파일 단추로 클릭 하 고 새 VSPackage에서 열을 선택 합니다. 이 시점에서 VSPackage는 새 형식으로 파일을 업그레이드 하거나 파일을 열고 VSPackage의 이전 버전과 호환성을 유지 제공할 수 있습니다.  
  
> [!NOTE]
>  이러한 방법을 결합할 수 있습니다. 예를 들어 이전 파일을 로드 하 여 이전 버전과 호환성을 제공할 수 있으며 저장할 때 파일 형식을 업그레이드에 게 제공.  
  
## <a name="facing-the-problem"></a>연결 문제  
 동일한 확장을 사용 하려면 여러-나란히 Vspackage를 원하는 경우의 버전을 선택 해야 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 확장와 연결 된입니다. 다음은 두 가지 대안입니다.  
  
-   최신 버전의에서 파일을 엽니다 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 사용자의 컴퓨터에 설치 합니다.  
  
     이 방법에서 프로그램 설치 관리자 판단할 책임은 최신 버전의 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 하는 파일 연결에 대해 작성 된 레지스트리 항목에 포함 합니다. Windows Installer 패키지에서의 최신 버전을 나타내는 속성을 설정 하는 사용자 지정 작업을 포함할 수 있습니다 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]합니다.  
  
    > [!NOTE]
    >  이 컨텍스트에서 "최신" 의미 "최신 지원 되는 버전입니다." 이러한 설치 관리자 항목의 후속 릴리스를 자동으로 감지 하지 못하고 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]합니다. 항목 [시스템 요구 사항 검색](../extensibility/internals/detecting-system-requirements.md) 및 [명령을 해야 수 실행 한 후 설치](../extensibility/internals/commands-that-must-be-run-after-installation.md) 의 추가 버전을 지원 해야 하 고 여기에 제시 된 것과 비슷한 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]합니다.  
  
     사용자 지정 테이블의 다음 행은 AppSearch 설정한 속성으로 DEVENV_EXE_LATEST 속성을 설정 하 고 RegLocator 테이블에 설명 된 [명령을 해야 수 실행 한 후 설치](../extensibility/internals/commands-that-must-be-run-after-installation.md)합니다. InstallExecuteSequence 테이블의 행 초기 execute 시퀀스에에서 사용자 지정 작업을 예약합니다. 논리 작업의 조건 열 make 값:  
  
    -   Visual Studio.NET 2002은만 있는 버전인 경우 최신 버전입니다.  
  
    -   가 존재 하는 경우에 visual Studio.NET 2003은 최신 버전 및 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 나타나지 않습니다.  
  
    -   [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]만 있는 버전인 경우 최신 버전이입니다.  
  
     그 결과 DEVENV_EXE_LATEST의 최신 버전의 devenv.exe 경로 포함 합니다.  
  
    ### <a name="customaction-table-rows-that-determine-the-latest-version-of-visual-studio"></a>Visual Studio의 최신 버전을 결정 하는 사용자 지정 테이블 행  
  
    |작업|형식|소스|대상|  
    |------------|----------|------------|------------|  
    |CA_SetDevenvLatest_2002|51|DEVENV_EXE_LATEST|[DEVENV_EXE_2002]|  
    |CA_SetDevenvLatest_2003|51|DEVENV_EXE_LATEST|[DEVENV_EXE_2003]|  
    |CA_SetDevenvLatest_2005|51|DEVENV_EXE_LATEST|[DEVENV_EXE_2005]|  
  
    ### <a name="installexecutesequence-table-rows-that-determine-the-latest-version-of-visual-studio"></a>Visual Studio의 최신 버전을 결정 하는 InstallExecuteSequence 테이블 행  
  
    |작업|조건|Sequence|  
    |------------|---------------|--------------|  
    |CA_SetDevenvLatest_2002|DEVENV_EXE_2002 및 NOT (DEVENV_EXE_2003 또는 DEVENV_EXE_2005)|410|  
    |CA_SetDevenvLatest_2003|DEVENV_EXE_2003 및 DEVENV_EXE_2005 하지|420|  
    |CA_SetDevenvLatest_2005|DEVENV_EXE_2005|430|  
  
     HKEY_CLASSES_ROOT를 작성 하는 Windows Installer 패키지의 레지스트리 표에 DEVENV_EXE_LATEST 속성을 사용할 수 있습니다*ProgId*ShellOpenCommand 키의 기본값을 [DEVENV_EXE_LATEST] "%1"  
  
-   적합 하 고 사용 가능한 VSPackage 버전에서 만들 수 있는 공유 시작 프로그램을 실행 합니다.  
  
     개발자 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 여러 형식의 솔루션 및 프로젝트의 여러 버전에서 발생 하는 복잡 한 요구를 처리 하는이 방법을 선택 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]합니다. 이 방법에서는 시작 프로그램 확장 처리기로 등록합니다. 시작 관리자 파일을 검사 하 고 버전을 결정 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] VSPackage는 해당 특정 파일을 처리할 수 있습니다. 예를 들어 VSPackage의 특정 버전에서 마지막으로 저장 하는 파일을 열려고 하는 경우 시작 관리자 시작할 수는 VSPackage의 짝이 되는 버전에 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]합니다. 또한 사용자는 항상 최신 버전을 시작 하려면 시작 관리자를 구성할 수 있습니다. 또한 시작 관리자는 사용자에 게 업그레이드 파일의 형식을 요구할 수 있습니다. 파일의 형식 버전 번호를 포함 하는 경우에 시작 관리자 파일 형식을 하나 이상의 설치 된 Vspackage 보다 최신인 버전의 경우 사용자에 알릴 수 있습니다.  
  
     시작 관리자 VSPackage의 모든 버전와 공유 하는 Windows Installer 구성 요소에 있어야 합니다. 이 이렇게 하면 최신 버전은 항상 설치 하 고 VSPackage의 모든 버전에는 제거 될 때까지 제거 되지 않습니다. 이러한 방식으로 파일 연결 및 시작 관리자 구성 요소의 다른 레지스트리 항목을 하나의 고 VSPackage 버전이 제거 되는 경우에 유지 됩니다.  
  
## <a name="uninstall-and-file-associations"></a>제거 하 고 파일 연결은  
 파일 연결을 제거 파일 연결에 대 한 레지스트리 항목을 기록 하는 VSPackage를 제거 합니다. 따라서 확장 프로그램에 연결 된 프로그램이 없습니다. Windows Installer 복구 되지 않습니다 "" VSPackage를 설치할 때 추가 된 레지스트리 항목. 일부의 사용자의 파일 연결을 수정 하려면:  
  
-   앞에서 설명한 대로 시작 관리자 공유 구성 요소를 사용 합니다.  
  
-   사용자가을 파일 연결을 소유 하는 VSPackage의 버전의 복구를 실행 하도록 지시 합니다.  
  
-   적절 한 레지스트리 항목을 다시 작성 하는 별도 실행 프로그램을 제공 합니다.  
  
-   구성 옵션 페이지 또는 대화 상자가 사용자가 파일 연결을 선택 하 고 확보 손실된 연결 수를 제공 합니다. 제거 후에 실행 하는 사용자에 게 지시 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [병렬 배포를 위한 파일 이름 확장명을 등록 하는 중입니다.](../extensibility/registering-file-name-extensions-for-side-by-side-deployments.md)   
 [파일 이름 확장명에 대한 동사 등록](../extensibility/registering-verbs-for-file-name-extensions.md)