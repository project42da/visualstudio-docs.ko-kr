---
title: "&lt;InstallChecks&gt; 요소(부트스트래퍼) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-deployment"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "<InstallChecks> 요소[부트스트래퍼]"
ms.assetid: ad329c87-b0ad-4304-84de-ae9496514c42
caps.latest.revision: 23
caps.handback.revision: 23
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &lt;InstallChecks&gt; 요소(부트스트래퍼)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

`InstallChecks` 요소에서는 응용 프로그램에 필수 구성 요소가 모두 설치되었는지 확인하기 위해 로컬 컴퓨터에 대해 다양한 테스트를 지원합니다.  
  
## 구문  
  
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
  
## AssemblyCheck  
 이 요소는 `InstallChecks`의 선택적 자식 요소입니다.  부트스트래퍼는 `AssemblyCheck`의 각 인스턴스에 대해 요소로 식별된 어셈블리가 GAC\(전역 어셈블리 캐시\)에 있는지 확인합니다.  이 요소는 자식 요소를 포함하지 않으며 다음과 같은 특성을 가지고 있습니다.  
  
|특성|설명|  
|--------|--------|  
|`Property`|필수 요소.  결과를 저장할 속성의 이름입니다.  이 속성은 `Command` 요소의 자식인 `InstallConditions` 요소 아래의 테스트에서 참조할 수 있습니다.  자세한 내용은 [\<Commands\> 요소](../deployment/commands-element-bootstrapper.md)를 참조하십시오.|  
|`Name`|필수 요소.  검사할 어셈블리의 정규화된 이름입니다.|  
|`PublicKeyToken`|필수 요소.  이 강력한 이름의 어셈블리와 연결된 공개 키의 간략한 형태입니다.  GAC에 저장된 모든 어셈블리에는 이름, 버전 및 공개 키가 있어야 합니다.|  
|`Version`|필수 요소.  어셈블리의 버전입니다.<br /><br /> 버전 번호의 형식은 \<*major version*\>.\<*minor version*\>.\<*build version*\>.\<*revision version*\>입니다.|  
|`Language`|선택적 요소.  지역화된 어셈블리의 언어입니다.  기본값은 `neutral`입니다.|  
|`ProcessorArchitecture`|선택적 요소.  이 설치의 대상 컴퓨터 프로세서입니다.  기본값은 `msil`입니다.|  
  
## ExternalCheck  
 이 요소는 `InstallChecks`의 선택적 자식 요소입니다.  `ExternalCheck`의 각 인스턴스에 대해 부트스트래퍼는 명명된 외부 프로그램을 별도의 프로세스에서 실행되고 `Property` 의해 표시된 속성에 종료 코드를 저장합니다.  `ExternalCheck`는 복잡한 종속성 검사를 구현하려는 경우나 구성 요소가 있는지 검사하려면 이를 인스턴스화해야만 하는 경우에 유용합니다.  
  
 `ExternalCheck`는 요소를 포함하지 않으며 다음과 같은 특성을 가지고 있습니다.  
  
|특성|설명|  
|--------|--------|  
|`Property`|필수 요소.  결과를 저장할 속성의 이름입니다.  이 속성은 `Command` 요소의 자식인 `InstallConditions` 요소 아래의 테스트에서 참조할 수 있습니다.  자세한 내용은 [\<Commands\> 요소](../deployment/commands-element-bootstrapper.md)를 참조하십시오.|  
|`PackageFile`|필수 요소.  실행할 외부 프로그램입니다.  이 프로그램은 설치 배포 패키지의 일부여야 합니다.|  
|`Arguments`|선택적 요소.  `PackageFile`에서 명명한 실행 파일에 명령줄 인수를 제공합니다.|  
  
## FileCheck  
 이 요소는 `InstallChecks`의 선택적 자식 요소입니다.  부트스트래퍼는 `FileCheck`의 각 인스턴스에 대해 명명된 파일이 있는지 확인하고 파일의 버전 번호를 반환합니다.  파일에 버전 번호가 없는 경우 부트스트래퍼는 `Property`에서 명명한 속성을 0으로 설정합니다.  파일이 없으면 `Property`가 모든 값으로 설정되지 않습니다.  
  
 `FileCheck`는 요소를 포함하지 않으며 다음과 같은 특성을 가지고 있습니다.  
  
|특성|설명|  
|--------|--------|  
|`Property`|필수 요소.  결과를 저장할 속성의 이름입니다.  이 속성은 `Command` 요소의 자식인 `InstallConditions` 요소 아래의 테스트에서 참조할 수 있습니다.  자세한 내용은 [\<Commands\> 요소](../deployment/commands-element-bootstrapper.md)를 참조하십시오.|  
|`FileName`|필수 요소.  찾을 파일의 이름입니다.|  
|`SearchPath`|필수 요소.  파일을 조회할 디스크나 폴더입니다.  `SpecialFolder`가 할당된 경우 이는 상대 경로여야 하고, 그렇지 않으면 절대 경로여야 합니다.|  
|`SpecialFolder`|선택적 요소.  Windows나 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)]에 특히 중요한 폴더입니다.  기본적으로는 `SearchPath`를 절대 경로로 해석합니다.  사용할 수 있는 값은 다음과 같습니다.<br /><br /> `AppDataFolder`.  이 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램에 대한 응용 프로그램 데이터 폴더입니다. 현재 사용자에게 적용됩니다.<br /><br /> `CommonAppDataFolder`.  모든 사용자가 사용하는 응용 프로그램 데이터 폴더입니다.<br /><br /> `CommonFilesFolder`.  현재 사용자에 대한 공통 파일 폴더입니다.<br /><br /> `LocalDataAppFolder`.  로밍되지 않는 응용 프로그램에 대한 데이터 폴더입니다.<br /><br /> `ProgramFilesFolder`.  32비트 응용 프로그램에 대한 표준 프로그램 파일 폴더입니다.<br /><br /> `StartUpFolder`.  시스템을 시작할 때 함께 시작하는 모든 응용 프로그램이 들어 있는 폴더입니다.<br /><br /> `SystemFolder`.  32비트 시스템 DLL이 들어 있는 폴더입니다.<br /><br /> `WindowsFolder`.  Windows 시스템 설치 항목이 들어 있는 폴더입니다.<br /><br /> `WindowsVolume`.  Windows 시스템 설치 항목이 들어 있는 드라이브나 파티션입니다.|  
|`SearchDepth`|선택적 요소.  명명된 파일에 대한 하위 폴더를 검색할 수준입니다.  검색은 깊이 우선 방식입니다.  기본값은 `SpecialFolder` 및 **SearchPath**에서 지정한 최상위 폴더만 검색하도록 제한하는 0입니다.|  
  
## MsiProductCheck  
 이 요소는 `InstallChecks`의 선택적 자식 요소입니다.  부트스트래퍼는 `MsiProductCheck`의 각 인스턴스에 대해 지정된 Microsoft Windows Installer 설치가 완료되었는지 검사합니다.  속성 값은 설치된 해당 제품의 상태에 따라 설정됩니다.  양수 값은 제품이 설치되어 있음을 나타내고 0 또는 \-1은 제품이 설치되지 않았음을 나타냅니다.  자세한 내용은 Windows Installer SDK의 MsiQueryFeatureState 함수를 참조하십시오. .  컴퓨터에 Windows Installer가 설치되어 있지 않으면 `Property`가 설정되지 않습니다.  
  
 `MsiProductCheck`는 요소를 포함하지 않으며 다음과 같은 특성을 가지고 있습니다.  
  
|특성|설명|  
|--------|--------|  
|`Property`|필수 요소.  결과를 저장할 속성의 이름입니다.  이 속성은 `Command` 요소의 자식인 `InstallConditions` 요소 아래의 테스트에서 참조할 수 있습니다.  자세한 내용은 [\<Commands\> 요소](../deployment/commands-element-bootstrapper.md)를 참조하십시오.|  
|`Product`|필수 요소.  설치된 제품의 GUID입니다.|  
|`Feature`|선택적 요소.  설치된 응용 프로그램의 특수 기능에 대한 GUID입니다.|  
  
## RegistryCheck  
 이 요소는 `InstallChecks`의 선택적 자식 요소입니다.  부트스트래퍼는 `RegistryCheck`의 각 인스턴스에 대해 지정된 레지스트리 키가 있는지 확인하거나 레지스트리 키에 지정된 값이 있는지 확인합니다.  
  
 `RegistryCheck`는 요소를 포함하지 않으며 다음과 같은 특성을 가지고 있습니다.  
  
|특성|설명|  
|--------|--------|  
|`Property`|필수 요소.  결과를 저장할 속성의 이름입니다.  이 속성은 `Command` 요소의 자식인 `InstallConditions` 요소 아래의 테스트에서 참조할 수 있습니다.  자세한 내용은 [\<Commands\> 요소](../deployment/commands-element-bootstrapper.md)를 참조하십시오.|  
|`Key`|필수 요소.  레지스트리 키의 이름입니다.|  
|`Value`|선택적 요소.  검색할 레지스트리 값의 이름입니다.  기본값은 기본값의 텍스트를 반환하는 것입니다.  `Value`는 문자열 또는 DWORD여야 합니다.|  
  
## RegistryFileCheck  
 이 요소는 `InstallChecks`의 선택적 자식 요소입니다.  부트스트래퍼는 `RegistryFileCheck`의 각 인스턴스에 대해 먼저 지정한 레지스트리 키에서 파일의 경로를 검색 시도하여 특정 파일의 버전을 검색합니다.  이는 레지스트리에 값으로 지정된 디렉터리에서 파일을 조회하려는 경우에 특히 유용합니다.  
  
 `RegistryFileCheck`는 요소를 포함하지 않으며 다음과 같은 특성을 가지고 있습니다.  
  
|특성|설명|  
|--------|--------|  
|`Property`|필수 요소.  결과를 저장할 속성의 이름입니다.  이 속성은 `Command` 요소의 자식인 `InstallConditions` 요소 아래의 테스트에서 참조할 수 있습니다.  자세한 내용은 [\<Commands\> 요소](../deployment/commands-element-bootstrapper.md)를 참조하십시오.|  
|`Key`|필수 요소.  레지스트리 키의 이름입니다.  `File` 특성이 설정되어 있지 않으면 그 값이 파일의 경로로 해석됩니다.  이 키가 없으면 `Property`가 설정되지 않습니다.|  
|`Value`|선택적 요소.  검색할 레지스트리 값의 이름입니다.  기본값은 기본값의 텍스트를 반환하는 것입니다.  `Value`는 문자열이어야 합니다.|  
|`FileName`|선택적 요소.  파일의 이름입니다.  이를 지정하면 레지스트리 키에서 가져온 값이 디렉터리 경로로 간주되고 이 이름이 경로에 추가됩니다.  이를 지정하지 않으면 레지스트리에서 반환된 값이 파일의 전체 경로로 간주됩니다.|  
|`SearchDepth`|선택적 요소.  명명된 파일에 대한 하위 폴더를 검색할 수준입니다.  검색은 깊이 우선 방식입니다.  기본값은 레지스트리 키의 값으로 지정한 최상위 폴더만 검색하도록 제한하는 0입니다.|  
  
## 설명  
 `InstallChecks` 아래의 요소는 실행할 테스트를 정의하지만 테스트를 실제로 실행하지는 않습니다.  테스트를 실행하려면 `Commands` 요소 아래에 `Command` 요소를 만들어야 합니다.  
  
## 예제  
 다음 코드 예제에서는 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]에 대한 제품 파일에 사용되는 `InstallChecks` 요소를 보여 줍니다.  
  
```  
<InstallChecks>  
    <ExternalCheck Property="DotNetInstalled" PackageFile="dotnetchk.exe" />  
    <RegistryCheck Property="IEVersion" Key="HKLM\Software\Microsoft\Internet Explorer" Value="Version" />  
</InstallChecks>  
```  
  
## InstallConditions  
 `InstallChecks`가 확인되면 속성이 생성됩니다.  이러한 속성은 `InstallConditions`에서 패키지를 설치할 것인지, 건너뛸 것인지 아니면 설치를 중지할 것인지를 결정하는 데 사용됩니다.  다음 표에는 `InstallConditions` 목록이 나와 있습니다.  
  
|||  
|-|-|  
|`FailIf`|`FailIf` 조건 중 하나라도 true인 경우에는 패키지 설치가 실패하며  나머지 조건은 확인되지 않습니다.|  
|`BypassIf`|`BypassIf` 조건 중 하나라도 true인 경우에는 패키지 설치를 건너뛰며  나머지 조건은 확인되지 않습니다.|  
  
## 미리 정의된 속성  
 다음 표는 `BypassIf` 및 `FailIf` 요소를 나열합니다.  
  
|Property|참고|가능한 값|  
|--------------|--------|-----------|  
|`Version9X`|Windows 9X 운영 체제의 버전 번호입니다.|4.10 \= Windows 98|  
|`VersionNT`|Windows NT 기반 운영 체제의 버전 번호입니다.|Major.Minor.ServicePack<br /><br /> 5.0 \= Windows 2000<br /><br /> 5.1.0 \= Windows XP<br /><br /> 5.1.2 \= Windows XP Professional SP2<br /><br /> 5.2.0 \= Windows Server 2003|  
|`VersionNT64`|64비트 Windows NT 기반 운영 체제의 버전 번호입니다.|위와 같음|  
|`VersionMsi`|Windows Installer 서비스의 버전 번호입니다.|2.0 \= Windows Installer 2.0|  
|`AdminUser`|사용자에게 Windows NT 기반 운영 체제에 대한 관리자 권한이 있는지 여부를 지정합니다.|0 \= 관리자 권한 없음<br /><br /> 1 \= 관리자 권한 있음|  
  
 예를 들어 Windows 95를 실행하는 컴퓨터에 대한 설치를 차단하려면 다음과 같은 코드를 사용합니다.  
  
```  
<!-- Block install on Windows 95 -->  
    <FailIf Property="Version9X" Compare="VersionLessThan" Value="4.10" String="InvalidPlatform"/>  
```  
  
## 참고 항목  
 [\<Commands\> 요소](../deployment/commands-element-bootstrapper.md)   
 [제품 및 패키지 스키마 참조](../deployment/product-and-package-schema-reference.md)