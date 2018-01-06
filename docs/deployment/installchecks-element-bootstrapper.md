---
title: "&lt;InstallChecks&gt; 요소 (부트스트래퍼) | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-deployment
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- FSharp
- VB
- CSharp
- C++
helpviewer_keywords: <InstallChecks> element [bootstrapper]
ms.assetid: ad329c87-b0ad-4304-84de-ae9496514c42
caps.latest.revision: "23"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.workload: multiple
ms.openlocfilehash: 787134277f27e901c6afe6a8e9c41d224431a122
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="ltinstallchecksgt-element-bootstrapper"></a>&lt;InstallChecks&gt; 요소 (부트스트래퍼)
`InstallChecks` 요소에서 다양 한 응용 프로그램에 대 한 필수 구성 요소가 모두 설치 되었는지 확인 하려면 로컬 컴퓨터에 대 한 테스트를 지원 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
<InstallChecks>  
    <AssemblyCheck   
        Property  
        Name  
        PublicKeyToken  
        Version  
        Language  
        ProcessorArchitecture  
    />  
    <RegistryCheck  
        Property  
        Key  
        Value  
    />  
    <ExternalCheck   
        PackageFile  
        Property  
        Arguments  
    />  
    <FileCheck   
        Property  
        FileName  
        SearchPath  
        SpecialFolder  
        SearchDepth  
    />  
    <MsiProductCheck   
        Property  
        Product  
        Feature  
    />  
    <RegistryFileCheck   
        Property  
        Key  
        Value  
        FileName  
        SearchDepth  
    />  
</InstallChecks>  
```  
  
## <a name="assemblycheck"></a>AssemblyCheck  
 이 요소는의 선택적 자식 요소 `InstallChecks`합니다. 각 인스턴스에 대해 `AssemblyCheck`, 부트스트래퍼 요소로 식별 된 어셈블리를 전역 어셈블리 캐시 (GAC)에 있는지 확인 합니다. 요소를 포함 하지 하 고 다음과 같은 특성이 있습니다.  
  
|특성|설명|  
|---------------|-----------------|  
|`Property`|필수. 결과 저장 하는 속성의 이름입니다. 아래의 테스트에서이 속성을 참조할 수 있습니다는 `InstallConditions` 자식 요소인의는 `Command` 요소입니다. 자세한 내용은 참조 [ \<명령 > 요소](../deployment/commands-element-bootstrapper.md)합니다.|  
|`Name`|필수. 확인할 어셈블리의 정규화 된 이름입니다.|  
|`PublicKeyToken`|필수. 강력한 이름의 어셈블리와 연결 된 공개 키의 간략된 한 형태입니다. GAC에 저장 된 모든 어셈블리는 이름, 버전, 및 공개 키에 있어야 합니다.|  
|`Version`|필수. 어셈블리의 버전입니다.<br /><br /> 버전 번호의 형식은 \< *주 버전*>.\< *부 버전*>.\< *빌드 버전*>.\< *수정 버전*> 합니다.|  
|`Language`|선택 사항입니다. 지역화 된 어셈블리의 언어입니다. 기본값은 `neutral`입니다.|  
|`ProcessorArchitecture`|선택 사항입니다. 이 설치에서 대상 컴퓨터 프로세서입니다. 기본값은 `msil`입니다.|  
  
## <a name="externalcheck"></a>ExternalCheck  
 이 요소는의 선택적 자식 요소 `InstallChecks`합니다. 각 인스턴스에 대해 `ExternalCheck`, 부트스트래퍼 별도 프로세스에서 명명된 된 외부 프로그램 실행을 가리키는 속성에서 종료 코드를 저장 `Property`합니다. `ExternalCheck`복잡 한 종속성 확인을 구현 하기 위한 또는 구성 요소가 있는지 확인 하는 유일한 방법은를 인스턴스화해야 하는 경우 유용 합니다.  
  
 `ExternalCheck`요소를 포함 하지 하 고 다음과 같은 특성이 있습니다.  
  
|특성|설명|  
|---------------|-----------------|  
|`Property`|필수. 결과 저장 하는 속성의 이름입니다. 아래의 테스트에서이 속성을 참조할 수 있습니다는 `InstallConditions` 자식 요소인의는 `Command` 요소입니다. 자세한 내용은 참조 [ \<명령 > 요소](../deployment/commands-element-bootstrapper.md)합니다.|  
|`PackageFile`|필수. 외부 프로그램을 실행 하도록 합니다. 프로그램은 설치 배포 패키지의 일부 여야 합니다.|  
|`Arguments`|선택 사항입니다. 명명 된 실행 파일에 명령줄 인수 제공 `PackageFile`합니다.|  
  
## <a name="filecheck"></a>체크  
 이 요소는의 선택적 자식 요소 `InstallChecks`합니다. 각 인스턴스에 대해 `FileCheck`, 부트스트래퍼는 있는지 확인 명명된 된 파일이 있는 파일의 버전 번호를 반환 합니다. 부트스트래퍼에서 명명 한 속성 설정 파일에 버전 번호를 찾을 수 없는 경우 `Property` 0입니다. 파일이 없으면 `Property` 값으로 설정 되지 않았습니다.  
  
 `FileCheck`요소를 포함 하지 하 고 다음과 같은 특성이 있습니다.  
  
|특성|설명|  
|---------------|-----------------|  
|`Property`|필수. 결과 저장 하는 속성의 이름입니다. 아래의 테스트에서이 속성을 참조할 수 있습니다는 `InstallConditions` 자식 요소인의는 `Command` 요소입니다. 자세한 내용은 참조 [ \<명령 > 요소](../deployment/commands-element-bootstrapper.md)합니다.|  
|`FileName`|필수. 찾으려는 파일의 이름입니다.|  
|`SearchPath`|필수. 디스크 또는 폴더의 파일을 검색 합니다. 경우 상대 경로 여야 합니다 `SpecialFolder` 할당 됩니다; 그렇지 않은 경우 절대 경로 여야 합니다.|  
|`SpecialFolder`|선택 사항입니다. Windows 또는 특별 한 의미가 있는 폴더 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]합니다. 기본값은 해석를 `SearchPath` 절대 경로로 합니다. 유효한 값은 다음과 같습니다.<br /><br /> `AppDataFolder`. 이 응용 프로그램 데이터 폴더 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램; 현재 사용자에 게 적용 합니다.<br /><br /> `CommonAppDataFolder`. 모든 사용자가 사용 되는 응용 프로그램 데이터 폴더.<br /><br /> `CommonFilesFolder`. 현재 사용자에 대 한 일반적인 파일 폴더입니다.<br /><br /> `LocalDataAppFolder`. 고정 된 응용 프로그램 데이터 폴더입니다.<br /><br /> `ProgramFilesFolder`. 32 비트 응용 프로그램에 대 한 표준 Program Files 폴더를 지정 합니다.<br /><br /> `StartUpFolder`. 시스템 시작 시 시작 하는 모든 응용 프로그램이 포함 된 폴더입니다.<br /><br /> `SystemFolder`. 32 비트 시스템 Dll을 포함 하는 폴더입니다.<br /><br /> `WindowsFolder`. Windows 시스템 설치가 포함 되어 있는 폴더입니다.<br /><br /> `WindowsVolume`. 드라이브나 Windows 시스템 설치를 포함 하는 파티션입니다.|  
|`SearchDepth`|선택 사항입니다. 명명된 된 파일에 대 한 하위 폴더를 검색 하는 깊이입니다. 검색은 깊이 우선 합니다. 기본값은 0으로 지정 된 최상위 폴더에 검색을 제한 하는 `SpecialFolder` 및 **SearchPath**합니다.|  
  
## <a name="msiproductcheck"></a>MsiProductCheck  
 이 요소는의 선택적 자식 요소 `InstallChecks`합니다. 각 인스턴스에 대해 `MsiProductCheck`, 부트스트래퍼 확인 완료 될 때까지 지정 된 Microsoft Windows Installer 설치에 실행 되는지 확인 합니다. 속성 값이 설치 된 해당 제품의 상태에 따라 설정 됩니다. 제품이 설치 된 양수 값 이면 0 또는-1을 설치 하지 않은 나타냅니다. (자세한 내용은 Windows Installer SDK 함수 MsiQueryFeatureState을 참조 하십시오.) . Windows Installer는 컴퓨터에 설치 되지 않은 경우 `Property` 설정 되지 않았습니다.  
  
 `MsiProductCheck`요소를 포함 하지 하 고 다음과 같은 특성이 있습니다.  
  
|특성|설명|  
|---------------|-----------------|  
|`Property`|필수. 결과 저장 하는 속성의 이름입니다. 아래의 테스트에서이 속성을 참조할 수 있습니다는 `InstallConditions` 자식 요소인의는 `Command` 요소입니다. 자세한 내용은 참조 [ \<명령 > 요소](../deployment/commands-element-bootstrapper.md)합니다.|  
|`Product`|필수. 설치 된 제품에 대 한 GUID입니다.|  
|`Feature`|선택 사항입니다. 설치 된 응용 프로그램의 특정 기능에 대 한 GUID입니다.|  
  
## <a name="registrycheck"></a>RegistryCheck  
 이 요소는의 선택적 자식 요소 `InstallChecks`합니다. 각 인스턴스에 대해 `RegistryCheck`, 부트스트래퍼가 지정된 된 레지스트리 키가 있는지 또는 지정 된 값이 있는지 여부를 확인 합니다.  
  
 `RegistryCheck`요소를 포함 하지 하 고 다음과 같은 특성이 있습니다.  
  
|특성|설명|  
|---------------|-----------------|  
|`Property`|필수. 결과 저장 하는 속성의 이름입니다. 아래의 테스트에서이 속성을 참조할 수 있습니다는 `InstallConditions` 자식 요소인의는 `Command` 요소입니다. 자세한 내용은 참조 [ \<명령 > 요소](../deployment/commands-element-bootstrapper.md)합니다.|  
|`Key`|필수. 레지스트리 키의 이름입니다.|  
|`Value`|선택 사항입니다. 검색할 레지스트리 값의 이름입니다. 기본값의 텍스트를 표시 하는 것이 기본값이입니다. `Value`DWORD 또는 문자열이 이어야 합니다.|  
  
## <a name="registryfilecheck"></a>RegistryFileCheck  
 이 요소는의 선택적 자식 요소 `InstallChecks`합니다. 각 인스턴스에 대해 `RegistryFileCheck`, 부트스트래퍼는 먼저 지정된 된 레지스트리 키에서 파일의 경로 검색 하는 지정된 된 파일의 버전 검색 합니다. 레지스트리에서 값으로 지정 된 디렉터리에서 파일을 검색 하려는 경우 특히 유용 합니다.  
  
 `RegistryFileCheck`요소를 포함 하지 하 고 다음과 같은 특성이 있습니다.  
  
|특성|설명|  
|---------------|-----------------|  
|`Property`|필수. 결과 저장 하는 속성의 이름입니다. 아래의 테스트에서이 속성을 참조할 수 있습니다는 `InstallConditions` 자식 요소인의는 `Command` 요소입니다. 자세한 내용은 참조 [ \<명령 > 요소](../deployment/commands-element-bootstrapper.md)합니다.|  
|`Key`|필수. 레지스트리 키의 이름입니다. 하지 않는 한 해당 값이는 파일의 경로를으로 해석 되는 `File` 특성이 설정 되어 있습니다. 이 키가 없는 경우 `Property` 설정 되지 않았습니다.|  
|`Value`|선택 사항입니다. 검색할 레지스트리 값의 이름입니다. 기본값의 텍스트를 표시 하는 것이 기본값이입니다. `Value`문자열 이어야 합니다.|  
|`FileName`|선택 사항입니다. 파일의 이름입니다. 레지스트리 키에서 얻은 값 디렉터리 경로 간주가 지정 되며이 이름에 추가 됩니다. 지정 하지 않으면 레지스트리에서 반환 된 값 파일에 전체 경로를 가정 합니다.|  
|`SearchDepth`|선택 사항입니다. 명명된 된 파일에 대 한 하위 폴더를 검색 하는 깊이입니다. 검색은 깊이 우선 합니다. 기본값은 0으로, 레지스트리 키의 값으로 지정 된 최상위 폴더에 검색을 제한 합니다.|  
  
## <a name="remarks"></a>설명  
 아래의 요소 동안 `InstallChecks` 실행 되도록 테스트 정의 해당 실행 되지 됩니다. 테스트를 실행 하려면 만들어야 `Command` 아래의 요소는 `Commands` 요소입니다.  
  
## <a name="example"></a>예  
 다음 코드 예제는 `InstallChecks` 그대로 요소에 대 한 제품 파일에 사용 되는 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]합니다.  
  
```  
<InstallChecks>  
    <ExternalCheck Property="DotNetInstalled" PackageFile="dotnetchk.exe" />  
    <RegistryCheck Property="IEVersion" Key="HKLM\Software\Microsoft\Internet Explorer" Value="Version" />  
</InstallChecks>  
```  
  
## <a name="installconditions"></a>InstallConditions  
 때 `InstallChecks` 는 속성이 생성 평가 됩니다. 속성을 다음 사용 `InstallConditions` 패키지 해야 설치, 무시할 되거나 실패 하는지 확인 합니다. 다음 표에 `InstallConditions`:  
  
|||  
|-|-|  
|`FailIf`|있는 경우 `FailIf` 조건이 true 인 경우 패키지가 실패 합니다. 나머지 조건은 평가 되지 않습니다.|  
|`BypassIf`|있는 경우 `BypassIf` 조건이 true 인 경우 패키지 사용 되지 것입니다. 나머지 조건은 평가 되지 않습니다.|  
  
## <a name="predefined-properties"></a>미리 정의 된 속성  
 다음 표에 `BypassIf` 및 `FailIf` 요소:  
  
|속성|노트|가능한 값|  
|--------------|-----------|---------------------|  
|`Version9X`|Windows 9x X 운영 체제의 버전 번호입니다.|4.10 = Windows 98|  
|`VersionNT`|Windows NT 기반 운영 체제의 버전 번호입니다.|Major.Minor.ServicePack<br /><br /> 5.0 Windows 2000 =<br /><br /> 5.1.0 = Windows XP<br /><br /> 5.1.2 = Windows XP Professional SP2<br /><br /> 5.2.0 = Windows Server 2003|  
|`VersionNT64`|64 비트 Windows NT 기반 운영 체제의 버전 번호입니다.|위와 동일 합니다.|  
|`VersionMsi`|Windows Installer 서비스의 버전 번호입니다.|2.0 = Windows Installer 2.0|  
|`AdminUser`|사용자는 Windows NT 기반 운영 체제에 대 한 관리자 권한이 있는지 여부를 지정 합니다.|0 = 관리자 권한 없음<br /><br /> 1 = 관리자 권한|  
  
 예를 들어 Windows 95를 실행 하는 컴퓨터에 설치를 차단 하기 위해 다음과 같은 코드를 사용 하 여:  
  
```  
<!-- Block install on Windows 95 -->  
    <FailIf Property="Version9X" Compare="VersionLessThan" Value="4.10" String="InvalidPlatform"/>  
```  
  
## <a name="see-also"></a>참고 항목  
 [\<명령 > 요소](../deployment/commands-element-bootstrapper.md)   
 [제품 및 패키지 스키마 참조](../deployment/product-and-package-schema-reference.md)