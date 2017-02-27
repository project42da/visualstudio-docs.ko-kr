---
title: "&lt;Commands&gt; 요소(부트스트래퍼) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
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
  - "<Commands> 요소[부트스트래퍼]"
ms.assetid: e61d5787-fe1f-4ebf-b0cf-0d7909be7ffb
caps.latest.revision: 13
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 13
---
# &lt;Commands&gt; 요소(부트스트래퍼)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

`Commands` 요소는 `InstallChecks` 요소 아래의 요소에서 설명하는 테스트를 구현하고, 테스트에 실패하는 경우 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 부트스트래퍼에서 설치해야 할 패키지를 선언합니다.  
  
## 구문  
  
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
  
## 요소 및 특성  
 `Commands` 요소는 필수 항목입니다.   요소에는 다음과 같은 특성이 있습니다.  
  
|특성|설명|  
|--------|--------|  
|`Reboot`|선택적 요소.  패키지 중 하나에서 재시작 종료 코드를 반환하는 경우 시스템을 다시 시작할지 여부를 결정합니다.  다음 목록에서는 올바른 값을 보여 줍니다.<br /><br /> `Defer`.  재시작을 지연하여 나중으로 미룹니다.<br /><br /> `Immediate`.  패키지 중 하나에서 재시작 종료 코드를 반환하는 즉시 시스템을 다시 시작합니다.<br /><br /> `None`.  재시작 요청을 모두 무시합니다.<br /><br /> 기본값은 `Immediate`입니다.|  
  
## 명령  
 `Command` 요소는 `Commands` 요소의 자식 요소입니다.  `Commands` 요소에는 `Command` 요소가 하나 이상 있을 수 있습니다.  이 요소에는 다음과 같은 특성이 있습니다.  
  
|특성|설명|  
|--------|--------|  
|`PackageFile`|필수 요소.  `InstallConditions`에서 지정한 조건 중 하나 이상에서 false를 반환하는 경우 설치할 패키지의 이름입니다.  이 패키지는 `PackageFile` 요소를 사용하여 동일한 파일에 정의해야 합니다.|  
|`Arguments`|선택적 요소.  패키지 파일에 전달할 명령줄 인수의 집합입니다.|  
|`EstimatedInstallSeconds`|선택적 요소.  패키지를 설치하는 데 걸리는 초 단위 예상 시간입니다.  이 값은 부트스트래퍼에서 사용자에게 표시하는 진행률 표시줄의 크기를 결정합니다.  기본값은 0입니다. 이 경우 예상 시간이 지정되지 않습니다.|  
|`EstimatedDiskBytes`|선택적 요소.  설치를 완료한 후에 패키지가 차지할 디스크 공간의 바이트 단위 예상 크기입니다.  이 값은 부트스트래퍼에서 사용자에게 하드 디스크 공간 요구 사항을 표시하는 데 사용됩니다.  기본값은 0입니다. 이 경우 부트스트래퍼는 하드 디스크 공간 요구 사항을 표시하지 않습니다.|  
|`EstimatedTempBytes`|선택적 요소.  패키지가 임시로 차지할 디스크 공간의 바이트 단위 예상 크기입니다.|  
|`Log`|선택적 요소.  패키지에서 생성하는 로그 파일의 경로입니다. 이 경로는 패키지의 루트 디렉터리를 기준으로 합니다.|  
  
## InstallConditions  
 `InstallConditions` 요소는 `Command` 요소의 자식입니다.  각 `Command` 요소에는 `InstallConditions` 요소가 하나만 있을 수 있습니다.  `InstallConditions` 요소가 없으면 `Condition`에서 지정한 패키지가 항상 실행됩니다.  
  
## BypassIf  
 `BypassIf` 요소는 `InstallConditions` 요소의 자식이며, 명령을 실행하지 말아야 할 조건을 설명합니다.  각 `InstallConditions` 요소에는 `BypassIf` 요소가 0개 이상 있을 수 있습니다.  
  
 `BypassIf`에는 다음과 같은 특성이 있습니다.  
  
|특성|설명|  
|--------|--------|  
|`Property`|필수 요소.  테스트할 속성의 이름입니다.  이 속성은 `InstallChecks` 요소의 자식에서 미리 정의되어 있어야 합니다.  자세한 내용은 [\<InstallChecks\> 요소](../deployment/installchecks-element-bootstrapper.md)를 참조하십시오.|  
|`Compare`|필수 요소.  수행할 비교의 형식입니다.  다음 목록에서는 올바른 값을 보여 줍니다.<br /><br /> `ValueEqualTo`, `ValueNotEqualTo`, `ValueGreaterThan`, `ValueGreaterThanOrEqualTo`, `ValueLessThan`, `ValueLessThanOrEqualTo`, `VersionEqualTo`, `VersionNotEqualTo`, `VersionGreaterThan`, `VersionGreaterThanOrEqualTo`, `VersionLessThan`, `VersionLessThanOrEqualTo`, `ValueExists`, `ValueNotExists`|  
|`Value`|필수 요소.  속성과 비교할 값입니다.|  
|`Schedule`|선택적 요소.  이 규칙을 확인해야 할 시기를 정의하는 `Schedule` 태그의 이름입니다.|  
  
## FailIf  
 `FailIf` 요소는 `InstallConditions` 요소의 자식이며, 설치를 중단해야 할 조건을 설명합니다.  각 `InstallConditions` 요소에는 `FailIf` 요소가 0개 이상 있을 수 있습니다.  
  
 `FailIf`에는 다음과 같은 특성이 있습니다.  
  
|특성|설명|  
|--------|--------|  
|`Property`|필수 요소.  테스트할 속성의 이름입니다.  이 속성은 `InstallChecks` 요소의 자식에서 미리 정의되어 있어야 합니다.  자세한 내용은 [\<InstallChecks\> 요소](../deployment/installchecks-element-bootstrapper.md)를 참조하십시오.|  
|`Compare`|필수 요소.  수행할 비교의 형식입니다.  다음 목록에서는 올바른 값을 보여 줍니다.<br /><br /> `ValueEqualTo`, `ValueNotEqualTo`, `ValueGreaterThan`, `ValueGreaterThanOrEqualTo`, `ValueLessThan`, `ValueLessThanOrEqualTo`, `VersionEqualTo`, `VersionNotEqualTo`, `VersionGreaterThan`, `VersionGreaterThanOrEqualTo`, `VersionLessThan`, `VersionLessThanOrEqualTo`, `ValueExists`, `ValueNotExists`|  
|`Value`|필수 요소.  속성과 비교할 값입니다.|  
|`String`|선택적 요소.  실패 시 사용자에게 표시할 텍스트입니다.|  
|`Schedule`|선택적 요소.  이 규칙을 확인해야 할 시기를 정의하는 `Schedule` 태그의 이름입니다.|  
  
## ExitCodes  
 `ExitCodes` 요소는 `Command` 요소의 자식입니다.  `ExitCodes` 요소에는 패키지의 종료 코드에 대한 응답으로 설치에서 수행해야 할 작업을 결정하는 `ExitCode` 요소가 하나 이상 들어 있습니다.  `Command` 요소 아래에 선택적 `ExitCode` 요소가 하나 있을 수 있습니다.  `ExitCodes`에는 특성이 없습니다.  
  
## ExitCode  
 `ExitCode` 요소는 `ExitCodes` 요소의 자식입니다.  `ExitCode` 요소는 패키지의 종료 코드에 대한 응답으로 설치에서 수행해야 할 작업을 결정합니다.  `ExitCode`는 자식 요소를 포함하지 않고 다음과 같은 특성이 있습니다.  
  
|특성|설명|  
|--------|--------|  
|`Value`|필수 요소.  이 `ExitCode` 요소를 적용할 종료 코드 값입니다.|  
|`Result`|필수 요소.  설치에서 이 종료 코드에 응답하는 방식을 지정합니다.  다음 목록에서는 올바른 값을 보여 줍니다.<br /><br /> `Success`.  패키지가 성공적으로 설치된 것으로 플래그를 설정합니다.<br /><br /> `SuccessReboot`.  패키지가 성공적으로 설치된 것으로 플래그를 설정하고 시스템을 다시 시작하도록 지시합니다.<br /><br /> `Fail`.  패키지 설치에 실패한 것으로 플래그를 설정합니다.<br /><br /> `FailReboot`.  패키지 설치에 실패한 것으로 플래그를 설정하고 시스템을 다시 시작하도록 지시합니다.|  
|`String`|선택적 요소.  이 종료 코드에 대한 응답으로 사용자에게 표시할 값입니다.|  
|`FormatMessageFromSystem`|선택적 요소.  종료 코드에 대한 응답으로 시스템에서 제공하는 오류 메시지를 사용할지 `String`에서 제공하는 값을 사용할지 결정합니다.  `true`로 설정하면 시스템에서 제공하는 오류가 사용되고, `false`로 설정하면 `String`에서 제공하는 문자열이 사용됩니다.  기본값은 `false`입니다.  이 속성이 `false`이지만 `String`이 설정되지 않은 경우 시스템에서 제공한 오류가 사용됩니다.|  
  
## 예제  
 다음 코드 예제에서는 .NET Framework 2.0을 설치하기 위한 명령을 정의합니다.  
  
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
  
## 참고 항목  
 [제품 및 패키지 스키마 참조](../deployment/product-and-package-schema-reference.md)   
 [\<InstallChecks\> 요소](../deployment/installchecks-element-bootstrapper.md)