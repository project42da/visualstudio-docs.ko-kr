---
title: "&lt;명령&gt; 요소 (부트스트래퍼) | Microsoft Docs"
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
helpviewer_keywords: <Commands> element [bootstrapper]
ms.assetid: e61d5787-fe1f-4ebf-b0cf-0d7909be7ffb
caps.latest.revision: "13"
author: stevehoag
ms.author: shoag
manager: wpickett
ms.openlocfilehash: ac8580a1b930d4ad18db9eebb275e4eb67d80c62
ms.sourcegitcommit: aadb9588877418b8b55a5612c1d3842d4520ca4c
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/27/2017
---
# <a name="ltcommandsgt-element-bootstrapper"></a>&lt;명령&gt; 요소 (부트스트래퍼)
`Commands` 요소 아래에 설명 된 테스트를 구현 하는 `InstallChecks` 요소인 패키지를 선언 하 고는 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 부트스트래퍼 테스트가 실패 하는 경우 설치 해야 합니다.  
  
## <a name="syntax"></a>구문  
  
```  
<Commands  
    Reboot  
>  
    <Command  
        PackageFile  
        Arguments  
        EstimatedInstallSeconds  
        EstimatedDiskBytes  
        EstimatedTempBytes  
        Log  
    >  
        <InstallConditions>  
            <BypassIf   
                Property  
                Compare  
                Value  
                Schedule  
            />  
            <FailIf   
                Property  
                Compare  
                Value  
                String  
                Schedule  
            />  
        </InstallConditions>  
        <ExitCodes>  
            <ExitCode   
                Value  
                Result  
                String  
            />  
        </ExitCodes>  
    </Command>  
</Commands>  
```  
  
## <a name="elements-and-attributes"></a>요소 및 특성  
 `Commands` 요소는 필수입니다. 요소에는 다음 특성이 있습니다.  
  
|특성|설명|  
|---------------|-----------------|  
|`Reboot`|선택 사항입니다. 시스템 다시 시작 종료 코드를 반환 하는 패키지를 다시 시작 해야 하는지 여부를 결정 합니다. 다음은 유효한 값입니다.<br /><br /> `Defer`. 다시 시작 기간까지 지연 됩니다.<br /><br /> `Immediate`. 즉시 다시 시작을 하면 패키지 중 하나가 재시작 종료 코드를 반환 합니다.<br /><br /> `None`. 하면 모든 다시 시작 요청이 무시 됩니다.<br /><br /> 기본값은 `Immediate`입니다.|  
  
## <a name="command"></a>명령  
 `Command` 요소는 `Commands` 요소의 자식 요소입니다. A `Commands` 하나 이상의 요소를 포함할 수 있습니다 `Command` 요소입니다. 요소에는 다음 특성이 있습니다.  
  
|특성|설명|  
|---------------|-----------------|  
|`PackageFile`|필수 요소. 설치 하는 패키지의 이름으로 지정 된 조건 중 하나 이상을 해야 `InstallConditions` false를 반환 합니다. 사용 하 여 패키지를 같은 파일에 정의 해야 합니다는 `PackageFile` 요소입니다.|  
|`Arguments`|선택 사항입니다. 패키지 파일에 전달할 명령줄 인수 집합.|  
|`EstimatedInstallSeconds`|선택 사항입니다. 패키지를 설치 하는 데 걸리는 예상된 시간 (초)을 합니다. 이 값 부트스트래퍼 사용자에 게 표시 하는 진행률 표시줄의 크기를 결정 합니다. 기본값은 0,이 경우 예상 값이 지정 된 시간이 없습니다.|  
|`EstimatedDiskBytes`|선택 사항입니다. 설치 후 패키지는 차지 하는 바이트 단위로 디스크 공간의 예상된 크기 완료 됩니다. 이 값은 부트스트래퍼 사용자에 게 표시 하는 하드 디스크 공간 요구 사항에 사용 됩니다. 기본값은 0 일 경우 부트스트래퍼 모든 하드 디스크 공간 요구 사항 표시 되지 않습니다.|  
|`EstimatedTempBytes`|선택 사항입니다. 임시 디스크 공간을 패키지 해야 하는 바이트의 예상된 양입니다.|  
|`Log`|선택 사항입니다. 패키지의 루트 디렉터리를 기준으로 패키지를 생성 하는 로그 파일에 대 한 경로입니다.|  
  
## <a name="installconditions"></a>InstallConditions  
 `InstallConditions` 의 자식인 요소는 `Command` 요소입니다. 각 `Command` 요소는 하나만 있을 수 `InstallConditions` 요소입니다. 없는 경우 `InstallConditions` 요소가 존재 하 여 지정 된 패키지 `Condition` 항상 실행 됩니다.  
  
## <a name="bypassif"></a>BypassIf  
 `BypassIf` 의 자식 이며는 `InstallConditions` 요소는 명령을 실행할 수는 없습니다 조건을 설명 하 고 합니다. 각 `InstallConditions` 요소는 0 또는 그 이상 있을 수 있습니다 `BypassIf` 요소입니다.  
  
 `BypassIf`다음과 같은 특성이 있습니다.  
  
|특성|설명|  
|---------------|-----------------|  
|`Property`|필수 요소. 테스트 속성의 이름입니다. 속성 해야 이전에 정의 된 자식에서는 `InstallChecks` 요소입니다. 자세한 내용은 참조 [ \<InstallChecks > 요소](../deployment/installchecks-element-bootstrapper.md)합니다.|  
|`Compare`|필수 요소. 수행할 비교의 형식입니다. 다음은 유효한 값입니다.<br /><br /> `ValueEqualTo`, `ValueNotEqualTo`, `ValueGreaterThan`, `ValueGreaterThanOrEqualTo`, `ValueLessThan`, `ValueLessThanOrEqualTo`, `VersionEqualTo`, `VersionNotEqualTo`, `VersionGreaterThan`, `VersionGreaterThanOrEqualTo`, `VersionLessThan`, `VersionLessThanOrEqualTo`, `ValueExists`, `ValueNotExists`|  
|`Value`|필수 요소. 속성과 비교할 값입니다.|  
|`Schedule`|선택 사항입니다. 이름을 `Schedule` 이 규칙의 평가 시점을 정의 하는 태그입니다.|  
  
## <a name="failif"></a>FailIf  
 `FailIf` 의 자식인 요소는 `InstallConditions` 요소를 설치를 중지 하도록 조건을 설명 하 고 있습니다. 각 `InstallConditions` 요소는 0 또는 그 이상 있을 수 있습니다 `FailIf` 요소입니다.  
  
 `FailIf`다음과 같은 특성이 있습니다.  
  
|특성|설명|  
|---------------|-----------------|  
|`Property`|필수 요소. 테스트 속성의 이름입니다. 속성 해야 이전에 정의 된 자식에서는 `InstallChecks` 요소입니다. 자세한 내용은 참조 [ \<InstallChecks > 요소](../deployment/installchecks-element-bootstrapper.md)합니다.|  
|`Compare`|필수 요소. 수행할 비교의 형식입니다. 다음은 유효한 값입니다.<br /><br /> `ValueEqualTo`, `ValueNotEqualTo`, `ValueGreaterThan`, `ValueGreaterThanOrEqualTo`, `ValueLessThan`, `ValueLessThanOrEqualTo`, `VersionEqualTo`, `VersionNotEqualTo`, `VersionGreaterThan`, `VersionGreaterThanOrEqualTo`, `VersionLessThan`, `VersionLessThanOrEqualTo`, `ValueExists`, `ValueNotExists`|  
|`Value`|필수 요소. 속성과 비교할 값입니다.|  
|`String`|선택 사항입니다. 실패 시 사용자에 게 표시할 텍스트입니다.|  
|`Schedule`|선택 사항입니다. 이름을 `Schedule` 이 규칙의 평가 시점을 정의 하는 태그입니다.|  
  
## <a name="exitcodes"></a>ExitCodes  
 `ExitCodes` 의 자식인 요소는 `Command` 요소입니다. `ExitCodes` 요소 하나 이상 포함 `ExitCode` 요소 설치가 수행 해야 하는 패키지에서 종료 코드에 대 한 응답에서을 결정 합니다. 있을 수 있습니다 (옵션) `ExitCode` 요소 아래에 `Command` 요소입니다. `ExitCodes`특성이 없습니다.  
  
## <a name="exitcode"></a>ExitCode  
 `ExitCode` 의 자식인 요소는 `ExitCodes` 요소입니다. `ExitCode` 요소 설치가 수행 해야 하는 패키지에서 종료 코드에 대 한 응답에서을 결정 합니다. `ExitCode`자식 요소가 없는 하 고 다음과 같은 특성이 있습니다.  
  
|특성|설명|  
|---------------|-----------------|  
|`Value`|필수 요소. 종료 코드 값이 `ExitCode` 요소에 적용 됩니다.|  
|`Result`|필수 요소. 어떻게 설치가 종료 코드에 응답 해야 합니다. 다음은 유효한 값입니다.<br /><br /> `Success`. 패키지가 성공적으로 설치 플래그를 지정 합니다.<br /><br /> `SuccessReboot`. 패키지가 성공적으로 설치 플래그를 지정 하 고 시스템을 다시 시작 하도록 지시 합니다.<br /><br /> `Fail`. 패키지에 실패 한 것으로 플래그를 지정 합니다.<br /><br /> `FailReboot`. 실패로, 패키지 플래그를 지정 하 고 시스템을 다시 시작 하도록 지시 합니다.|  
|`String`|선택 사항입니다. 이 종료 코드에 대 한 응답으로 사용자에 게 표시할 값입니다.|  
|`FormatMessageFromSystem`|선택 사항입니다. 종료 코드에 해당 하는 시스템에서 제공한 오류 메시지를 사용 하거나에 제공 된 값을 사용할 것인지 결정 `String`합니다. 유효한 값은 `true`, 즉, 시스템 제공 하는 오류를 사용 하 고 `false`, 의미에서 제공 하는 문자열을 사용 하는 `String`합니다. 기본값은 `false`입니다. 이 속성이 `false`, 하지만 `String` 시스템에서 제공한 오류가 사용될지를 설정 하지 않으면 합니다.|  
  
## <a name="example"></a>예제  
 다음 코드 예제에서는.NET Framework 2.0을 설치 하기 위한 명령이 정의 합니다.  
  
```  
<Commands Reboot="Immediate">  
    <Command PackageFile="instmsia.exe"  
             Arguments= ' /q /c:"msiinst /delayrebootq"'  
             EstimatedInstallSeconds="20" >  
        <InstallConditions>  
           <BypassIf Property="VersionNT" Compare="ValueExists"/>  
             BypassIf Property="VersionMsi" Compare="VersionGreaterThanOrEqualTo" Value="2.0"/>  
        </InstallConditions>  
        <ExitCodes>  
            <ExitCode Value="0" Result="SuccessReboot"/>  
            <ExitCode Value="1641" Result="SuccessReboot"/>  
            <ExitCode Value="3010" Result="SuccessReboot"/>  
            <DefaultExitCode Result="Fail" FormatMessageFromSystem="true" String="GeneralFailure" />  
        </ExitCodes>  
    </Command>  
    <Command PackageFile="WindowsInstaller-KB884016-v2-x86.exe"  
             Arguments= '/quiet /norestart'   
             EstimatedInstallSeconds="20" >  
      <InstallConditions>  
          <BypassIf Property="Version9x" Compare="ValueExists"/>  
          <BypassIf Property="VersionNT" Compare="VersionLessThan" Value="5.0.3"/>  
          <BypassIf Property="VersionMsi" Compare="VersionGreaterThanOrEqualTo" Value="3.0"/>  
          <FailIf Property="AdminUser" Compare="ValueEqualTo" Value="false" String="AdminRequired"/>  
      </InstallConditions>  
      <ExitCodes>  
          <ExitCode Value="0" Result="Success"/>  
          <ExitCode Value="1641" Result="SuccessReboot"/>  
          <ExitCode Value="3010" Result="SuccessReboot"/>  
          <DefaultExitCode Result="Fail" FormatMessageFromSystem="true" String="GeneralFailure" />  
      </ExitCodes>  
    </Command>  
    <Command PackageFile="dotnetfx.exe"   
         Arguments=' /q:a /c:"install /q /l"'   
         EstimatedInstalledBytes="21000000"   
         EstimatedInstallSeconds="300">  
  
        <!-- These checks determine whether the package is to be installed -->  
        <InstallConditions>  
            <!-- Either of these properties indicates the .NET Framework is already installed -->  
            <BypassIf Property="DotNetInstalled" Compare="ValueNotEqualTo" Value="0"/>  
  
            <!-- Block install if user does not have adminpermissions -->  
            <FailIf Property="AdminUser" Compare="ValueEqualTo" Value="false" String="AdminRequired"/>  
  
            <!-- Block install on Windows 95 -->  
            <FailIf Property="Version9X" Compare="VersionLessThan" Value="4.10" String="InvalidPlatformWin9x"/>  
  
            <!-- Block install on Windows 2000 SP 2 or less -->  
            <FailIf Property="VersionNT" Compare="VersionLessThan" Value="5.0.3" String="InvalidPlatformWinNT"/>  
  
            <!-- Block install if Internet Explorer 5.01 or later is not present -->  
            <FailIf Property="IEVersion" Compare="ValueNotExists" String="InvalidPlatformIE" />  
            <FailIf Property="IEVersion" Compare="VersionLessThan" Value="5.01" String="InvalidPlatformIE" />  
  
            <!-- Block install if the operating system does not support x86 -->  
            <FailIf Property="ProcessorArchitecture" Compare="ValueNotEqualTo" Value="Intel" String="InvalidPlatformArchitecture" />  
       </InstallConditions>  
  
        <ExitCodes>  
            <ExitCode Value="0" Result="Success"/>  
            <ExitCode Value="3010" Result="SuccessReboot"/>  
            <ExitCode Value="4097" Result="Fail" String="AdminRequired"/>  
            <ExitCode Value="4098" Result="Fail" String="WindowsInstallerComponentFailure"/>  
            <ExitCode Value="4099" Result="Fail" String="WindowsInstallerImproperInstall"/>  
            <ExitCode Value="4101" Result="Fail" String="AnotherInstanceRunning"/>  
            <ExitCode Value="4102" Result="Fail" String="OpenDatabaseFailure"/>  
            <ExitCode Value="4113" Result="Fail" String="BetaNDPFailure"/>  
            <DefaultExitCode Result="Fail" FormatMessageFromSystem="true" String="GeneralFailure" />  
        </ExitCodes>  
  
    </Command>  
</Commands>  
```  
  
## <a name="see-also"></a>참고 항목  
 [제품 및 패키지 스키마 참조](../deployment/product-and-package-schema-reference.md)   
 [\<InstallChecks > 요소](../deployment/installchecks-element-bootstrapper.md)