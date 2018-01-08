---
title: "VSPackage에 대 한 설치 디렉터리를 선택 합니다. | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: VSPackages, installation directory
ms.assetid: 01fbbb5b-f747-446c-afe0-2a081626a945
caps.latest.revision: "17"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 085c3bea9b9edc726fa09dd5d7658aff4a55e568
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="choosing-the-installation-directory-for-a-vspackage"></a>VSPackage에 대 한 설치 디렉터리를 선택합니다.
VSPackage 및 해당 지원 파일 사용자의 파일 시스템에 있어야 합니다. 위치는 VSPackage는 관리 하거나 관리 되지 않는,-side-by-side 버전 관리 체계 및 사용자 선택에 따라 달라 집니다.  
  
## <a name="unmanaged-vspackages"></a>관리 되지 않는 Vspackage  
 관리 되지 않는 VSPackage는 어느 위치에 설치할 수 있는 COM 서버입니다. 등록 정보 해당 위치를 정확 하 게 반영 해야 합니다. 설치 프로그램 사용자 인터페이스 (UI)를 하위 ProgramFilesFolder Windows Installer 속성의 기본 위치를 제공 해야 합니다. 예:  
  
 [ProgramFilesFolder] MyCompany\MyVSPackageProduct\V1.0\  
  
 작은 부트 파티션을 유지 하는 사용자를 수용 하기 위해 기본 디렉터리를 변경 하 고 다른 볼륨에 응용 프로그램 및 도구를 설치 하는 것을 선호 하는 사용자 수 있어야 합니다.  
  
 나란히 체계 버전 관리 된 VSPackage를 사용 하는 경우에 서로 다른 버전을 저장할 수 하위 디렉터리를 사용할 수 있습니다. 예:  
  
 [ProgramFilesFolder] MyCompany\MyVSPackageProduct\V1.0\2002\  
  
 [ProgramFilesFolder] MyCompany\MyVSPackageProduct\V1.0\2003\  
  
 [ProgramFilesFolder] MyCompany\MyVSPackageProduct\V1.0\2005\  
  
## <a name="managed-vspackages"></a>관리되는 VSPackage  
 또한 어떤 위치에 관리 되는 Vspackage는 설치할 수 있습니다. 그러나 항상 전역 어셈블리 캐시 (GAC) 어셈블리 로드 시간을 줄이는에 설치 하는 것이 좋습니다. 관리 되는 Vspackage는 항상 강력한 이름의 어셈블리를 GAC에 설치 하 의미 설치 시에만 해당 강력한 이름 서명을 확인 약간 것 합니다. 파일 시스템의 다른 곳에 설치 하는 강력한 이름의 어셈블리를 로드할 때마다 확인 된 대리자의 시그니처가 있어야 합니다. Regpkg 도구를 사용 하 여 GAC에 관리 되는 Vspackage를 설치할 때 **/assembly** 어셈블리의 강력한 이름 가리키는 레지스트리 항목을 작성 하는 스위치입니다.  
  
 GAC 이외의 위치에 관리 되는 Vspackage를 설치 하는 경우에 디렉터리 계층 구조 선택에 대 한 관리 되지 않는 Vspackage에 대 한 지정 된 이전 지시를 따릅니다. Regpkg 도구를 사용 하 여 **/codebase** VSPackage 어셈블리의 경로를 가리키는 레지스트리 항목을 작성 하는 스위치입니다.  
  
 자세한 내용은 참조 [등록 및 등록 취소 Vspackage](../../extensibility/registering-and-unregistering-vspackages.md)합니다.  
  
## <a name="satellite-dlls"></a>위성 Dll  
 VSPackage 위성 Dll 규칙에 따라-특정 로캘에 대 한 리소스를 포함 하는-VSPackage 디렉터리의 하위 디렉터리에 있습니다. 로캘 ID (LCID) 값에 해당 하는 하위 디렉터리입니다.  
  
 [관리 Vspackage](../../extensibility/managing-vspackages.md) 레지스트리 항목 위치를 제어 나타냅니다 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 실제로 찾습니다는 VSPackage에 대 한 위성 DLL입니다. 그러나 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 다음과 같은 순서로 LCID 값에 대 한 명명 된 하위 디렉터리에 있으면 위성 DLL을 로드 하려고 합니다.  
  
1.  기본 LCID (VS LCID 영어에 대 한 예를 들어 \1033)  
  
2.  기본 LCID 기본 보조 언어입니다.  
  
3.  시스템 기본값 LCID입니다.  
  
4.  기본 하위 언어와 시스템 기본값 LCID입니다.  
  
5.  미국 영어 (. \1033 또는. \0x409).  
  
 VSPackage DLL 리소스와 SatelliteDll\DllName 레지스트리 진입점을 포함 하는 경우 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 위의 순서를 로드 하려고 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [공유 및 버전 지정 Vspackage 중에서 선택](../../extensibility/choosing-between-shared-and-versioned-vspackages.md)   
 [Vspackage를 관리합니다.](../../extensibility/managing-vspackages.md)   
 [관리 되는 패키지 등록](http://msdn.microsoft.com/en-us/f69e0ea3-6a92-4639-8ca9-4c9c210e58a1)