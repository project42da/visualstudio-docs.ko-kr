---
title: "Side by Side 파일 연결 관리 | Microsoft Docs"
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
  - "동사를 기본 설정"
ms.assetid: 9b6df3bc-d15c-4a5d-9015-948a806193b7
caps.latest.revision: 17
caps.handback.revision: 17
ms.author: "gregvanl"
manager: "ghogen"
---
# Side by Side 파일 연결 관리
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

하면 VSPackage 파일 연결을 제공 하는 경우\-병렬 설치를 처리 하는 방법을 결정 해야 특정 버전의 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 파일을 여는 호출 하지 않아야 합니다.  호환 되지 않는 파일 서식 문제가 복합입니다.  
  
 사용자가 새 버전을 기존 파일에 새 버전으로 데이터 손실 없이 로드할 수 있도록 이전 버전과 호환 될 수 있는 제품 기대 합니다.  원칙적으로 하면 VSPackage 로드 및 수 파일 형식은 이전 버전의 저장 합니다.  True가 아닌 경우 파일 형식을 VSPackage 새 버전으로 업그레이드를 제공 해야 합니다.  이전 버전에서 업그레이드 된 파일을 열 수 없습니다이 방법의 단점은 것입니다.  
  
 이 문제를 방지 하려면 파일 형식을 호환 되지 않는 될 때 확장명을 변경할 수 있습니다.  예를 들어, 확장,.mypkg10, 버전 2를 확장명을 사용할 수 있다 하면 Vspackage의 1 버전을 사용할 수 있습니다.mypkg20.  특정 파일을 여는 Vspackage이이 차이 식별 합니다.  최신 Vspackages가 이전 확장명과 연결 되는 프로그램 목록에 추가 하는 경우 사용자가 파일을 마우스 오른쪽 단추로 클릭 하 고는 최신 Vspackage를 엽니다 선택 있습니다.  이 시점 Vspackage를 파일을 새 형식으로 업그레이드 하거나 파일을 열고 있는 Vspackage의 이전 버전과 호환성을 유지 합니다 제공할 수 있습니다.  
  
> [!NOTE]
>  두이 방법을 조합할 수 있습니다.  예를 들어, 이전 파일을 로드 하 여 이전 버전과 호환성을 제공 하 고 파일 형식을 저장할 때 업그레이드를 제공 합니다.  
  
## 이 문제에 직면  
 여러 병렬 VSPackages 동일한 확장명을 사용 하려면 버전을 선택 해야 합니다 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 확장명과 연결 되어 있습니다.  두 가지 대안 다음과 같습니다.  
  
-   최신 버전의 파일을 열 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 는 사용자의 컴퓨터에 설치 합니다.  
  
     이 방법에서는 설치 관리자의 최신 버전을 확인 하는 담당 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 는 파일 연결을 기록 하는 레지스트리 항목을 포함 하 여.  Windows Installer 패키지에 최신 버전을 나타내는 속성을 설정 하는 사용자 지정 작업이 포함 될 수 있습니다 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
    > [!NOTE]
    >  이 컨텍스트에 즉, "최신" "최신 버전: 지원 되는 버전입니다." 후속 릴리스 이러한 설치 항목이 자동으로 검색 하지 않습니다 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  항목에 [시스템 요구 사항 검색](../extensibility/internals/detecting-system-requirements.md) 및 [설치 후 실행 해야 하는 명령](../extensibility/internals/commands-that-must-be-run-after-installation.md) 여기에 제시 된 것과 유사한 고의 추가 버전을 지원 해야 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  
  
     CustomAction 테이블의 다음 행 Appsearch로 설정 하는 속성에 DEVENV\_EXE\_LATEST 속성을 설정 하 고 RegLocator 테이블 설명에서 [설치 후 실행 해야 하는 명령](../extensibility/internals/commands-that-must-be-run-after-installation.md).  InstallExecuteSequence 테이블의 행에에서 시퀀스 실행 초기 단계에서 사용자 지정 작업을 예약합니다.  조건 열 설정 논리 작업 시간 값:  
  
    -   Visual Studio.만 현재 버전이 있는 경우 NET 2002 최신 버전입니다.  
  
    -   Visual Studio.NET 2003이 최신 버전이 있는 경우에 및 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 없습니다.  
  
    -   [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]만 현재 버전이 있으면 최신 버전이입니다.  
  
     DEVENV\_EXE\_LATEST 최신 버전 devenv.exe의 경로 포함 됩니다.  
  
    ### Visual Studio 최신 버전을 확인 하는 사용자 지정 작업 테이블 행  
  
    |동작|형식|소스|대상|  
    |--------|--------|--------|--------|  
    |CA\_SetDevenvLatest\_2002|51|DEVENV\_EXE\_LATEST|\[DEVENV\_EXE\_2002\]|  
    |CA\_SetDevenvLatest\_2003|51|DEVENV\_EXE\_LATEST|\[DEVENV\_EXE\_2003\]|  
    |CA\_SetDevenvLatest\_2005|51|DEVENV\_EXE\_LATEST|\[DEVENV\_EXE\_2005\]|  
  
    ### Visual Studio 최신 버전을 확인 하는 InstallExecuteSequence 테이블 행  
  
    |동작|조건|시퀀스|  
    |--------|--------|---------|  
    |CA\_SetDevenvLatest\_2002|DEVENV\_EXE\_2002 및 않습니다 \(DEVENV\_EXE\_2003 또는 DEVENV\_EXE\_2005\)|410|  
    |CA\_SetDevenvLatest\_2003|DEVENV\_EXE\_2003 및 DEVENV\_EXE\_2005 않은|420|  
    |CA\_SetDevenvLatest\_2005|DEVENV\_EXE\_2005|430|  
  
     Windows Installer 패키지 레지스트리 테이블에 DEVENV\_EXE\_LATEST 속성을 사용 하 여 중이지 쓸*ProgId*\\Shell\\Open\\Command 키의 기본 값을 "%1" \[DEVENV\_EXE\_LATEST\]  
  
-   가장 좋은 사용 가능한 VSPackage 버전에서 수행할 수 있는 공유 시작 관리자 프로그램을 실행 합니다.  
  
     개발자는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 솔루션 및 결과에서 여러 버전의 프로젝트를 여러 가지 형식의 복잡 한 요구 사항을 처리할 수 있는이 방법을 선택한 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  이 방법에는 런처 프로그램 확장명 처리기로 등록합니다.  실행 프로그램 파일을 확인 하 고 버전을 결정 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 하 여 VSPackage 해당 파일을 처리할 수 있습니다.  하면 Vspackage의 특정 버전에서 마지막으로 저장 한 파일을 열 경우 예를 들어, 실행 프로그램 해당 Vspackage에 일치 하는 버전을 시작할 수 있습니다 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)].  또한, 사용자가 항상 최신 버전을 시작 하는 실행 프로그램을 구성할 수 있습니다.  실행 프로그램 또한 파일의 형식을 업그레이드 하 게 수 있습니다.  서식 파일의 버전 번호가 포함 되어 있는 경우 하나 이상의 설치 된 VSPackages 보다 이후 버전의 파일 형식으로 경우 실행 프로그램 사용자를 알릴 수 있습니다.  
  
     실행 프로그램을 Vspackage의 모든 버전을 공유 하는 Windows Installer 구성 요소에 있어야 합니다.  이 과정은 최신 버전이 항상 설치 하 고 하면 Vspackage의 모든 버전에서 제거 될 때까지 제거 되지 않습니다 확인 합니다.  있는 VSPackage 버전을 제거 하는 경우에이 방법으로 파일 연결 및 다른 실행 프로그램 구성 요소의 레지스트리 항목 보존 됩니다.  
  
## 제거 하 고 파일 연결  
 파일 연결에 대 한 레지스트리 항목을 씁니다 있는 VSPackage 제거 파일 연결을 제거 합니다.  따라서 연결 된 프로그램이 없습니다 확장명이 있습니다.  Windows Installer "를 Vspackage를 설치할 때 추가 된 레지스트리 항목 복구 되지 않습니다".  사용자가 파일 연결 문제를 해결 하는 몇 가지 다음과 같습니다.  
  
-   앞에서 설명한 대로 공유 시작 관리자 구성 요소를 사용 합니다.  
  
-   버전에는 사용자가 파일 연결을 소유 하려는 Vspackage의 복구를 실행 하려면 사용자에 게 지시 합니다.  
  
-   적절 한 레지스트리 항목을 다시 작성 하는 별도 프로그램을 제공 합니다.  
  
-   파일 연결을 선택 하 고 손실 된 연결을 다시 사용할 수 있는 구성 옵션 페이지 또는 대화 상자를 제공 합니다.  제거 후 실행 하도록 알려 주어 야 합니다.  
  
## 참고 항목  
 [병렬 배포에 대 한 파일 이름 확장명을 등록 하는 중입니다.](../extensibility/registering-file-name-extensions-for-side-by-side-deployments.md)   
 [파일 이름 확장명에 대 한 동사를 등록 하는 중](../extensibility/registering-verbs-for-file-name-extensions.md)