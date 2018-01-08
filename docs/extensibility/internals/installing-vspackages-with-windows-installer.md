---
title: "Windows Installer를 사용 하 여 Vspackage 설치 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- installation [Visual Studio SDK], with Windows Installer
- VSPackages, deploying
ms.assetid: 41d2c72c-0a97-4fcd-b3aa-33a8d3aa962a
caps.latest.revision: "30"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: a9f4d45c3fccebed9febc2ea722981f597896ace
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="installing-vspackages-with-windows-installer"></a>Windows Installer를 사용 하 여 Vspackage 설치
VSPackage에 통합 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 것 이상의 사용자의 컴퓨터에 파일을 복사 해야 합니다. VSPackage의 설치 관리자는 VSPackage 및 해당 종속 파일을 설치 하 고을 등록 하 고로 통합 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다. VSPackage에 아이콘을 표시 하는 등 통합 기능을 이용할 수는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 화면 및 정보 대화 상자를 시작 합니다.  
  
 Microsoft Windows Installer 파일은 사용자 Vspackage를 배포 하는 것이 좋습니다. 사용 하기 쉬운 Windows Installer 패키지에서 지 원하는 모든 Windows 운영 체제에서 실행할 수 있습니다 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다. 자세한 내용은 참조 [Windows Installer](http://msdn.microsoft.com/en-us/121be21b-b916-43e2-8f10-8b080516d2a0)합니다.  
  
## <a name="in-this-section"></a>섹션 내용  
 [Windows Installer 기본 사항](../../extensibility/internals/windows-installer-basics.md)  
 Windows Installer에 대 한 개요를 제공합니다.  
  
 [VSPackage 설치 시나리오](../../extensibility/internals/vspackage-setup-scenarios.md)  
 두 사용자 Vspackage의 함께-설치를 지원할 수 있는 다양 한 방법에 설명 하 고 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다.  
  
 [Windows Installer 패키지 작성](../../extensibility/internals/authoring-a-windows-installer-package.md)  
 올바르게 설치 하 고 Vspackage에 통합 설치 관리자가 수행 하는 일반적인 단계를 간략히 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다.  
  
 [시스템 요구 사항 검색](../../extensibility/internals/detecting-system-requirements.md)  
 설치 관리자에는 검색할 수는 방법에 대해 설명 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 하 여 VSPackage 요구 사항이 충족 되지 않으면 해당 구성 요소와 취소를 설정 합니다.  
  
 [구성 요소 관리](../../extensibility/internals/component-management.md)  
 이전 제품 버전의 무결성이 유지 되도록 하는 설치 관리자를 개발 하는 방법에 설명 합니다.  
  
 [VSPackage용 설치 디렉터리 선택](../../extensibility/internals/choosing-the-installation-directory-for-a-vspackage.md)  
 Vspackage를 찾기 위한 옵션을 요약 합니다.  
  
 [VSPackage 등록](../../extensibility/internals/vspackage-registration.md)  
 Vspackage는 설치 중에 등록 하는 방법을 설명 하 고 이유 자체 등록 것이 바람직합니다.  
  
 [프로젝트 형식 배포](../../extensibility/internals/deploying-project-types.md)  
 관리 코드 프로젝트 형식에 대 한 새 프로젝트 형식 집계를 사용 하는 방법을 설명 합니다.  
  
 [방법: 설치 관리자에 대한 레지스트리 정보 생성](../../extensibility/internals/how-to-generate-registry-information-for-an-installer.md)  
 관리 되는 VSPackage에 대 한 등록 매니페스트를 생성 하 RegPkg.exe를 사용 하는 방법에 설명 합니다.  
  
 [설치 후 실행해야 하는 명령](../../extensibility/internals/commands-that-must-be-run-after-installation.md)  
 설치 후에 Vspackage를 통합 하는 명령을 실행 하는 방법에 설명 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)]합니다.  
  
 [Windows Installer를 사용하여 VSPackage 제거](../../extensibility/internals/uninstalling-a-vspackage-with-windows-installer.md)  
 설치 관리자는 사용자가 VSPackage를 제거 하는 경우 수행 해야 하는 단계를 설명 합니다.  