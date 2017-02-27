---
title: "Windows Installer를 사용 하 여 Vspackage를 설치 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "Windows Installer를 사용 하 여 설치 [Visual Studio SDK]"
  - "Vspackage를 배포"
ms.assetid: 41d2c72c-0a97-4fcd-b3aa-33a8d3aa962a
caps.latest.revision: 30
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 30
---
# Windows Installer를 사용 하 여 Vspackage를 설치
[!INCLUDE[vs2017banner](../../code-quality/includes/vs2017banner.md)]

통합 하 여 Vspackage에 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 이외의 내용을 사용자의 컴퓨터로 파일을 복사 해야 합니다.  설치 관리자를 VSPackage 합니다 있는 VSPackage 및 해당 종속 파일을 설치 및 등록 하 고에 통합 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  하면 VSPackage 아이콘을 표시 하는 등의 통합 기능을 사용할 수 있습니다에서 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] splash 화면 및 정보 대화 상자.  
  
 Microsoft Windows Installer 파일 Vspackages를 배포 하는 권장된 방법입니다.  사용 하기 쉬운 Windows Installer 패키지에서 지 원하는 모든 Windows 운영 체제에서 실행할 수 있습니다 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  자세한 내용은 [Windows Installer](http://msdn.microsoft.com/ko-kr/121be21b-b916-43e2-8f10-8b080516d2a0)를 참조하십시오.  
  
## 단원 내용  
 [Windows Installer 기본 사항](../../extensibility/internals/windows-installer-basics.md)  
 Windows 설치 프로그램의 개요를 제공합니다.  
  
 [VSPackage 설치 시나리오](../../extensibility/internals/vspackage-setup-scenarios.md)  
 여러 가지 방법으로 모두를 Vspackages의 좌우로 나란히 설치 지원에 대해 설명 하 고 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
 [Windows Installer 패키지를 작성합니다.](../../extensibility/internals/authoring-a-windows-installer-package.md)  
 설치 관리자를 올바르게 설치 하 고 Vspackages에 통합 하는 일반적인 단계를 간략히 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
 [시스템 요구 사항 검색](../../extensibility/internals/detecting-system-requirements.md)  
 설치 관리자를 검색할 수 있습니다 하는 방법에 대해 설명 합니다 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 및 해당 구성 요소와 취소 VSPackage 요구 사항이 충족 되지 않으면 설치 합니다.  
  
 [구성 요소 관리](../../extensibility/internals/component-management.md)  
 이전 제품 버전의 무결성을 유지 하는 설치 관리자를 개발 하는 방법에 설명 합니다.  
  
 [VSPackage에 대해 설치 디렉터리를 선택합니다.](../../extensibility/internals/choosing-the-installation-directory-for-a-vspackage.md)  
 Vspackages를 찾기 옵션이 요약 되어 있습니다.  
  
 [VSPackage 등록](../../extensibility/internals/vspackage-registration.md)  
 VSPackages 설치 시에 등록 하는 방법에 대해 설명 하 고 왜 등록은 좋지 않습니다.  
  
 [배포 프로젝트 형식](../../extensibility/internals/deploying-project-types.md)  
 관리 코드 프로젝트 형식에 대 한 새 프로젝트 형식의 집계를 사용 하는 방법을 설명 합니다.  
  
 [방법: 설치 관리자에 대 한 레지스트리 정보를 생성 합니다.](../../extensibility/internals/how-to-generate-registry-information-for-an-installer.md)  
 Regpkg.exe에 대 한 관리 되는 VSPackage 등록 매니페스트를 생성 하는 방법에 설명 합니다.  
  
 [설치 후 실행 해야 하는 명령](../../extensibility/internals/commands-that-must-be-run-after-installation.md)  
 Vspackages에 통합 하는 설치 후 명령을 실행 하는 방법에 설명 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)].  
  
 [Windows Installer VSPackage를 제거합니다.](../../extensibility/internals/uninstalling-a-vspackage-with-windows-installer.md)  
 사용자 Vspackage를 제거할 때 설치 관리자가 수행 해야 하는 단계에 설명 합니다.  
  
## 관련 단원  
 [VSPackage 설치](../../misc/installing-vspackages.md)  
 빌드 및 Vspackages를 설치 하는 방법 및 여러 버전을 실행 하는 사용자를 지 원하는 방법에 설명의 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 동시에.