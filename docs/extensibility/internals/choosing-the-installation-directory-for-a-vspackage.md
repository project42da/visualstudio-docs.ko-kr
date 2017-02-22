---
title: "VSPackage에 대해 설치 디렉터리를 선택합니다. | Microsoft Docs"
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
  - "Vspackage를 설치 디렉터리"
ms.assetid: 01fbbb5b-f747-446c-afe0-2a081626a945
caps.latest.revision: 17
caps.handback.revision: 17
ms.author: "gregvanl"
manager: "ghogen"
---
# VSPackage에 대해 설치 디렉터리를 선택합니다.
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

사용자의 파일 시스템에 있는 VSPackage 및 지원 파일에 있어야 합니다.  위치 인지 Vspackage를 관리 하는 또는 관리 되지 않는, 왼쪽 \/ 오른쪽 버전 지정 체계, 및 사용자 선택에 따라 달라 집니다.  
  
## 관리 되지 않는 VSPackages  
 관리 되지 않는 Vspackage를 어떤 위치에 나 설치할 수 있는 COM 서버입니다.  해당 등록 정보 위치를 정확 하 게 반영 해야 합니다.  설치 프로그램 사용자 인터페이스 \(UI\)의 하위 디렉터리로 기본 위치가 ProgramFilesFolder Windows Installer 속성을 제공 해야 합니다.  예를 들면 다음과 같습니다.  
  
 \[ProgramFilesFolder\]MyCompany\\MyVSPackageProduct\\V1.0\\  
  
 작은 부팅 파티션을 유지 하는 사용자에 맞게 기본 디렉터리를 변경 하 고 다른 볼륨에 응용 프로그램 및 도구를 설치 하는 것이 좋습니다 사용자를 허용 합니다.  
  
 버전이 있는 VSPackage 나란히 구성표를 사용 하는 경우 하위 디렉터리가 다른 버전을 저장할 수 있습니다.  예를 들면 다음과 같습니다.  
  
 \[ProgramFilesFolder\]MyCompany\\MyVSPackageProduct\\V1.0\\2002\\  
  
 \[ProgramFilesFolder\]MyCompany\\MyVSPackageProduct\\V1.0\\2003\\  
  
 \[ProgramFilesFolder\]MyCompany\\MyVSPackageProduct\\V1.0\\2005\\  
  
## 관리 되는 VSPackages  
 관리 되는 VSPackages 또한 아무 위치에 나 설치할 수 있습니다.  그러나 항상이 전역 어셈블리 캐시 \(GAC\) 어셈블리 로드 시간을 줄이기 위해에 설치 하는 것이 좋습니다.  항상 VSPackages 관리 되는 강력한 이름의 어셈블리 이므로를 GAC에 설치의 강력한 이름 서명을 확인 설치 시만 쓴다는 의미 합니다.  다른 위치에서 파일 시스템에 설치 된 강력한 이름의 어셈블리가 로드 될 때마다 확인 서명이 있어야 합니다.  관리 Vspackages를 GAC에 설치 하는 경우 regpkg 도구 사용 하 여 **\/assembly** 어셈블리의 강력한 이름을 가리키는 레지스트리 항목을 작성 하는 스위치입니다.  
  
 관리 VSPackages GAC 아닌 다른 위치에 설치한 경우 이전 디렉터리 계층 구조를 선택 하는 관리 되지 않는 Vspackages에 주어진 지시를 따릅니다.  Regpkg 도구를 사용 **\/codebase** 스위치 VSPackage 어셈블리의 경로를 가리키는 레지스트리 항목을 작성할 수 있습니다.  
  
 자세한 내용은 [Vspackage를 등록 및 등록 취소](../../extensibility/registering-and-unregistering-vspackages.md)를 참조하십시오.  
  
## 위성 Dll  
 일반적으로 위성 Dll VSPackage — 특정 로캘에 대 한 리소스를 포함 하는\-VSPackage 디렉터리의 하위 디렉터리에 있는 있습니다.  로캘 ID \(LCID\) 값으로 하위 디렉터리에 해당합니다.  
  
 [Vspackage를 관리합니다.](../../extensibility/managing-vspackages.md)위치를 제어 하는 레지스트리 항목을 나타내는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 실제로 있는 VSPackage 찾습니다 위성 DLL입니다.  그러나, [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 순서로 LCID 값에 대 한 명명 된 하위 디렉터리에 위성 DLL을 로드 하려고 합니다.  
  
1.  기본 LCID VS LCID \(예를 들어 \\ 영어의 경우 1033\)  
  
2.  기본 보조 언어와 기본 LCID입니다.  
  
3.  시스템 기본 LCID입니다.  
  
4.  기본 보조 언어를 시스템 기본 LCID입니다.  
  
5.  U.S.  영어 \(.  \\ 1033 또는.  \\0x409\)입니다.  
  
 VSPackage DLL 리소스와 SatelliteDll\\DllName 레지스트리 진입점을 포함 하는 경우 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 위의 순서 대로 로드 하도록 시도 합니다.  
  
## 참고 항목  
 [Vspackage를 공유 하 고 버전 중에서 선택](../../extensibility/choosing-between-shared-and-versioned-vspackages.md)   
 [Vspackage를 관리합니다.](../../extensibility/managing-vspackages.md)   
 [Managed Package Registration](http://msdn.microsoft.com/ko-kr/f69e0ea3-6a92-4639-8ca9-4c9c210e58a1)