---
title: "설치 후 실행 해야 하는 명령 | Microsoft Docs"
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
  - "설치 후 명령"
ms.assetid: c9601f2e-2c6e-4da9-9a6e-e707319b39e2
caps.latest.revision: 22
caps.handback.revision: 22
ms.author: "gregvanl"
manager: "ghogen"
---
# 설치 후 실행 해야 하는 명령
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

.Msi 파일을 통해 확장 프로그램을 배포 하는 경우 실행 해야 `devenv /setup` for Visual Studio 확장 프로그램을 검색 하는 순서 대로 설치의 일부로 합니다.  
  
> [!NOTE]
>  이 항목의 정보 찾기 DevEnv Visual Studio 2008 및 이전 버전에 적용 됩니다. 이상 버전의 Visual Studio와 DevEnv를 검색 하는 방법에 대 한 정보를 참조 하십시오. [시스템 요구 사항 검색](../../extensibility/internals/detecting-system-requirements.md)합니다.  
  
## Devenv.exe 찾기  
 각 버전을 찾을 수 있습니다 레지스트리에서 devenv.exe 값 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 설치 관리자를 사용 하 여 쓸 RegLocator 테이블과 AppSearch 테이블 속성으로 레지스트리 값을 저장할 수 있습니다. 자세한 내용은 [시스템 요구 사항 검색](../../extensibility/internals/detecting-system-requirements.md)을 참조하세요.  
  
### 서로 다른 버전의 Visual Studio의 devenv.exe를 찾으려고 RegLocator 테이블 행  
  
|Signature\_|루트|키|이름|형식|  
|-----------------|--------|-------|--------|--------|  
|RL\_DevenvExe\_2002|2|SOFTWARE\\Microsoft\\VisualStudio\\7.0\\Setup\\VS|EnvironmentPath|2|  
|RL\_DevenvExe\_2003|2|SOFTWARE\\Microsoft\\VisualStudio\\7.1\\Setup\\VS|EnvironmentPath|2|  
|RL\_DevenvExe\_2005|2|SOFTWARE\\Microsoft\\VisualStudio\\8.0\\Setup\\VS|EnvironmentPath|2|  
|RL\_DevenvExe\_2008|2|SOFTWARE\\Microsoft\\VisualStudio\\9.0\\Setup\\VS|EnvironmentPath|2|  
  
### 해당 RegLocator 테이블 행에 대 한 AppSearch 테이블 행  
  
|속성|Signature\_|  
|--------|-----------------|  
|DEVENV\_EXE\_2002|RL\_DevenvExe\_2002|  
|DEVENV\_EXE\_2003|RL\_DevenvExe\_2003|  
|DEVENV\_EXE\_2005|RL\_DevenvExe\_2005|  
|DEVENV\_EXE\_2008|RL\_DevenvExe\_2008|  
  
 Visual Studio 설치 관리자에서 레지스트리 값을 작성 하는 예를 들어 **HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\VisualStudio\\9.0\\Setup\\VS\\EnvironmentPath** 으로 **C:\\VS2008\\Common7\\IDE\\devenv.exe**, 설치 관리자를 실행 해야 하는 실행 파일에 전체 경로입니다.  
  
 **참고** RegLocator 유형 열 2 이기 때문에 필요는 없습니다 서명 테이블에 추가 버전 정보를 지정할 수 있습니다.  
  
## Devenv.exe를 실행합니다.  
 설치 관리자에서 실행 되는 표준 작업 AppSearch, AppSearch 테이블의 각 속성에 대 한 해당 버전의 Visual Studio devenv.exe 파일을 가리키는 값을 있습니다. 하는 경우 지정 된 레지스트리 값이 하나라도 없는\-해당 버전의 Visual Studio가 설치 되어 있지 않으므로\-지정 된 속성은 null로 합니다.  
  
 사용자 지정 동작을 통해 속성을 가리키는 실행 파일을 실행 하는 Windows Installer 지원 50을 입력 합니다. 사용자 지정 작업 스크립트의 실행 옵션, msidbCustomActionTypeInScript \(1024\) 및 \(512\) msidbCustomActionTypeCommit VSPackage에 통합 하기 전에 제대로 설치 되었는지 확인 포함 해야 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다. 자세한 내용은 CustomAction 테이블 및 사용자 지정 작업에서 스크립트 실행 옵션을 참조 하십시오.  
  
 50 형식의 사용자 지정 동작 실행 파일의 원본 열과 대상 열에 명령줄 인수 값으로 포함 된 속성을 지정 합니다.  
  
### Devenv.exe를 실행 하는 CustomAction 테이블 행  
  
|작업|형식|소스|대상|  
|--------|--------|--------|--------|  
|CA\_RunDevenv2002|1586|DEVENV\_EXE\_2002|\/setup|  
|CA\_RunDevenv2003|1586|DEVENV\_EXE\_2003|\/setup|  
|CA\_RunDevenv2005|1586|DEVENV\_EXE\_2005|\/setup|  
|CA\_RunDevenv2008|1586|DEVENV\_EXE\_2008|\/setup|  
  
 설치 하는 동안 실행 하도록 일정을 잡는 InstallExecuteSequence 테이블에 사용자 지정 작업을 작성 해야 합니다. 조건 열의 각 행의 해당 속성을 사용 하 여 해당 실행 되지 않도록 사용자 지정 동작을 방지 하기 위해 버전의 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 시스템에 설치 되지 않았습니다.  
  
> [!NOTE]
>  `Null` 속성으로 계산 `False` 조건에서 사용 하는 경우.  
  
 각 사용자 지정 동작에 대 한 시퀀스 열의 값을 Windows Installer 패키지에 다른 시퀀스 값에 따라 달라 집니다. 시퀀스 값 InstallFinalize 표준 작업 직전에 가능한 닫습니다 devenv.exe 사용자 지정 작업으로 실행 되도록 해야 합니다.  
  
### InstallExecuteSequence 테이블 devenv.exe 사용자 지정 동작을 예약 하려면  
  
|작업|조건|Sequence|  
|--------|--------|--------------|  
|CA\_RunDevenv2002|DEVENV\_EXE\_2002|6602|  
|CA\_RunDevenv2003|DEVENV\_EXE\_2003|6603|  
|CA\_RunDevenv2005|DEVENV\_EXE\_2005|6605|  
|CA\_RunDevenv2008|DEVENV\_EXE\_2008|6608|  
  
## 참고 항목  
 [Windows Installer를 사용 하 여 Vspackage를 설치](../../extensibility/internals/installing-vspackages-with-windows-installer.md)