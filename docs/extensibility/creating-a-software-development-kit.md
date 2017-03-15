---
title: "소프트웨어 개발 키트 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 8496afb4-1573-4585-ac67-c3d58b568a12
caps.latest.revision: 54
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 54
---
# 소프트웨어 개발 키트 만들기
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

소프트웨어 개발 키트 (SDK)은 Visual Studio에서 단일 항목으로 참조할 수 있는 Api의 컬렉션입니다.  **참조 관리자** 대화 상자는 프로젝트에 관련 된 모든 Sdk를 나열 합니다. 프로젝트에 SDK를 추가 하면 Api를 Visual Studio에서 사용할 수 있습니다.  
  
 Sdk는 다음과 같은 두 종류가 있습니다.  
  
-   플랫폼 Sdk는 플랫폼에 대 한 앱 개발을 위한 필수 구성 요소가 있습니다. 예를 들어는 [!INCLUDE[win81](../debugger/includes/win81_md.md)] SDK 개발 해야 합니다. [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] 앱입니다.  
  
-   확장 Sdk는 선택적 구성 요소는 플랫폼을 확장 아닌 해당 플랫폼에 앱을 개발 하기 위한 필수 항목입니다.  
  
 다음 섹션에서는 Sdk 및 platform SDK를 만드는 방법의 일반적인 인프라와 확장 SDK입니다.  
  
-   [플랫폼 Sdk](#PlatformSDKs)  
  
-   [확장 Sdk](#ExtensionSDKs)  
  
##  <a name="a-nameplatformsdksa-platform-sdks"></a><a name="PlatformSDKs"></a> 플랫폼 Sdk  
 플랫폼 Sdk는 응용 프로그램 플랫폼을 개발 해야 합니다. 예를 들어는 [!INCLUDE[win81](../debugger/includes/win81_md.md)] 앱을 개발 하려면 SDK가 필요 [!INCLUDE[win81](../debugger/includes/win81_md.md)]합니다.  
  
### <a name="installation"></a>설치  
 모든 플랫폼 Sdk HKLM\Software\Microsoft\Microsoft Sdk에서 설치 됩니다\\[TPI] \v [TPV]\\@InstallationFolder = [SDK 루트]. 따라서는 [!INCLUDE[win81](../debugger/includes/win81_md.md)] HKLM\Software\Microsoft\Microsoft SDKs\Windows\v8.1에 SDK를 설치 합니다.  
  
### <a name="layout"></a>레이아웃  
 플랫폼 Sdk에는 다음과 같은 레이아웃을 적용 됩니다.  
  
```  
\[InstallationFolder root]  
            SDKManifest.xml  
            \References  
                  \[config]  
                        \[arch]  
            \DesignTime  
                  \[config]  
                        \[arch]  
```  
  
|노드|설명|  
|----------|-----------------|  
|References 폴더|Api에 대해 코딩 된 수를 포함 하는 이진 파일을 포함 합니다. 이러한 Windows 메타 데이터 (WinMD) 파일이 나 어셈블리에 포함 될 수 있습니다.|  
|DesignTime 폴더|사전-run/디버깅 시간에만 필요한 파일이 포함 되어 있습니다. 이러한 XML 문서, 라이브러리, 헤더, 도구 상자 디자인 타임 이진 파일, MSBuild 아티팩트 등을 포함 될 수 있습니다.<br /><br /> XML 문서와 마찬가지로 이상적으로 \DesignTime 폴더에 배치할 수 있지만 참조에 대 한 XML 문서는 Visual Studio에서 참조 파일과 함께 배치 될 계속 됩니다. 예를 들어, XML 문서에 대 한 참조 \References\\[구성]\\[arch]\sample.dll \References 됩니다\\[구성]\\[arch]\sample.xml, 및 해당 doc의 지역화 된 버전에는 \References 됩니다\\[구성]\\[arch]\\[locale]\sample.xml 합니다.|  
|구성 폴더|세 개의 폴더가 있을 수 있습니다: 디버그, 소매 및 CommonConfiguration 합니다. SDK 작성자는 동일한 집합 SDK 파일을 사용 해야, SDK 소비자를 대상으로 하는 구성에 관계 없이 경우 CommonConfiguration 파일을를 배치할 수 있습니다.|  
|아키텍처 폴더|모든 지원 되는 아키텍처 폴더 존재할 수 있습니다. Visual Studio 지원 아키텍처: x86, x64, ARM 및 중립 합니다. 참고: Win32, x86에 매핑되고 AnyCPU 중립에 매핑됩니다.<br /><br /> MSBuild는 플랫폼 Sdk \CommonConfiguration\neutral 인 경우에 찾습니다.|  
|SDKManifest.xml|이 파일은 Visual Studio SDK를 사용 하는 방법을 설명 합니다. 에 대 한 SDK 매니페스트를 살펴보고 [!INCLUDE[win81](../debugger/includes/win81_md.md)]:<br /><br /> `<FileList             DisplayName = “Windows”             PlatformIdentity = “Windows, version=8.1”             TargetFramework = “.NET for Windows Store apps, version=v4.5.1; .NET Framework, version=v4.5.1”             MinVSVersion = “14.0”>              <File Reference = “Windows.winmd”>                <ToolboxItems VSCategory = “Toolbox.Default” />             </File> </FileList>`<br /><br /> **표시 이름:** 찾아보기 목록에 개체 브라우저를 표시 하는 값입니다.<br /><br /> **PlatformIdentity:** 이 특성의 존재 여부에 따라 Visual Studio 및 MSBuild SDK 플랫폼 SDK 인지 및 여기에서 추가 된 참조는 복사 안 로컬로 합니다.<br /><br /> **TargetFramework:** 만이 값에 지정 된 대로 동일한 프레임 워크를 대상으로 하는 투영 하 수 있도록 Visual Studio에서이 특성은 사용 특성 SDK를 사용할 수 있습니다.<br /><br /> **MinVSVersion:** 이 특성에 적용 되는 Sdk를 사용 하도록 Visual Studio에서 사용 됩니다.<br /><br /> **참조:** 이 특성 컨트롤이 포함 된 참조만 지정 되어야 합니다. 에 대 한 참조를 컨트롤에 포함 되는지 여부를 지정 하는 방법에 대 한 내용은 다음을 참조 하세요.|  
  
##  <a name="a-nameextensionsdksa-extension-sdks"></a><a name="ExtensionSDKs"></a> 확장 Sdk  
 다음 섹션에서는 확장 SDK를 배포 하는 데 필요한 것을 설명 합니다.  
  
### <a name="installation"></a>설치  
 확장 Sdk는 레지스트리 키를 지정 하지 않고 모든 사용자에 대해 또는 특정 사용자에 설치할 수 있습니다. 모든 사용자에 대 한 SDK를 설치 하려면 다음 경로 사용 합니다.  
  
 `%Program Files%\Microsoft SDKs\<target platform>\v<platform version number>\ExtensionSDKs`  
  
 사용자 고유의 설치의 경우 다음 경로 사용 합니다.  
  
 `%USERPROFILE%\AppData\Local\Microsoft SDKs\<target platform>\v<platform version number>\ExtensionSDKs`  
  
 다른 위치를 사용 하려는 경우 다음 두 가지 중 하나를 수행 해야 합니다.  
  
1.  레지스트리 키에서 지정 합니다.  
  
     `HKLM\Software\Microsoft\Microsoft SDKs\<target platform>\v<platform version number>\ExtensionSDKs\<SDKName>\<SDKVersion>\`  
  
     값 (기본값) 하위 키를 추가 하 고 `<path to SDK><SDKName><SDKVersion>`합니다.  
  
2.  MSBuild 속성 추가 `SDKReferenceDirectoryRoot` 을 프로젝트 파일입니다. 이 속성의 값은 참조 하려는 확장 Sdk는 거주 하는 디렉터리의 세미 콜론 구분 된 목록.  
  
### <a name="installation-layout"></a>설치 레이아웃  
 확장 Sdk는 다음과 같은 설치 레이아웃을 사용할 수 있습니다.  
  
```  
\<ExtensionSDKs root>  
           \<SDKName>  
                 \<SDKVersion>  
                        SDKManifest.xml  
                        \References  
                              \<config>  
                                    \<arch>  
                        \Redist  
                              \<config>  
                                    \<arch>  
                        \DesignTime  
                               \<config>  
                                     \<arch>  
  
```  
  
1.  \\< SDKName\>\\< SDKVersion\>: 이름 및 버전의 SDK는 SDK 루트 경로에 해당 폴더 이름은에서 파생 된 확장 합니다. Visual Studio에서이 id를 표시 하 고 MSBuild이이 id를 사용 하 여 디스크에 SDK를 찾을 수는 **속성** 창 및 **참조 관리자** 대화 합니다.  
  
2.  References 폴더: Api를 포함 하는 이진 파일입니다. 여기에 Windows 메타 데이터 (WinMD) 파일이 나 어셈블리 수 있습니다.  
  
3.  재배포 가능 패키지 폴더: 런타임/디버깅에 필요 하며, 사용자의 응용 프로그램의 일부로 패키징되 해야 하는 파일입니다. \Redist 아래에 있는 모든 이진 파일을 배치 해야\\< 구성\>\\< 아키텍처\>, 고 이진 이름 고유성을 보장 하려면 다음 형식을 가져야 합니다.: **\< 회사>. \< 제품>. \< 목적>. \< 확장명>**합니다. 예를 들어: Microsoft.Cpp.Build.dll \Redist 아래에 있는 다른 Sdk (예: javascript, css, 우선 순위, xaml, png 및 jpg 파일)에서 파일 이름으로 이름이 충돌할 하는 모든 파일을 배치 해야\\< 구성\>\\< arch\>\\< sdkname\>\ XAML과 관련 된 파일을 제외 하 고 제어 합니다. 이러한 파일은 \redist 아래에 배치 되어야\\< 구성\>\\< arch\>\\< componentname\>\\합니다.  
  
4.  DesignTime 폴더: 유일한 사전-run/디버깅에 필요한 파일이 고 사용자의 응용 프로그램의 일부분으로 패키지할 수 없습니다. 이러한 XML 문서, 라이브러리, 헤더, 도구 상자 디자인 타임 이진 파일, MSBuild 아티팩트 등 일 수 있습니다. 네이티브 프로젝트에서 사용 해야 하는 모든 SDK는 *SDKName*.props 파일입니다. 다음이 유형의 파일의 예제를 보여 줍니다.  
  
    ```xml  
    <?xml version="1.0" encoding="utf-8"?>  
    <Project xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
      <PropertyGroup>  
        <ExecutablePath>C:\Temp\ExecutablePath;$(ExecutablePath)</ExecutablePath>  
        <IncludePath>$(FrameworkSDKRoot)\..\v8.1\ExtensionSDKs\cppimagingsdk\1.0\DesignTime\CommonConfiguration\Neutral\include;$(IncludePath)</IncludePath>  
        <AssemblyReferencePath>C:\Temp\AssemblyReferencePath;(AssemblyReferencePath)</AssemblyReferencePath>  
        <LibraryPath>$(FrameworkSDKRoot)\..\v8.1\ExtensionSDKs\cppimagingsdk\1.0\DesignTime\Debug\ARM;$(LibraryPath)</LibraryPath>  
        <SourcePath>C:\Temp\SourcePath\X64;$(SourcePath)</SourcePath>  
        <ExcludePath>C:\Temp\ExcludePath\X64;$(ExcludePath)</ExcludePath>  
        <_PropertySheetDisplayName>DevILSDK, 1.0</_PropertySheetDisplayName>  
      </PropertyGroup>  
    </Project>  
  
    ```  
  
     XML 참조 문서 참조 파일과 함께 배치 됩니다. 예를 들어,에 대 한 XML 참조 문서는 **\References\\< 구성\>\\< 아키텍처\>\sample.dll** 어셈블리는 **\References\\< 구성\>\\< 아키텍처\>\sample.xml**, 해당 doc의 지역화 된 버전 및 **\References\\< 구성\>\\< 아키텍처\>\\< 로캘\>\sample.xml**합니다.  
  
5.  구성 폴더: 세 개의 하위 폴더: 디버그, 소매 및 CommonConfiguration 합니다. SDK 작성자는 동일한 집합 SDK 파일을 사용 해야, SDK 소비자에 의해 대상으로 하는 구성에 관계 없이 때 CommonConfiguration 파일을 배치할 수 있습니다.  
  
6.  아키텍처 폴더: 아키텍처 지원 됩니다: x86, x64, ARM, 무관 합니다. Win32, x86에 매핑되고 AnyCPU 중립에 매핑됩니다.  
  
### <a name="sdkmanifestxml"></a>SDKManifest.xml  
 이 파일은 Visual Studio SDK를 사용 하는 방법을 설명 합니다. 다음은 예제입니다.  
  
```  
<FileList>  
DisplayName = “My SDK”  
ProductFamilyName = “My SDKs”  
TargetFramework = “.NETCore, version=v4.5.1; .NETFramework, version=v4.5.1”  
MinVSVersion = “14.0”  
MaxPlatformVersion = "8.1"  
AppliesTo = "WindowsAppContainer + WindowsXAML"  
SupportPrefer32Bit = “True”  
SupportedArchitectures = “x86;x64;ARM”  
SupportsMultipleVersions = “Error”  
CopyRedistToSubDirectory = “.”  
DependsOn = “SDKB, version=2.0”  
MoreInfo = “http://msdn.microsoft.com/MySDK”>  
<File Reference = “MySDK.Sprint.winmd” Implementation = “XNASprintImpl.dll”>  
<Registration Type = “Flipper” Implementation = “XNASprintFlipperImpl.dll” />  
<Registration Type = “Flexer” Implementation = “XNASprintFlexerImpl.dll” />  
<ToolboxItems VSCategory = “Toolbox.Default” />  
</File>  
</FileList>  
```  
  
 다음은 파일의 요소를 제공합니다.  
  
1.  표시 이름: 참조 관리자, 솔루션 탐색기, 개체 브라우저 및 Visual studio 사용자 인터페이스의 다른 위치에 표시 되는 값입니다.  
  
2.  ProductFamilyName: 전체 SDK 제품 이름입니다. 예를 들어는 [!INCLUDE[winjs_long](../debugger/includes/winjs_long_md.md)] SDK "Microsoft.WinJS" SDK 제품 패밀리의 동일한 제품군에 속하는 "Microsoft.WinJS.1.0" 및 "Microsoft.WinJS.2.0" 라고 합니다. 이 특성에는 Visual Studio 및 MSBuild 해당 연결을 만들 수 있습니다. 이 특성이 없는 경우 SDK 이름 제품 제품군 이름으로 사용 됩니다.  
  
3.  FrameworkIdentity: 소비 응용 프로그램 매니페스트에이 특성의 값을 추가할 하나 이상의 Windows 구성 요소 라이브러리에 대 한 종속성을 지정 합니다. 이 특성은 Windows 구성 요소 라이브러리에만 적용할 수 있습니다.  
  
4.  TargetFramework: 참조 관리자, 도구 상자에서 사용할 수 있는 Sdk를 지정 합니다. 예를 들어 이것은 대상 프레임 워크 모니커가의 세미콜론으로 구분 된 목록이 ".NET Framework, 버전 = v2.0;.NET Framework, 버전 v4.5.1 =". 여러 버전의 동일한 대상 프레임 워크를 지정 하는 경우 참조 관리자 필터링 목적에 대 한 지정된 된 가장 낮은 버전을 사용 합니다. 예를 들어 경우 ".NET Framework, 버전 = v2.0;.NET Framework, 버전 v4.5.1 ="이 지정, 참조 관리자에서 사용 됩니다 ".NET Framework, 버전 v2.0 =". 특정 대상 프레임 워크 프로필을 지정 하는 경우 해당 프로필에만 필터링 목적에 대 한 참조 관리자에 의해 사용 됩니다. 예를 들어, "Silverlight 버전 = v4.0, profile WindowsPhone =" 지정 참조 관리자에는 Windows Phone 프로필;에 대 한 필터 전체 Silverlight 4.0 Framework를 대상으로 하는 프로젝트에 SDK 참조 관리자에서 표시 되지 않습니다.  
  
5.  MinVSVersion: 최소 Visual Studio 버전입니다.  
  
6.  MaxPlatformVerson: 확장 SDK는 작동 하지는 플랫폼 버전을 지정할 최대 대상 플랫폼 버전을 사용 해야 합니다. 예를 들어 Microsoft Visual c + + 런타임 패키지 v11.0 해야 참조할 수만 Windows 8 프로젝트. 따라서 Windows 8 프로젝트의 MaxPlatformVersion 8.0입니다. 즉, 참조 관리자 필터링 합니다. Microsoft Visual c + + 런타임 패키지는 Windows 8.1 프로젝트에 대 한 오류를 throw 하는 MSBuild 때는 [!INCLUDE[win81](../debugger/includes/win81_md.md)] 프로젝트에서 참조 합니다. 참고:이 요소는 지원부터 [!INCLUDE[vs_dev12](../data-tools/includes/vs_dev12_md.md)]합니다.  
  
7.  AppliesTo: 적용 되는 Visual Studio 프로젝트 유형을 지정 하 여 참조 관리자에서 사용할 수 있는 Sdk를 지정 합니다. 9 개의 값은 인식: WindowsAppContainer, VisualC, VB, CSharp, WindowsXAML, JavaScript, 관리 및 네이티브 합니다. SDK 작성자 사용 하 여 하 고 ("+'), 또는 ("&#124;") 하지 않습니다 ("! ") SDK에 적용 되는 프로젝트 형식의 범위에 정확 하 게 지정 하는 연산자입니다.  
  
     WindowsAppContainer 식별에 대 한 프로젝트 [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] 앱입니다.  
  
8.  SupportPrefer32Bit: 지원 되는 값은 "True" 및 "False"입니다. 기본값은 "True"입니다. MSBuild에 대 한 오류를 반환 값은 "False"로 설정 된 경우 [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] 프로젝트 (또는 데스크톱 프로젝트에 대 한 경고) SDK를 참조 하는 프로젝트에 Prefer32Bit 사용 하도록 설정 합니다. Prefer32Bit에 대 한 자세한 내용은 참조 [빌드 페이지, 프로젝트 디자이너 (C#)](../ide/reference/build-page-project-designer-csharp.md) 또는 [컴파일 페이지, 프로젝트 디자이너 (Visual Basic)](../ide/reference/compile-page-project-designer-visual-basic.md)합니다.  
  
9. SupportedArchitectures: 세미콜론으로 구분 된 목록 아키텍처를 지 원하는 SDK의 합니다. MSBuild 대상된 SDK 아키텍처 사용 하는 프로젝트에 지원 되지 않으면 경고를 표시 합니다. 이 특성이 지정 되지 않으면 MSBuild는 이러한 유형의 경고를 표시 되지 않습니다.  
  
10. SupportsMultipleVersions:이 특성 설정 된 경우 **오류** 또는 **경고**, MSBuild 나타냅니다 같은 프로젝트 같은 SDK 제품군의 여러 버전을 참조할 수 없습니다. 이 특성이 존재 하지 않거나로 설정 된 경우 **허용**, MSBuild는 이러한 유형의 오류 또는 경고가 표시 되지 않습니다.  
  
11. AppX: 디스크에서 Windows 구성 요소 라이브러리에 대 한 응용 프로그램 패키지에 대 한 경로 지정합니다. 이 값은 로컬 디버깅 하는 동안 Windows 구성 요소 라이브러리의 등록 구성 요소에 전달 합니다. 파일 이름에 대 한 명명 규칙은 **\< 회사>. \< 제품>. \< 아키텍처>. \< 구성>. \< 버전>.appx**합니다. 구성 및 아키텍처는 Windows 구성 요소 라이브러리에는 적용 되지 경우 특성 이름 및 특성 값에 선택적입니다. 이 값은 Windows 구성 요소 라이브러리에만 적용할 수 있습니다.  
  
12. CopyRedistToSubDirectory: 앱 패키지 루트에 상대적인 \redist 폴더에서 파일을 복사할 위치 지정 (즉,는 **패키지 위치** 응용 프로그램 패키지 만들기 마법사에서 선택) 및 런타임 레이아웃 루트입니다. 기본 위치는 응용 프로그램 패키지와 F5 레이아웃의 루트입니다.  
  
13. DependsOn:이 SDK 의존 하는 Sdk를 정의 하는 SDK id의 목록. 이 특성은 참조 관리자의 세부 정보 창에 나타납니다.  
  
14. MoreInfo: 도움말 및 자세한 정보를 제공 하는 웹 페이지 URL입니다. 이 값은 참조 관리자의 오른쪽 창에서 추가 정보 링크에 사용 됩니다.  
  
15. 등록 유형: WinMD 등록 응용 프로그램 매니페스트에서 지정 되며 해당 구현 DLL에 있는 네이티브 WinMD에 대 한 필요 합니다.  
  
16. 파일 참조: 네이티브 Winmd 않거나 컨트롤이 들어 있는 참조만 지정. 참조 컨트롤에 포함 되는지 여부를 지정 하는 방법에 대 한 정보를 참조 하십시오. [도구 상자 항목의 위치를 지정 하](#ToolboxItems) 아래입니다.  
  
##  <a name="a-nametoolboxitemsa-specifying-the-location-of-toolbox-items"></a><a name="ToolboxItems"></a> 도구 상자 항목의 위치를 지정합니다.  
 SDKManifest.xml 스키마의 ToolBoxItems 요소 플랫폼와 확장 Sdk에서 범주 및 도구 상자 항목의 위치를 지정합니다. 다음 예제에서는 서로 다른 위치를 지정 하는 방법을 보여 줍니다. WinMD 또는 DLL 참조에 적용 됩니다.  
  
1.  도구 상자 기본 범주에 컨트롤을 배치 합니다.  
  
    ```  
    <File Reference = “sample.winmd”>  
        <ToolboxItems VSCategory = “Toolbox.Default”/>       
    </File>  
    ```  
  
2.  특정 범주 이름과 아래의 컨트롤을 배치 합니다.  
  
    ```  
    <File Reference = “sample.winmd”>  
        <ToolboxItems VSCategory= “MyCategoryName”/>  
    </File>  
    ```  
  
3.  특정 범주 이름 아래에서 컨트롤을 배치 합니다.  
  
    ```  
    <File Reference = “sample.winmd”>  
        <ToolboxItems VSCategory = “Graph”>  
        <ToolboxItems/>  
        <ToolboxItems VSCategory = “Data”>  
        <ToolboxItems />  
    </File>  
    ```  
  
4.  Blend 및 Visual Studio에서 서로 다른 범주 이름 아래에서 컨트롤을 배치 합니다.  
  
    ```  
    // Blend accepts a slightly different structure for the category name because it allows a path rather than a single category.  
    <File Reference = “sample.winmd”>  
        <ToolboxItems VSCategory = “Graph” BlendCategory = “Controls/sample/Graph”>   
        <ToolboxItems />  
    </File>  
    ```  
  
5.  Blend 및 Visual Studio에서 다르게 특정 컨트롤을 열거 합니다.  
  
    ```  
    <File Reference = “sample.winmd”>  
        <ToolboxItems VSCategory = “Graph”>  
        <ToolboxItems/>  
        <ToolboxItems BlendCategory = “Controls/sample/Graph”>  
        <ToolboxItems/>  
    </File>  
    ```  
  
6.  Visual Studio 일반 경로에서 또는 모든 컨트롤 그룹에만 중지 하 고 특정 컨트롤을 열거 합니다.  
  
    ```  
    <File Reference = “sample.winmd”>  
        <ToolboxItems VSCategory = “Toolbox.Common”>  
        <ToolboxItems />  
        <ToolboxItems VSCategory = “Toolbox.All”>  
        <ToolboxItems />  
    </File>  
    ```  
  
7.  특정 컨트롤을 열거 하 고 괄호 없이 ChooseItems에는 특정 집합에만 표시 도구 상자에 있는 것입니다.  
  
    ```  
    <File Reference = “sample.winmd”>  
        <ToolboxItems VSCategory = “Toolbox.ChooseItemsOnly”>  
        <ToolboxItems />  
    </File>  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [연습: c + +를 사용 하 여 SDK 만들기](../extensibility/walkthrough-creating-an-sdk-using-cpp.md)   
 [연습: C# 또는 Visual Basic을 사용 하 여 SDK 만들기](../extensibility/walkthrough-creating-an-sdk-using-csharp-or-visual-basic.md)   
 [프로젝트에서 참조 관리](../ide/managing-references-in-a-project.md)