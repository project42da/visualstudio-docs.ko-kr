---
title: "Visual Studio 2017 확장성의 주요 변경 내용 | Microsoft 문서"
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
translationtype: Machine Translation
ms.sourcegitcommit: 221f4911981deec0330f76a82c0cc8a1b968e56e
ms.openlocfilehash: 081a569fc7e38fecc8cc1ae5b0f8138ae8f25521
ms.lasthandoff: 02/22/2017

---
# <a name="changes-in-visual-studio-2017-extensibility"></a>Visual Studio 2017 확장성의 변경 내용

>**참고:** 이 설명서는 임시로 제공 되며 Visual Studio 2017 RC 릴리스를 기반으로 합니다.

Visual Studio 2017 년 된 것을 제공 하 고는 [, 가벼운 Visual Studio 설치 환경을](https://blogs.msdn.microsoft.com/visualstudio/2016/04/01/faster-leaner-visual-studio-installer) 작업 부하와 설치 된 기능을 통해 사용자에 게 선택의 폭을 제공 하는 동안 사용자 시스템에 Visual Studio의 영향을 감소 합니다. 이러한 향상 된이 기능을 지원 하려면 확장성 모델을 변경 했습니다 우리와 Visual Studio 확장성을 몇 가지 주요 변경 했습니다. 이 문서에서는 이러한 변경 내용 및 해결을 위해 수행할 수 있는 기술 세부 정보를 설명 합니다. 일부 정보가 시점에서 구현 정보 이며 나중에 변경할 수 있습니다 note 하십시오.

## <a name="changes-affecting-vsix-format-and-installation"></a>VSIX 형식 및 설치에 영향을 주는 변경 내용

VSIX v3 도입 간단한 설치 환경을 지 원하는 데 (버전 3) 형식입니다.

다음과 같은 VSIX 형식 변경

* 필수 구성 요소 설치 프로그램의 선언입니다. 간단한, 빠른 설치 Visual Studio의 약속을 전달 하는 설치 관리자 사용자에 게 더 많은 구성 옵션 이제 제공 합니다. 결과적으로, 기능 및 확장에 필요한 구성 요소 설치 확인 하려면 해당 종속성을 선언 하 확장 해야 합니다.
  * RC 버전으로 얻고 확장 설치의 일부로 사용자에 대 한 필수 구성 요소를 설치 하는 Visual Studio 2017 설치 관리자가 자동으로 제공 됩니다.
  * 사용자가 만들어지지 않은 새 VSIX v3 형식을 사용 하 여 자신의 매니페스트에서 15.0 버전을 대상으로 표시 된 경우에 확장을 설치 하려고 할 때 경고가 표시 됩니다.
* VSIX 형식에 대 한 향상 된 기능입니다. 제공 하는 [낮은 영향 설치](https://blogs.msdn.microsoft.com/visualstudio/2016/04/25/anatomy-of-a-low-impact-visual-studio-install) -나란히 설치에도 지 Visual Studio의 우리 더 이상 시스템 레지스트리로 대부분의 구성 데이터를 저장 하 고 GAC에서 어셈블리를 Visual Studio 관련 작업을 옮겼습니다. 또한 늘렸습니다 VSIX 형식 및 VSIX 설치 엔진의 기능을 일부 설치 유형에 대 한 확장을 설치 하려면 것 보다는 프로그램의 MSI 또는 EXE를 사용할 수 있습니다.

  다음과 같은 새로운 기능

  * 지정된 된 Visual Studio 인스턴스를 등록 합니다.
  * 외부 설치는 [확장 폴더](set-install-root.md)합니다.
  * 프로세서 아키텍처를 감지 합니다.
  * 언어 구분 된 언어 팩에 대 한 종속성입니다.
  * 설치를 [NGEN 지원](ngen-support.md)합니다.

## <a name="building-an-extension-for-visual-studio-2017"></a>Visual Studio 2017에 대 한 확장 프로그램을 구축

새 제작을 위한 도구 디자이너 VSIX v3 매니페스트 형식이 Visual Studio 2017에 출시 되었습니다. 문서를 참조 하십시오. [하는 방법: Visual Studio 2017를 확장성 프로젝트 마이그레이션](how-to-migrate-extensibility-projects-to-visual-studio-2017.md) 디자이너 도구를 사용 하거나 수동 업데이트는 프로젝트에 대 한 자세한 내용은 및 VSIX v3 확장을 개발 하는 매니페스트.

## <a name="change-visual-studio-user-data-path"></a>Visual Studio 사용자 데이터 경로 변경 합니다.

이전에 Visual Studio의 각 주요 릴리스를 하나만 설치할 각 컴퓨터에 존재할 수 있습니다. Visual Studio 2017-나란히 설치를 지원 하기 위해 Visual Studio 용 다중 사용자 데이터 경로 사용자의 컴퓨터에 있을 수 있습니다.

Visual Studio 설정 관리자를 사용 하 여 Visual Studio 프로세스 내에서 실행 하는 코드를 업데이트 해야 합니다. Visual Studio 프로세스 외부에서 실행 되는 코드의 특정 Visual Studio 설치 사용자 경로 찾을 수 [여기에 제공 된 지침에 따라](https://blogs.msdn.microsoft.com/heaths/2016/09/15/changes-to-visual-studio-15-setup)합니다.

## <a name="change-global-assembly-cache-gac"></a>변경: 전역 어셈블리 캐시 (GAC)

더 이상 대부분 Visual Studio core 어셈블리는 GAC에 설치 됩니다. Visual Studio 프로세스에서 실행 되는 코드에서 런타임에 필요한 어셈블리를 찾을 수 있도록 다음과 같이 변경 했습니다.

* GAC에만 설치 된 어셈블리의 경우:
  * 이러한 어셈블리는 이제 %VsFolder%\Common7\IDE 아래에 설치 된\, %VsFolder%\Common7\IDE\PublicAssemblies 또는 VsFolder%\Common7\IDE\PrivateAssemblies %입니다. 이러한 폴더를 사용 하면 Visual Studio 프로세스의 검색 경로에 속합니다.
* 비 검색 경로 및 GAC에 설치 된 어셈블리의 경우:
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
    런타임 시 Visual Studio pkgdef 하위 시스템은 병합 VsAppDataFolder%\devenv.exe.config %) (아래에 Visual Studio 프로세스의 런타임 구성 파일에 이러한 항목으로 [ `<codeBase>` ](https://msdn.microsoft.com/en-us/library/efs781xb(v=vs.110).aspx) 요소입니다. 이것이 경로 검색을 통해 검색을 방지 하므로 Visual Studio 프로세스에 어셈블리를 찾을 수 있도록 하는 권장된 방법입니다.

### <a name="reacting-to-this-breaking-change"></a>이 주요 변경에 대응

* 확장 프로그램은 Visual Studio 프로세스 내에서 실행 됩니다.
  * 코드는 Visual Studio 핵심 어셈블리를 찾을 수 됩니다.
  * .Pkgdef 파일을 사용 하 여 필요한 경우 어셈블리에 대 한 경로 지정 하는 것이 좋습니다.
* 확장 프로세스 외부의 Visual Studio 실행 하는 경우:
  * %VsFolder%\Common7\IDE 아래에서 Visual Studio 핵심 어셈블리를 찾고 하는 것이 좋습니다.\, %VsFolder%\Common7\IDE\PublicAssemblies 또는 %VsFolder%\Common7\IDE\PrivateAssemblies 구성 파일 또는 어셈블리 해결 프로그램을 사용 합니다.

## <a name="change-reduce-registry-impact"></a>변경: 레지스트리 영향을 줄이기

### <a name="global-com-registration"></a>전역 COM 등록

* 이전에 Visual Studio는 네이티브 COM 등록을 지원 하기 위해 HKEY_CLASSES_ROOT 및 HKEY_LOCAL_MACHINE 하이브에 많은 레지스트리 키를 설치 합니다. 이 영향을 제거 하려면 Visual Studio 사용 하 여 [COM 구성 요소에 대 한 등록이 필요 없는 활성화](https://msdn.microsoft.com/en-us/library/ms973913.aspx)합니다.
* 결과적으로 대부분 TLB / OLB / %ProgramFiles (x86) %\Common Files\Microsoft Shared\MSEnv 아래에 있는 DLL 파일은 더 이상 Visual Studio에서 기본적으로 설치 됩니다. 이러한 파일은 이제 해당 등록이 필요 없는 COM 매니페스트는 Visual Studio 호스트 프로세스에서 사용 된 % VsFolder % 아래 설치 됩니다.
* 결과적으로, Visual Studio COM 인터페이스에 대 한 전역 COM 등록에 의존 하는 외부 코드는이 등록을 찾을 더 이상 됩니다. Visual Studio 프로세스 내에서 실행 되는 코드에는 차이가 표시 되지 않습니다.

### <a name="visual-studio-registry"></a>Visual Studio 레지스트리

* 이전에 Visual Studio 시스템의 HKEY_LOCAL_MACHINE 및 HKEY_CURRENT_USER 하이브 Visual Studio 관련 키 아래에 많은 레지스트리 키를 설치 합니다.
  * HKLM\Software\Microsoft\VisualStudio\\**버전**: MSI 설치 관리자 및 컴퓨터별 확장에서 만든 레지스트리 키입니다.
  * HKCU\Software\Microsoft\VisualStudio\\**버전**: 사용자 고유의 설정을 저장 하는 Visual Studio에서 만든 레지스트리 키입니다.
  * HKCU\Software\Microsoft\VisualStudio\\**버전**_Config: 확장 프로그램에서.pkgdef 파일에서 위의 작업을 수행 하는 Visual Studio HKLM 키와 레지스트리 키의 복사본을 병합 합니다.
* 레지스트리에 미치는 영향을 줄이기 위해 Visual Studio 지금 사용 하는 [RegLoadAppKey](https://msdn.microsoft.com/en-us/library/windows/desktop/ms724886(v=vs.85).aspx) VsAppDataFolder%\privateregistry.bin % 아래에 있는 개인 이진 파일에 레지스트리 키를 저장 하는 함수입니다. 매우 적은 수 Visual Studio 관련 키의 시스템 레지스트리에 남아 있습니다.
* Visual Studio 프로세스 내에서 실행 되는 기존 코드의 영향을 받지 않습니다. Visual Studio HKCU Visual Studio 전용 키 아래의 모든 레지스트리 작업을 개인 레지스트리를 리디렉션합니다. 시스템 레지스트리를 사용 하 여 읽기 및 쓰기 다른 레지스트리 위치를 계속 됩니다.
* 외부 코드를 로드 하 고 Visual Studio 레지스트리 항목에 대 한이 파일에서 읽은 할 수 있습니다.

### <a name="reacting-to-this-breaking-change"></a>이 주요 변경에 대응

* 외부 코드에 대 한 COM 구성 요소에도 등록이 필요 없는 활성화를 사용 하 여 변환 되어야 합니다.
* 외부 구성 요소는 Visual Studio 위치를 찾을 수 [여기에 제공 된 지침에 따라](https://blogs.msdn.microsoft.com/heaths/2016/09/15/changes-to-visual-studio-15-setup)합니다.
* 외부 구성 요소를 사용 하는 것이 좋습니다는 [외부 Settings Manager](https://msdn.microsoft.com/en-us/library/microsoft.visualstudio.settings.externalsettingsmanager.aspx) 대신 Visual Studio 레지스트리 키에 직접 읽기/쓰기입니다.
* 여부 확장 프로그램을 사용 하는 구성 요소 수 구현한 등록을 위한 또 다른 방법은 확인 합니다. 예를 들어 디버거 확장 수 새 활용 하기 위해 [msvsmon JSON 파일 COM 등록](migrate-debugger-COM-registration.md)합니다.

## <a name="change-lightweight-solution-load"></a>간단한 솔루션 로드 변경 내용:

간단한 솔루션을 로드 (LSL)는 사용자가 서로 작업을 시작 될 때까지 완전히 프로젝트를 로드 하 여 솔루션 로드 시간을 줄입니다. 이 프로젝트는 완전히 로드 하는 것으로 가정 하는 확장 변화 시킬 수 있습니다. 참조 [Lightweight 솔루션 로드](lightweight-solution-load-extension-impact.md) 확장 영향을 받을 수와 확장 업데이트에 대 한 지침을 확인 여부를 익힐 수 있습니다.

