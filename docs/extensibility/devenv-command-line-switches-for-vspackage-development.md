---
title: "VSPackage 개발에 대 한 Devenv 명령줄 스위치 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "/setup 명령줄 스위치"
  - "때 명령줄 스위치"
  - "/noVSIP 명령줄 스위치"
  - "/rootsuffix 명령줄 스위치"
  - "명령줄 스위치"
  - "레지스트리, Visual Studio SDK"
  - "명령줄 스위치"
  - "Visual Studio SDK 명령줄 스위치"
ms.assetid: d65d2c04-dd84-42b0-b956-555b11f5a645
caps.latest.revision: 16
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 16
---
# VSPackage 개발에 대 한 Devenv 명령줄 스위치
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 개발자는 devenv.exe, Visual Studio 통합된 개발 환경 \(IDE\)을 시작 하는 파일을 실행할 때 명령줄에서 작업을 자동화할 수 있습니다.  
  
 작업은 다음과 같습니다.  
  
-   IDE 외부에서 미리 정의 된 구성에서 응용 프로그램을 배포 합니다.  
  
-   자동으로 기본 설정을 사용 하는 프로젝트 빌드 설정 빌드하거나 디버그 구성 합니다.  
  
-   IDE 외부 모두에서 특정 구성의 IDE를 로드 합니다. 또한 시작할 때 IDE를 사용자 지정할 수 있습니다.  
  
## 스위치에 대 한 지침  
 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 설명서에 사용자 수준 devenv 명령줄 스위치에 설명 합니다. 자세한 내용은 [Devenv 명령줄 스위치](../ide/reference/devenv-command-line-switches.md)을 참조하세요. 또한 Devenv VSPackage 개발, 배포 및 디버깅에 유용한 추가 명령줄 스위치를 지원 합니다.  
  
|명령줄 스위치|설명|  
|-------------|--------|  
|\/safemode|시작 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 안전 모드에서 기본 IDE 및 서비스를 로드 합니다. \/Safemode 스위치에서 로드 될 때 모든 타사 VSPackages 방지 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 시작 되 면 안정적으로 실행 되도록 합니다.<br /><br /> 이 스위치는 인수가 필요 없습니다.|  
|때|문제가 있는 Vspackage 로드 되지 않도록 하려는 사용자가 추가한 로드 옵션을 건너뛸 모든 지웁니다 다음 시작 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]합니다. SkipLoading 태그의 존재는 VSPackage의 로드를 해제합니다. 태그를 지우면 VSPackage의 로드를 다시 설정 합니다.<br /><br /> 이 스위치는 인수가 필요 없습니다.|  
|\/rootsuffix|시작 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 대체 위치를 사용 하 여 합니다. 다음 명령을 실행 하 여 만든 바로 가기가 [!INCLUDE[vsipsdk](../extensibility/includes/vsipsdk_md.md)] 설치 관리자:<br /><br /> devenv \/RootSuffix exp<br /><br /> 이 경우 exp 10.0 보다는 특정 접미사, 예를 들어 10.0Exp이 있는 위치를 식별합니다. 실험적 인스턴스에서 디버깅할 수 있으며의 인스턴스는 별도로 VSPackage [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 코드를 작성 하는 사용 하는 합니다.<br /><br /> 이 스위치는 VSRegEx.exe를 사용 하 여 만든 위치를 식별 하는 모든 문자열을 사용할 수 있습니다. 자세한 내용은 [실험적 인스턴스](../extensibility/the-experimental-instance.md)을 참조하세요.|  
|\/splash|표시는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 정상적으로 시작 화면 및 주요 IDE를 표시 하기 전에 메시지 상자를 표시 합니다. 메시지 상자는 VSPackage 제품 아이콘에 대 한 예를 확인 하려면 시작 화면을 학습할 수 있습니다.<br /><br /> 이 스위치는 인수가 필요 없습니다.|  
  
## 참고 항목  
 [명령줄 스위치를 추가합니다.](../extensibility/adding-command-line-switches.md)   
 [Devenv 명령줄 스위치](../ide/reference/devenv-command-line-switches.md)