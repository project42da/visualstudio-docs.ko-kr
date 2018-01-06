---
title: "소프트웨어 개발 키트 만들기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 8496afb4-1573-4585-ac67-c3d58b568a12
caps.latest.revision: "54"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 4ea17b02cfa2e987c4a3c02acddf838001b4ae2f
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="creating-a-software-development-kit"></a>소프트웨어 개발 키트 만들기
소프트웨어 개발 키트 (SDK)은 Visual Studio에서 단일 항목으로 참조할 수 있는 Api의 컬렉션입니다. **참조 관리자** 대화 상자는 프로젝트에 관련 된 모든 Sdk를 나열 합니다. 프로젝트에 SDK를 추가 하면 Api는 Visual Studio에서 사용할 수 있습니다.  
  
 Sdk는 다음과 같은 두 종류가 있습니다.  
  
-   플랫폼 Sdk는 플랫폼에 대 한 앱 개발을 위한 필수 구성 요소는 있습니다. 예를 들어는 [!INCLUDE[win81](../debugger/includes/win81_md.md)] SDK 개발 해야 합니다. [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] 앱.  
  
-   확장 Sdk는 한 플랫폼을 확장 하지만 해당 플랫폼에 대 한 앱 개발을 위한 필수 아닌 선택적 구성 요소입니다.  
  
 다음 섹션에서는 Sdk 및 플랫폼 SDK를 만드는 방법의 일반적인 인프라를 설명 하 고 확장 SDK입니다.  
  
-   [플랫폼 Sdk](#PlatformSDKs)  
  
-   [확장 Sdk](#ExtensionSDKs)  
  
##  <a name="PlatformSDKs"></a>플랫폼 Sdk  
 플랫폼 Sdk는 한 플랫폼에 대 한 앱을 개발 해야 합니다. 예를 들어는 [!INCLUDE[win81](../debugger/includes/win81_md.md)] SDK는 응용 프로그램을 개발 해야 [!INCLUDE[win81](../debugger/includes/win81_md.md)]합니다.  
  
### <a name="installation"></a>설치  
 HKLM\Software\Microsoft\Microsoft Sdk에서 모든 플랫폼 Sdk가 설치\\[TPI] \v [TPV]\\ @InstallationFolder [SDK 루트] = 합니다. 따라서는 [!INCLUDE[win81](../debugger/includes/win81_md.md)] HKLM\Software\Microsoft\Microsoft SDKs\Windows\v8.1에 SDK가 설치 되어 있습니다.  
  
### <a name="layout"></a>레이아웃  
 플랫폼 Sdk에는 다음과 같은 레이아웃을 포함 됩니다.  
  
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
|References 폴더|에 대해 코딩 될 수 있는 Api를 포함 하는 이진 파일을 포함 합니다. 여기에 Windows 메타 데이터 (WinMD) 파일 또는 어셈블리 포함 합니다.|  
|DesignTime 폴더|사전-run/디버깅 타임에만 필요한 파일이 포함 되어 있습니다. XML 문서, 라이브러리, 머리글, 디자인 타임 이진 도구 상자, MSBuild 아티팩트 등 이러한가 포함 될 수 있습니다.<br /><br /> XML 문서 \DesignTime 폴더에 배치 이상적으로 적절 하 게 하지만 참조에 대 한 XML 문서는 Visual Studio에서 참조 파일과 함께 배치 될 계속 됩니다. 예를 들어 XML 문서에 대 한 참조 \References\\[구성]\\[arch]\sample.dll \References 됩니다\\[구성]\\[arch]\sample.xml, 되 고 해당 문서의 지역화 된 버전 됩니다 \References\\[구성]\\[보관]\\[locale]\sample.xml 합니다.|  
|구성 폴더|세 개의 폴더가 될 수 있습니다: 디버그, 소매 및 CommonConfiguration 합니다. SDK 작성자 SDK 소비자를 대상으로 하는 구성에 관계 없이 동일한 SDK 파일 집합에 사용, 될 해야 하는 경우 CommonConfiguration 파일을 배치할 수 있습니다.|  
|아키텍처 폴더|모든 지원 되는 아키텍처 폴더 존재할 수 있습니다. Visual Studio에서는 다음 아키텍처: x86, x64, ARM 및 neutral입니다. 참고: Win32 x86에 매핑되고 AnyCPU 중립에 매핑됩니다.<br /><br /> MSBuild는 플랫폼 Sdk에 대 한 \CommonConfiguration\neutral 인 경우에 찾습니다.|  
|SDKManifest.xml|이 파일에 Visual Studio SDK를 사용 해야 방법을 설명 합니다. 에 대 한 SDK 매니페스트에 살펴보고 [!INCLUDE[win81](../debugger/includes/win81_md.md)]:<br /><br /> `<FileList             DisplayName = "Windows"             PlatformIdentity = "Windows, version=8.1"             TargetFramework = ".NET for Windows Store apps, version=v4.5.1; .NET Framework, version=v4.5.1"             MinVSVersion = "14.0">              <File Reference = "Windows.winmd">                <ToolboxItems VSCategory = "Toolbox.Default" />             </File> </FileList>`<br /><br /> **표시 이름:** 찾아보기 목록에 개체 브라우저를 표시 하는 값입니다.<br /><br /> **PlatformIdentity:** 이 특성의 존재 여부 Visual Studio 및 MSBuild는 SDK 플랫폼 SDK 이며 알립니다 여기에서 추가 된 참조를 복사 하지 않아야 함을 로컬로 합니다.<br /><br /> **TargetFramework:** 만이 값에 지정 된 대로 동일한 프레임 워크를 대상으로 하는 투영 하 되도록 Visual Studio에서이 특성은 사용 특성 SDK를 사용할 수 있습니다.<br /><br /> **MinVSVersion:** 이 특성에 적용 되 고 Sdk를 사용 하도록 Visual Studio에서 사용 됩니다.<br /><br /> **참조:** 이 특성 컨트롤이 포함 된 참조에만 지정 되어야 합니다. 참조 컨트롤 포함 되는지 여부를 지정 하는 방법에 대 한 내용은 다음을 참조 합니다.|  
  
##  <a name="ExtensionSDKs"></a>확장 Sdk  
 다음 섹션에서는 확장 SDK를 배포 하기 위해 수행 해야 합니다.  
  
### <a name="installation"></a>설치  
 확장 Sdk는 레지스트리 키를 지정 하지 않고 특정 사용자에 대해 또는 모든 사용자가 설치할 수 있습니다. 모든 사용자에 대 한 SDK를 설치 하려면 다음 경로 사용 합니다.  
  
 `%Program Files%\Microsoft SDKs\<target platform>\v<platform version number>\ExtensionSDKs`  
  
 사용자 고유의 설치의 경우 다음 경로 사용 합니다.  
  
 `%USERPROFILE%\AppData\Local\Microsoft SDKs\<target platform>\v<platform version number>\ExtensionSDKs`  
  
 다른 위치를 사용 하려는 경우 다음 두 가지 중 하나를 수행 해야 합니다.  
  
1.  레지스트리 키에 지정 합니다.  
  
     `HKLM\Software\Microsoft\Microsoft SDKs\<target platform>\v<platform version number>\ExtensionSDKs\<SDKName>\<SDKVersion>\`  
  
     값 (기본값) 하위 키를 추가 하 고 `<path to SDK><SDKName><SDKVersion>`합니다.  
  
2.  추가 MSBuild 속성 `SDKReferenceDirectoryRoot` 프로젝트 파일입니다. 이 속성의 값은 세미 콜론 구분 된 목록에는 확장 Sdk 참조 하려는 거주 하는 디렉터리입니다.  
  
### <a name="installation-layout"></a>설치 레이아웃  
 확장 Sdk에는 다음과 같은 설치 레이아웃  
  
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
  
1.  \\< SDKName\>\\< s d k v\>: 이름 및 버전의 확장 SDK SDK 루트 경로에 해당 폴더 이름은에서 파생 됩니다. 이 id를 표시 하는 Visual Studio 및 MSBuild이이 id를 사용 하 여 디스크에 SDK를 찾을 수는 **속성** 창 및 **참조 관리자** 대화 상자.  
  
2.  References 폴더: Api를 포함 하는 이진 파일입니다. Windows 메타 데이터 (WinMD) 파일 또는 어셈블리를 사용할 수 있습니다.  
  
3.  Redist 폴더: 런타임/디버깅을 위해 필요 하 고 사용자의 응용 프로그램의 일부로 패키지 될 해야 하는 파일입니다. \Redist 아래 모든 이진 파일을 배치 해야\\< 구성\>\\< arch\>, 이진 이름 고유성을 보장 하려면 다음과 같은 형식에 있어야 합니다:  **\<회사 >.\< 제품 > 합니다. \<목적 > 합니다. \<확장 >**합니다. 예를 들어: Microsoft.Cpp.Build.dll 다른 Sdk (예: javascript, css, pri, xaml, png 및 jpg 파일)에서 파일 이름으로 이름이 충돌할 수 있습니다 하는 모든 파일 \redist 아래를 배치할\\< 구성\>\\< arch\> \\< sdkname\>\ XAML와 연결 된 파일을 제외 하 고 제어 합니다. 이러한 파일은 \redist 아래 저장할\\< 구성\>\\< arch\>\\< componentname\>\\합니다.  
  
4.  DesignTime 폴더: 유일한 사전-run/디버깅에 필요한 파일이 고 사용자의 응용 프로그램의 일부로 패키지할 수 없습니다. 이러한 XML 문서, 라이브러리, 머리글, 디자인 타임 이진 도구 상자, MSBuild 아티팩트 등 수 있습니다. 네이티브 프로젝트 사용가지고 있어야 되는 모든 SDK는 *SDKName*.props 파일입니다. 다음이 유형의 파일의 예제를 보여 줍니다.  
  
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
  
     XML 참조 문서 참조 파일과 함께 배치 됩니다. 예를 들어에 대 한 XML 참조 문서는 **\References\\< 구성\>\\< arch\>\sample.dll** 어셈블리가 **\References\\ < 구성\>\\< arch\>\sample.xml**, 해당 문서의 지역화 된 버전 및 **\References\\< 구성\>\\< arch\>\\< 로캘\>\sample.xml**합니다.  
  
5.  구성 폴더: 세 개의 하위 폴더가: 디버그, 정품 및 CommonConfiguration 합니다. SDK 작성자는 동일한 집합 SDK 파일을 사용 해야 하, SDK 소비자의 대상 구성에 관계 없이 때 CommonConfiguration 파일을 배치할 수 있습니다.  
  
6.  아키텍처 폴더: 아키텍처는 지원: x86, x64, ARM, neutral입니다. Win32 x86에 매핑되고 AnyCPU 중립에 매핑됩니다.  
  
### <a name="sdkmanifestxml"></a>SDKManifest.xml  
 이 파일에 Visual Studio SDK를 사용 해야 방법을 설명 합니다. 다음은 예제입니다.  
  
```  
<FileList>  
DisplayName = "My SDK"  
ProductFamilyName = "My SDKs"  
TargetFramework = ".NETCore, version=v4.5.1; .NETFramework, version=v4.5.1"  
MinVSVersion = "14.0"  
MaxPlatformVersion = "8.1"  
AppliesTo = "WindowsAppContainer + WindowsXAML"  
SupportPrefer32Bit = "True"  
SupportedArchitectures = "x86;x64;ARM"  
SupportsMultipleVersions = "Error"  
CopyRedistToSubDirectory = "."  
DependsOn = "SDKB, version=2.0"  
MoreInfo = "http://msdn.microsoft.com/MySDK">  
<File Reference = "MySDK.Sprint.winmd" Implementation = "XNASprintImpl.dll">  
<Registration Type = "Flipper" Implementation = "XNASprintFlipperImpl.dll" />  
<Registration Type = "Flexer" Implementation = "XNASprintFlexerImpl.dll" />  
<ToolboxItems VSCategory = "Toolbox.Default" />  
</File>  
</FileList>  
```  
  
 다음 목록에는 파일의 요소를 제공합니다.  
  
1.  표시 이름: 참조 관리자, 솔루션 탐색기, 개체 브라우저 및 Visual Studio에 대 한 사용자 인터페이스의 다른 위치에 표시 되는 값입니다.  
  
2.  ProductFamilyName: 전체 SDK 제품 이름입니다. 예를 들어는 [!INCLUDE[winjs_long](../debugger/includes/winjs_long_md.md)] SDK "Microsoft.WinJS" SDK 제품 패밀리의 동일한 제품군에 속하는 "Microsoft.WinJS.1.0" 및 "Microsoft.WinJS.2.0" 라고 합니다. 이 특성에는 Visual Studio 및 MSBuild 해당 연결을 만들 수 있습니다. 이 특성이 존재 하지 않으면 SDK 이름이 며 제품 제품군 이름으로 사용 됩니다.  
  
3.  FrameworkIdentity:이 특성의 값을 사용 중인 응용 프로그램 매니페스트에 넣을 하나 이상의 Windows 구성 요소 라이브러리에 대 한 종속성을 지정 합니다. 이 특성은 Windows 구성 요소 라이브러리에만 적용할 수 있습니다.  
  
4.  TargetFramework: 참조 관리자, 도구 상자에서 사용할 수 있는 Sdk를 지정 합니다. 예를 들어 이것은 대상 프레임 워크 모니커 세미콜론으로 구분 된 목록 ".NET Framework, version = v2.0;.NET Framework, version = v4.5.1"입니다. 동일한 대상 프레임 워크의 여러 버전을 지정 하는 경우 참조 관리자는 필터링 용도로 지정 된 가장 낮은 버전을 사용 합니다. 예를 들어 경우 ".NET Framework, version = v2.0;.NET Framework, version v4.5.1 =" 지정, 참조 관리자를 사용 합니다 ".NET Framework, version = v2.0"입니다. 특정 대상 프레임 워크 프로필을 지정 하는 경우 해당 프로필에만 필터링 용도로 참조 관리자가 사용 됩니다. 예를 들어 "Silverlight, 버전 = v4.0, profile WindowsPhone =" 지정 된 참조 관리자는 Windows Phone 프로필;에 대 한 필터 전체 Silverlight 4.0 Framework를 대상으로 하는 프로젝트는 SDK 참조 관리자에 표시 되지 않습니다.  
  
5.  MinVSVersion: 최소 Visual Studio 버전입니다.  
  
6.  MaxPlatformVerson: 확장 SDK는 작동 하지는 플랫폼 버전을 지정할 최대 대상 플랫폼 버전을 사용 해야 합니다. 예를 들어 Microsoft Visual c + + 런타임 패키지 v11.0만 Windows 8 프로젝트에서 참조 하도록 합니다. 따라서 Windows 8 프로젝트의 MaxPlatformVersion 8.0입니다. 즉, Windows 8.1 프로젝트에 대 한 필터링 된 Microsoft Visual c + + 런타임 패키지 참조 관리자 MSBuild 오류를 발생 시키는 경우는 [!INCLUDE[win81](../debugger/includes/win81_md.md)] 프로젝트에서 참조 합니다. 참고:이 요소는 지원부터 [!INCLUDE[vs_dev12](../extensibility/includes/vs_dev12_md.md)]합니다.  
  
7.  AppliesTo: 적용 되는 Visual Studio 프로젝트 유형을 지정 하 여 참조 관리자에서 사용할 수 있는 Sdk를 지정 합니다. 9 개의 값이 인식 되: WindowsAppContainer, VisualC, VB, CSharp, WindowsXAML, JavaScript, 관리 및 네이티브 합니다. SDK 작성자 צ ְ ײ 및 ("+'), 또는 ("&#124;"), 없습니다 ("! ") SDK에 적용 되는 프로젝트 형식의 범위 정확 하 게 지정 하는 연산자입니다.  
  
     WindowsAppContainer 식별에 대 한 프로젝트 [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] 앱.  
  
8.  SupportPrefer32Bit: 지원 되는 값은 "True" 및 "False"입니다. 기본값은 "True"입니다. MSBuild에 대 한 오류를 반환 값을 "False"로 설정 [!INCLUDE[win8_appname_long](../debugger/includes/win8_appname_long_md.md)] 프로젝트 (또는 데스크톱 프로젝트에 대 한 경고) SDK를 참조 하는 프로젝트에 Prefer32Bit 사용 하도록 설정 합니다. Prefer32Bit에 대 한 자세한 내용은 참조 [빌드 페이지, 프로젝트 디자이너 (C#)](../ide/reference/build-page-project-designer-csharp.md) 또는 [컴파일 페이지, 프로젝트 디자이너 (Visual Basic)](../ide/reference/compile-page-project-designer-visual-basic.md)합니다.  
  
9. SupportedArchitectures: 세미콜론으로 구분한 목록 SDK는 지원 아키텍처입니다. MSBuild 대상된 SDK 아키텍처가 사용 중인 프로젝트에서 지원 되지 않으면 경고를 표시 합니다. 이 특성을 지정 하지 않은 경우 MSBuild는 이러한 유형의 경고를 표시 되지 않습니다.  
  
10. SupportsMultipleVersions:이 특성은로 설정 하는 경우 **오류** 또는 **경고**, MSBuild 나타냅니다 동일한 프로젝트 동일한 SDK 제품군의 여러 버전을 참조할 수 없습니다. 이 특성이 존재 하지 않거나로 설정 되어 **허용**, MSBuild는 이러한 유형의 오류 또는 경고가 표시 되지 않습니다.  
  
11. AppX: 디스크에서 Windows 구성 요소 라이브러리에 대 한 앱 패키지에 대 한 경로 지정합니다. 이 값은 로컬 디버깅 하는 동안 Windows 구성 요소 라이브러리의 등록 구성 요소에 전달 합니다. 파일 이름에 대 한 명명 규칙은  **\<회사 >.\< 제품 > 합니다. \<아키텍처 >. \<구성 >. \<버전 >.appx**합니다. 구성 및 아키텍처는 Windows 구성 요소 라이브러리에 적용 하지 특성 이름 및 특성 값의 경우 선택 사항입니다. 이 값은 Windows 구성 요소 라이브러리에만 적용할 수 있습니다.  
  
12. CopyRedistToSubDirectory: 앱 패키지 루트에 상대적인 \redist 폴더에서 파일을 복사할 위치 지정 (즉,는 **패키지 위치** 응용 프로그램 패키지 만들기 마법사에서 선택) 및 런타임 레이아웃 루트입니다. 기본 위치는 응용 프로그램 패키지 및 F5 레이아웃의 루트입니다.  
  
13. DependsOn:이 SDK 의존 하는 Sdk를 정의 하는 SDK id의 목록. 이 특성은 참조 관리자의 세부 정보 창에 나타납니다.  
  
14. MoreInfo: 자세한 정보 및 도움말을 제공 하는 웹 페이지 URL입니다. 이 값은 참조 관리자의 오른쪽 창에서 추가 정보 링크에 사용 됩니다.  
  
15. 등록 유형: WinMD 등록 응용 프로그램 매니페스트에서 지정 되며 정수 구현 DLL에 네이티브 WinMD에 대 한 필요 합니다.  
  
16. 파일 참조: 지정 된 컨트롤이 포함 파일이 나 네이티브 Winmd 참조만. 참조 컨트롤 포함 되는지 여부를 지정 하는 방법에 대 한 정보를 참조 하십시오. [도구 상자 항목의 위치 지정](#ToolboxItems) 아래 합니다.  
  
##  <a name="ToolboxItems"></a>도구 상자 항목의 위치 지정  
 SDKManifest.xml 스키마의 ToolBoxItems 요소 플랫폼 및 확장 Sdk 모두에 범주 및 도구 상자 항목의 위치를 지정합니다. 다음 예에서는 서로 다른 위치를 지정 하는 방법을 보여 줍니다. WinMD 또는 DLL 참조에 적용 됩니다.  
  
1.  도구 상자 기본 범주에 컨트롤을 배치 합니다.  
  
    ```  
    <File Reference = "sample.winmd">  
        <ToolboxItems VSCategory = "Toolbox.Default"/>       
    </File>  
    ```  
  
2.  특정 범주 이름에서 컨트롤을 배치 합니다.  
  
    ```  
    <File Reference = "sample.winmd">  
        <ToolboxItems VSCategory= "MyCategoryName"/>  
    </File>  
    ```  
  
3.  특정 범주의 이름 아래에서 컨트롤을 배치 합니다.  
  
    ```  
    <File Reference = "sample.winmd">  
        <ToolboxItems VSCategory = "Graph">  
        <ToolboxItems/>  
        <ToolboxItems VSCategory = "Data">  
        <ToolboxItems />  
    </File>  
    ```  
  
4.  Blend 및 Visual Studio의 다른 범주 이름 아래에서 컨트롤을 배치 합니다.  
  
    ```  
    // Blend accepts a slightly different structure for the category name because it allows a path rather than a single category.  
    <File Reference = "sample.winmd">  
        <ToolboxItems VSCategory = "Graph" BlendCategory = "Controls/sample/Graph">   
        <ToolboxItems />  
    </File>  
    ```  
  
5.  Blend 및 Visual Studio에서 다르게 특정 컨트롤을 열거 합니다.  
  
    ```  
    <File Reference = "sample.winmd">  
        <ToolboxItems VSCategory = "Graph">  
        <ToolboxItems/>  
        <ToolboxItems BlendCategory = "Controls/sample/Graph">  
        <ToolboxItems/>  
    </File>  
    ```  
  
6.  특정 컨트롤을 열거 하 고 Visual Studio 일반 경로에서 하거나는 모든 컨트롤 그룹에 배치 합니다.  
  
    ```  
    <File Reference = "sample.winmd">  
        <ToolboxItems VSCategory = "Toolbox.Common">  
        <ToolboxItems />  
        <ToolboxItems VSCategory = "Toolbox.All">  
        <ToolboxItems />  
    </File>  
    ```  
  
7.  특정 컨트롤을 열거 하 고 없이도 특정 집합만 ChooseItems에 표시 된 도구 상자에 있는 것입니다.  
  
    ```  
    <File Reference = "sample.winmd">  
        <ToolboxItems VSCategory = "Toolbox.ChooseItemsOnly">  
        <ToolboxItems />  
    </File>  
    ```  
  
## <a name="see-also"></a>참고 항목  
 [연습: c + +를 사용 하 여 SDK 만들기](../extensibility/walkthrough-creating-an-sdk-using-cpp.md)   
 [연습: C# 또는 Visual Basic을 사용 하 여 SDK 만들기](../extensibility/walkthrough-creating-an-sdk-using-csharp-or-visual-basic.md)   
 [프로젝트의 참조 관리](../ide/managing-references-in-a-project.md)