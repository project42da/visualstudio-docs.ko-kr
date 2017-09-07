---
title: "Visual Studio 2017 확장성의 주요 변경 내용 | Microsoft Docs"
ms.custom: 
ms.date: 11/09/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 54d5af60-0b44-4ae1-aa57-45aa03f89f3d
caps.latest.revision: 1
author: gregvanl
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: MT
ms.sourcegitcommit: 17defdd0b96ec1c3273fc6b845af844b031a4a17
ms.openlocfilehash: ac7a99673eb4dc23dd53a46c3c93fd735325c255
ms.contentlocale: ko-kr
ms.lasthandoff: 09/06/2017

---
# <a name="changes-in-visual-studio-2017-extensibility"></a>Visual Studio 2017 확장성의 변경 내용

Visual Studio 2017와 것을 제공 하 고는 [Visual Studio 설치 경험을 더 빠르게, 간단한](https://blogs.msdn.microsoft.com/visualstudio/2016/04/01/faster-leaner-visual-studio-installer) 작업 및 기능을 통해 사용자에 게 선택의 폭을 제공 하는 동안 사용자 시스템에 대 한 Visual Studio의 영향을 줄여 주는 설치 되어 있습니다. 이러한 향상 된이 기능을 지원 하려면 확장성 모델을 변경 했습니다 우리 및 Visual Studio 확장성을 몇 가지 주요 변경 했습니다. 이 문서에서는 이러한 변경 내용 및 해결을 수행할 수 있는 작업의 기술 세부 정보에 설명 합니다. 일부 정보가 지정 시간 구현 정보 이며 나중에 변경할 수 있습니다 note 하십시오.

## <a name="changes-affecting-vsix-format-and-installation"></a>VSIX 형식 및 설치에 영향을 주는 변경 내용

VSIX v3 도입 경량 설치 환경을 지 원하는 데 (버전 3) 형식입니다.

VSIX 형식에 대 한 변경 내용은 다음과 같습니다.

* 설치 필수 구성 요소의 선언입니다. Fast-Visual Studio 설치, 경량 완성도에 배달 하려면 설치 프로그램 사용자에 게 더 많은 구성 옵션 이제 제공 합니다. 결과적으로, 기능 및 확장에 필요한 구성 요소를 설치 하려면, 해당 종속성을 선언 하 확장 해야 합니다.
  * Visual Studio 2017 설치 관리자를 획득 하 고 확장 설치의 일환으로 사용자에 대해 필요한 구성 요소 설치를 자동으로 제공 합니다.
  * 사용자가 만들어지지 않은 새 VSIX v3 형식을 사용 하 여 대상 15.0 버전으로의 매니페스트에 표시 된 경우에는 확장을 설치 하려고 할 때 경고가 표시도 됩니다.
* VSIX 형식에 대 한 향상 된 기능입니다. 제공 하는 [영향이 적은 설치](https://blogs.msdn.microsoft.com/visualstudio/2016/04/25/anatomy-of-a-low-impact-visual-studio-install) -나란히 설치에도 지 Visual Studio의 म 더 이상 시스템 레지스트리에 대부분의 구성 데이터를 저장 하 고 Visual Studio 관련 어셈블리 GAC 외부로 이동 했습니다. 또한 늘렸습니다 VSIX 형식 및 VSIX 설치 엔진의 기능 설치 유형도 확장을 설치 하지 않고는 MSI 또는 EXE를 사용할 수 있습니다.

  다음과 같은 새로운 기능

  * 지정된 된 Visual Studio 인스턴스를 등록 합니다.
  * 외부 설치는 [확장 폴더](set-install-root.md)합니다.
  * 프로세서 아키텍처를 감지 합니다.
  * 언어 구분 된 언어 팩에 대 한 종속성입니다.
  * 사용한 설치 [NGEN 지원](ngen-support.md)합니다.

## <a name="building-an-extension-for-visual-studio-2017"></a>Visual Studio 2017에 대 한 확장 프로그램을 구축

새 제작 하기 위한 도구 디자이너 VSIX v3 매니페스트 형식이 Visual Studio 2017에 출시 되었습니다. 문서를 참조 하십시오. [하는 방법: Visual Studio 2017을 확장성 프로젝트 마이그레이션](how-to-migrate-extensibility-projects-to-visual-studio-2017.md) 디자이너 도구를 사용 하거나 수동 업데이트는 프로젝트에 대 한 자세한 내용은 및 VSIX v3 확장을 개발 하는 매니페스트 합니다.

## <a name="change-visual-studio-user-data-path"></a>변경 사항: Visual Studio 사용자 데이터 경로

이전에 Visual Studio의 각 주요 릴리스에서 하나만 설치할 각 컴퓨터에 존재할 수 있습니다. Visual Studio 2017-나란히 설치를 지원 하려면 Visual Studio에 대 한 다중 사용자 데이터 경로 사용자의 컴퓨터에 있을 수 있습니다.

Visual Studio 프로세스 내에서 실행 되는 코드는 Visual Studio 설정 관리자를 사용 하도록 업데이트 되어야 합니다. Visual Studio 프로세스 외부에서 실행 되는 코드의 특정 Visual Studio 설치 사용자 경로 찾을 수 [여기에 제공 된 지침에 따라](locating-visual-studio.md)합니다.

## <a name="change-global-assembly-cache-gac"></a>변경 사항: 전역 어셈블리 캐시 (GAC)

대부분의 Visual Studio 핵심 어셈블리를 GAC에 더 이상 설치 됩니다. Visual Studio 프로세스에서 실행 되는 코드에서 런타임에 필요한 어셈블리를 찾을 수 있도록 다음과 같이 변경 했습니다.

> [!NOTE]
> [INSTALLDIR] 아래 Visual Studio의 설치 루트 디렉터리를 참조 합니다. VSIXInstaller.exe를 자동으로이 채우는 하지만 사용자 지정 배포 코드를 작성 하려면 읽으세요 [Visual Studio 찾기](locating-visual-studio.md)합니다.

* 어셈블리를 GAC에만 설치 된:
  * 이러한 어셈블리 설치 [INSTALLDIR] \Common7\IDE 이제\, [INSTALLDIR] \Common7\IDE\PublicAssemblies 또는 [INSTALLDIR] \Common7\IDE\PrivateAssemblies 합니다. 이러한 폴더는 검색 경로 Visual Studio 프로세스의 일부입니다.
* 비 검색 경로에 및를 GAC에 설치 된 어셈블리의 경우:
  * GAC에 있는 복사본은 설치 프로그램에서 제거 되었습니다.
  * 어셈블리에 대 한 코드 베이스 엔트리를 지정 하는.pkgdef 파일 추가 되었습니다.

    예:
    
    ```xml
    [$RootKey$\RuntimeConfiguration\dependentAssembly\codeBase\{UniqueGUID}]
    "name"="AssemblyName" "codeBase"="$PackageFolder$\AssemblyName.dll"
    "publicKeyToken"="Public Key Token"
    "culture"="neutral"
    "version"=15.0.0.0
    ```
    런타임 시 Visual Studio pkgdef 하위 시스템 병합 됩니다 (아래 [VSAPPDATA]\devenv.exe.config) Visual Studio 프로세스의 런타임 구성 파일에 이러한 항목으로 [ `<codeBase>` ](https://msdn.microsoft.com/en-us/library/efs781xb(v=vs.110).aspx) 요소입니다. 이 경로 검색을 통해 검색을 방지 하기 때문에 Visual Studio 프로세스에 어셈블리를 찾을 수 있도록 하는 것이 좋습니다.

### <a name="reacting-to-this-breaking-change"></a>이 주요 변경 내용에 응답

* 확장 프로그램은 Visual Studio 프로세스 내에서 실행 중인 경우:
  * 코드는 Visual Studio 핵심 어셈블리를 찾을 수 됩니다.
  * .Pkgdef 파일을 사용 하 여 필요한 경우 어셈블리에 대 한 경로 지정 하는 것이 좋습니다.
* 확장 프로그램은 Visual Studio 프로세스 외부에서 실행 되 하는 경우:
  * [INSTALLDIR] \Common7\IDE 아래에서 Visual Studio 핵심 어셈블리를 찾고 하는 것이 좋습니다.\, [INSTALLDIR] \Common7\IDE\PublicAssemblies 또는 [INSTALLDIR] \Common7\IDE\PrivateAssemblies 구성 파일이 나 어셈블리 해결 프로그램을 사용 합니다.

## <a name="change-reduce-registry-impact"></a>변경 사항: 레지스트리 영향을 감소

### <a name="global-com-registration"></a>전역 COM 등록

* 이전에 Visual Studio는 네이티브 COM 등록을 지원 하기 위해 HKEY_CLASSES_ROOT 및 HKEY_LOCAL_MACHINE 하이브에 많은 레지스트리 키를 설치 합니다. 이 영향을 제거 하려면 Visual Studio 지금 사용 하 여 [COM 구성 요소에 대 한 등록이 필요 없는 활성화](https://msdn.microsoft.com/en-us/library/ms973913.aspx)합니다.
* 결과적으로 대부분 TLB / OLB / %ProgramFiles (x86) %\Common Files\Microsoft Shared\MSEnv 아래에 있는 DLL 파일은 더 이상 Visual Studio에서 기본적으로 설치 됩니다. 이러한 파일은 이제 Visual Studio 호스트 프로세스에서 사용 하는 해당 등록이 필요 없는 COM 매니페스트를 포함 [INSTALLDIR]에서 설치 됩니다.
* 결과적으로, Visual Studio COM 인터페이스에 대 한 전역 COM 등록에 사용 하는 외부 코드는 이러한 등록을 찾을 더 이상 됩니다. Visual Studio 프로세스 내에서 실행 되는 코드에는 차이가 표시 되지 않습니다.

### <a name="visual-studio-registry"></a>Visual Studio 레지스트리

* 이전에 Visual Studio는 시스템의 HKEY_LOCAL_MACHINE 및 HKEY_CURRENT_USER 하이브의 Visual Studio 관련 키 아래에 많은 레지스트리 키를 설치 합니다.
  * HKLM\Software\Microsoft\VisualStudio\\**버전**: MSI 설치 관리자와 컴퓨터별 확장에 의해 만들어진 레지스트리 키입니다.
  * HKCU\Software\Microsoft\VisualStudio\\**버전**: 사용자 관련 설정을 저장 하는 Visual Studio에서 만든 레지스트리 키입니다.
  * HKCU\Software\Microsoft\VisualStudio\\**버전**_Config: 확장 프로그램에서.pkgdef 파일에서 위의 Visual Studio HKLM 키와 레지스트리 키의 복사본을 병합 합니다.
* 레지스트리에 미치는 영향을 줄이기 위해 Visual Studio 지금 사용 하는 [RegLoadAppKey](https://msdn.microsoft.com/en-us/library/windows/desktop/ms724886(v=vs.85).aspx) [VSAPPDATA]\privateregistry.bin 아래에 있는 개인 이진 파일에 레지스트리 키를 보관할지 함수. Visual Studio 관련 키의 매우 작은 수만 시스템 레지스트리에 남아 있습니다.
* Visual Studio 프로세스 내에서 실행 되는 기존 코드의 영향을 받지 않습니다. Visual Studio는 개인 레지스트리에 HKCU Visual Studio 관련 키 아래에 있는 모든 레지스트리 작업을 리디렉션합니다. 시스템 레지스트리를 사용 하는 읽기 및 쓰기 다른 레지스트리 위치를 계속 됩니다.
* 외부 코드는 로드 하 고 Visual Studio 레지스트리 항목에 대 한이 파일에서 읽거나 해야 합니다.

### <a name="reacting-to-this-breaking-change"></a>이 주요 변경 내용에 응답

* 외부 코드에 대 한 COM 구성 요소에도 등록이 필요 없는 활성화를 사용 하도록 변환 됩니다.
* 외부 구성 요소는 Visual Studio 위치를 찾을 수 [여기에 제공 된 지침에 따라](https://blogs.msdn.microsoft.com/heaths/2016/09/15/changes-to-visual-studio-15-setup)합니다.
* 외부 구성 요소를 사용 하는 것이 좋습니다는 [외부 설정 관리자](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.settings.externalsettingsmanager.aspx) 대신 Visual Studio의 레지스트리 키에 직접 읽기/쓰기입니다.
* 확장 프로그램을 사용 하 여 구성 요소 여부 등록에 대 한 또 다른 방법에서 구현 있을 수 있습니다를 확인 합니다. 예를 들어 디버거 확장 수 새 활용 하기 위해 [msvsmon JSON 파일 COM 등록](migrate-debugger-COM-registration.md)합니다.

## <a name="change-lightweight-solution-load"></a>변경 사항: 간단한 솔루션 로드

간단한 솔루션 로드 (LSL) 사용자가 이러한 작업을 시작 될 때까지 완전히 프로젝트를 로드 하 여 솔루션 로드 시간을 줄입니다. 이 프로젝트는 완전히 로드 된 것으로 가정 하는 확장명 변화 시킬 수 있습니다. 참조 [Lightweight 솔루션 로드](lightweight-solution-load-extension-impact.md) 여부 확장 영향을 미칠 수 있습니다 하 고 확장을 업데이트 하는 방법에 대 한 지침을 확인 합니다.

