---
title: "제품 및 패키지 스키마 참조 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-deployment"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "MSBuild.GenerateBootstrapper.CircularIncludes"
  - "MSBuild.ResolveManifestFiles.PublishFileNotFound"
dev_langs: 
  - "FSharp"
  - "VB"
  - "CSharp"
  - "C++"
helpviewer_keywords: 
  - "ClickOnce, 부트스트래퍼 요소"
  - "ClickOnce, 제품 및 패키지 파일"
  - "패키지 파일[ClickOnce]"
  - "패키지 파일[Windows Installer]"
  - "제품 파일[ClickOnce]"
  - "제품 파일[Windows Installer]"
  - "Windows Installer, 부트스트래퍼 요소"
  - "Windows Installer, 제품 및 패키지 파일"
ms.assetid: 5a74878f-b896-4cca-b968-98d00fe78fb0
caps.latest.revision: 7
caps.handback.revision: 7
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# 제품 및 패키지 스키마 참조
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

*제품 파일*은 [!INCLUDE[ndptecclick](../deployment/includes/ndptecclick_md.md)] 응용 프로그램에 필요한 모든 외부 종속성을 설명하는 XML 매니페스트입니다.  외부 종속성의 예로는 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]나 MDAC\(Microsoft Data Access Components\)를 들 수 있습니다.  패키지 파일은 제품 파일과 비슷하지만 종속성 중 지역화된 어셈블리, 사용권 계약, 설명서 등 culture에 종속된 구성 요소를 설치하는 데 사용된다는 점에서 차이가 있습니다.  
  
 제품 파일과 패키지 파일은 최상위 `Product` 요소나 `Package` 요소를 구성하며 각각 다음과 같은 요소를 포함합니다.  
  
|요소|설명|특성|  
|--------|--------|--------|  
|[\<Product\> 요소](../deployment/product-element-bootstrapper.md)|제품 파일에 필요한 최상위 요소입니다.|없음|  
|[\<Package\> 요소](../deployment/package-element-bootstrapper.md)|패키지 파일에 필요한 최상위 요소입니다.|`Culture`<br /><br /> `Name`<br /><br /> `EULA`|  
|[\<RelatedProducts\> 요소](../deployment/relatedproducts-element-bootstrapper.md)|제품 파일의 선택적 요소입니다.  이 제품에서 설치의 기반으로 삼거나 이 제품이 의존하는 다른 제품입니다.|없음|  
|[\<InstallChecks\> 요소](../deployment/installchecks-element-bootstrapper.md)|필수적 요소입니다.  설치하는 동안 로컬 컴퓨터에서 수행할 종속성 검사를 나열합니다.|없음|  
|[\<Commands\> 요소](../deployment/commands-element-bootstrapper.md)|필수적 요소입니다.  `InstallChecks`의 설명에 따라 하나 이상의 설치 검사를 실행하고, 검사가 실패할 경우에 설치할 패키지를 지정합니다.|없음|  
|[\<PackageFiles\> 요소](../deployment/packagefiles-element-bootstrapper.md)|필수적 요소입니다.  이 설치 프로세스에서 설치할 수 있는 패키지를 나열합니다.|없음|  
|[\<Strings\> 요소](../deployment/strings-element-bootstrapper.md)|필수적 요소입니다.  제품 이름과 오류 문자열의 지역화된 버전을 저장합니다.|없음|  
  
## 설명  
 패키지 스키마는 MS Build 부트스트래핑 작업에서 생성하며 하드 코딩된 자체 논리가 거의 없는 스텁 프로그램인 Setup.exe에서 사용합니다.  이 스키마는 설치 프로세스의 모든 측면을 주관합니다.  
  
 `InstallChecks`는 지정한 패키지의 존재에 대해 setup.exe에서 실행해야 하는 테스트입니다.  `PackageFiles`는 지정한 테스트에 실패하는 경우 설치 프로세스에서 설치해야 할 모든 패키지를 나열합니다.  Commands 아래의 각 Command 엔트리에서는 `InstallChecks`에서 설명한 테스트 중 하나를 실행하고 테스트가 실패하는 경우 실행할 `PackageFile`을 지정합니다.  `Strings` 요소를 사용하여 제품 이름과 오류 메시지를 지역화하고 단일 설치 이진 파일을 사용하여 응용 프로그램을 언어 수에 상관없이 설치할 수 있습니다.  
  
## 예제  
 다음 코드 예제에서는 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)]를 설치하기 위한 전체 제품 파일을 보여 줍니다.  
  
```  
<?xml version="1.0" encoding="utf-8" ?>  
  
<Product  
  xmlns="http://schemas.microsoft.com/developer/2004/01/bootstrapper"  
  ProductCode="Microsoft.Net.Framework.2.0"  
>  
  
    <RelatedProducts>  
        <IncludesProduct Code="Microsoft.Windows.Installer.2.0" />  
    </RelatedProducts>  
  
    <!-- Defines list of files to be copied on build -->  
    <PackageFiles>  
        <PackageFile Name="instmsia.exe" HomeSite="InstMsiAExe" PublicKey="3082010A0282010100AA99BD39A81827F42B3D0B4C3F7C772EA7CBB5D18C0DC23A74D793B5E0A04B3F595ECE454F9A7929F149CC1A47EE55C2083E1220F855F2EE5FD3E0CA96BC30DEFE58C82732D08554E8F09110BBF32BBE19E5039B0B861DF3B0398CB8FD0B1D3C7326AC572BCA29A215908215E277A34052038B9DC270BA1FE934F6F335924E5583F8DA30B620DE5706B55A4206DE59CBF2DFA6BD154771192523D2CB6F9B1979DF6A5BF176057929FCC356CA8F440885558ACBC80F464B55CB8C96774A87E8A94106C7FF0DE968576372C36957B443CF323A30DC1BE9D543262A79FE95DB226724C92FD034E3E6FB514986B83CD0255FD6EC9E036187A96840C7F8E203E6CF050203010001"/>  
        <PackageFile Name="WindowsInstaller-KB884016-v2-x86.exe" HomeSite="Msi30Exe" PublicKey="3082010A0282010100B22D8709B55CDF5599EB5262E7D3F4E34571A932BF94F20EE90DADFE9DC7046A584E9CA4D1D84441FB647E0F65EEC817DA4DDBD9D650B40C565B6C16884BBF03EE504883EC4F88939A51E394197FFAB397A5CE606D9FDD4C9338BDCD345971E686CEE98399A096B8EAE0445B1342B93A484E5472F70896E400C482017643AF61C2DBFAE5C5F00213DDF835B40F0D5236467443B1A2CA9CDD7E99F1351177FB1526018ECFE0B804782A15FD72C66076910CE74FB218181B6989B4F12F211B66EACA91C7460DB91758715856866523D10232AE64A06FDA5295FDFBDD8D34F5C10C35A347D7E91B6AFA0F45B4E8321D7019BDD1F9E5641FEB8737EA6FD40D838FFD0203010001"/>  
        <PackageFile Name="dotnetfx.exe" HomeSite="DotNetFXExe" PublicKey="3082010A0282010100B22D8709B55CDF5599EB5262E7D3F4E34571A932BF94F20EE90DADFE9DC7046A584E9CA4D1D84441FB647E0F65EEC817DA4DDBD9D650B40C565B6C16884BBF03EE504883EC4F88939A51E394197FFAB397A5CE606D9FDD4C9338BDCD345971E686CEE98399A096B8EAE0445B1342B93A484E5472F70896E400C482017643AF61C2DBFAE5C5F00213DDF835B40F0D5236467443B1A2CA9CDD7E99F1351177FB1526018ECFE0B804782A15FD72C66076910CE74FB218181B6989B4F12F211B66EACA91C7460DB91758715856866523D10232AE64A06FDA5295FDFBDD8D34F5C10C35A347D7E91B6AFA0F45B4E8321D7019BDD1F9E5641FEB8737EA6FD40D838FFD0203010001"/>  
        <PackageFile Name="dotnetchk.exe"/>  
    </PackageFiles>  
  
    <InstallChecks>  
        <ExternalCheck Property="DotNetInstalled" PackageFile="dotnetchk.exe" />  
        <RegistryCheck Property="IEVersion" Key="HKLM\Software\Microsoft\Internet Explorer" Value="Version" />  
    </InstallChecks>  
  
    <!-- Defines how to invoke the setup for the .NET Framework redist -->  
    <!-- TODO: Needs EstrimatedTempSpace, LogFile, and an update of EstimatedDiskSpace -->  
    <Commands Reboot="Defer">  
        <Command PackageFile="instmsia.exe"  
                 Arguments= ' /q /c:"msiinst /delayrebootq"'  
                 EstimatedInstallSeconds="20" >  
            <InstallConditions>  
                <BypassIf Property="VersionNT" Compare="ValueExists"/>  
                <BypassIf Property="VersionMsi" Compare="VersionGreaterThanOrEqualTo" Value="2.0"/>  
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
  
                <!-- Block install if user does not have admin privileges -->  
                <FailIf Property="AdminUser" Compare="ValueEqualTo" Value="false" String="AdminRequired"/>  
  
                <!-- Block install on Windows 95 -->  
                <FailIf Property="Version9X" Compare="VersionLessThan" Value="4.10" String="InvalidPlatformWin9x"/>  
  
                <!-- Block install on Windows 2000 SP 2 or less -->  
                <FailIf Property="VersionNT" Compare="VersionLessThan" Value="5.0.3" String="InvalidPlatformWinNT"/>  
  
                <!-- Block install if Internet Explorer 5.01 or greater is not present -->  
                <FailIf Property="IEVersion" Compare="ValueNotExists" String="InvalidPlatformIE" />  
                <FailIf Property="IEVersion" Compare="VersionLessThan" Value="5.01" String="InvalidPlatformIE" />  
  
                <!-- Block install if the platform is not x86 -->  
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
</Product>  
```  
  
## 참고 항목  
 [ClickOnce 배포 매니페스트](../deployment/clickonce-deployment-manifest.md)   
 [ClickOnce 응용 프로그램 매니페스트](../deployment/clickonce-application-manifest.md)