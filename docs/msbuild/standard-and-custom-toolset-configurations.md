---
title: "표준 및 사용자 지정 도구 집합 구성 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "MSBuild, 사용자 지정 도구 집합 구성"
  - "MSBuild, msbuild.exe.config"
ms.assetid: 15a048c8-5ad3-448e-b6e9-e3c5d7147ed2
caps.latest.revision: 31
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 31
---
# 표준 및 사용자 지정 도구 집합 구성
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

MSBuild 도구 집합은 작업, 대상 및 응용 프로그램 프로젝트를 만드는 데 사용할 수 있는 도구에 대한 참조를 포함 합니다.  MSBuild는 표준 도구 집합을 포함하지만 사용자 지정 도구 집합을 만들 수도 있습니다.  도구 집합을 지정하는 방법에 대한 자세한 내용은 [도구 집합\(ToolsVersion\)](../msbuild/msbuild-toolset-toolsversion.md)을 참조하십시오.  
  
## 표준 도구 집합 구성  
 MSBuild 12.0은 아래와 같은 표준 도구 집합을 포함합니다.  
  
|ToolsVersion|도구 집합 경로\(MSBuildToolsPath 또는 MSBuildBinPath 빌드 속성에 지정된 경우\)|  
|------------------|------------------------------------------------------------------|  
|2.0|*Windows installation path*\\Microsoft.Net\\Framework\\v2.0.50727\\|  
|3.5|*Windows installation path*\\Microsoft.NET\\Framework\\v3.5\\|  
|4.0|*Windows installation path*\\Microsoft.NET\\Framework\\v4.0.30319\\|  
|12.0|*%ProgramFiles%*\\MSBuild\\12.0\\bin|  
  
 `ToolsVersion` 값은 어떤 도구 집합이 Visual Studio에서 생성한 프로젝트에 의해 사용될지 결정합니다.   [!INCLUDE[vs_dev12](../data-tools/includes/vs_dev12_md.md)] 에서 기본 값은 "12.0" 입니다.\(프로젝트 파일에 어떤 버전이 지정되어 있는지와는 관계없이\) 그러나 명령 프롬프트에서 **\/toolsversion** 스위치를 사용함으로서 특성을 오버라이드 할 수 있습니다.  이 특성과 `ToolsVersion` 을 지정하는 다른방법에 대한 자세한 정보는 [ToolsVersion 설정 재정의](../msbuild/overriding-toolsversion-settings.md) 를 참조하십시오.  
  
 만약 `ToolsVersion` 가 정의 되지 않았더라도, 레지스트리 키 HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\MSBuild\\\<Version Number\>\\DefaultToolsVersion 는 `ToolsVersion` 를 항상 2.0 으로 정의합니다.  
  
 아래의 레지스트리 키는 MSBuild.exe.의 설치 경로를 지정합니다.  
  
|레지스트리 키|키 이름|문자열 키 값|  
|-------------|----------|-------------|  
|\\HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\MSBuild\\ToolsVersions\\2.0\\|MSBuildToolsPath|.NET Framework 2.0 Install Path|  
|\\HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\ MSBuild\\ToolsVersions\\3.5\\|MSBuildToolsPath|.NET Framework 3.5 Install Path|  
|\\HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\ MSBuild\\ToolsVersions\\4.0\\|MSBuildToolsPath|.NET Framework 4 Install Path|  
|\\HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\ MSBuild\\ToolsVersions\\12.0\\|MSBuildToolsPath|MSBuild Install Path|  
  
### 하위 도구 집합  
 위의 표의 레지스트리 키에 하위 키가 있으면 MSBuild는 부모 도구 집합에서 경로를 재정의 할 수 있는 하위 도구 집합 경로를 결정하기 위해 그것을 사용합니다.  다음은 하위키의 예제입니다.  
  
 \\HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\MSBuild\\ToolsVersions\\12.0\\12.0  
  
 어떤 속성이라도 기본 도구 집합과 선택된 하위 도구 집합 둘다에 정의되어 있으면, 하위 도구 집합에 정의된 속성이 사용됩니다.  예를 들어 MSBuild 4.0 toolset이 `SDK40ToolsPath` 를 7.0A SDK를 가르키도록 정의한 반면에 MSBuild 4.0\\11.0 도구 집합은 같은 속성을 8.0A SDK를 가르키도록 정의합니다.  `VisualStudioVersion` 가 설정되어 있지 않은 경우 `SDK40ToolsPath` 가 7.0A를 카르켜도 `VisualStudioVersion` 가 11.0으로 설정되어 있으면, 속성은 8.0A 를 가르킵니다.  
  
 `VisualStudioVersion` 빌드 속성은 하위 도구 집합의 활성화 여부를 나타냅니다.  예를 들어, "12.0"의 `VisualStudioVersion` 값은 MSBuild 12.0 하위 도구 집합을 지정 합니다.  자세한 내용은 [도구 집합\(ToolsVersion\)](../msbuild/msbuild-toolset-toolsversion.md) 의 하위 도구 집합 섹션을 참조하십시오.  
  
> [!NOTE]
>  이러한 설정을 변경하는 것은 피하는 것이 좋습니다.  그러나 다음 단원에서 설명하는 것처럼 사용자 고유의 설정을 추가하고 컴퓨터 전체 사용자 지정 도구 집합 정의를 정의할 수 있습니다.  
  
## 사용자 지정 도구 집합 정의  
 표준 도구 집합에서 빌드 요구 사항을 충족하지 않는 경우 사용자 지정 도구 집합을 만들 수 있습니다.  예를 들어 [!INCLUDE[vcprvc](../debugger/includes/vcprvc_md.md)] 프로젝트를 빌드하기위한 별도의 시스템을 가지고 있어야 하는 빌드 랩 시나리오가 있을 수 있습니다.  사용자 도구 집합을 사용하여, 프로젝트를 생성하거나 MSBuild.exe를 실행 할때 사용자 지정 값을 `ToolsVersion` 특성에 할당할 수 있습니다.  이렇게 함으로서, 도구 집합을 사용하는 어떤 프로젝트를 위해 사용되는사용자 지정 도구 집합 속성을 지정하는 것 뿐만 아니라 디렉터리로부터 .targets 파일을 가져오기 위해 `$(MSBuildToolsPath)` 속성을 사용할 수 있습니다.  
  
 구성 파일에 MSBuild.exe에 대한 사용자 지정 도구 집합을 정의합니다.\(또는 사용하고있는 경우 MSBuild 엔진을 호스팅하는 사용자 지정 도구에 대해\)  예를 들어, ToolsVersion 12.0의 기본 동작을 재정의하려는 경우 MSBuild.exe에 대한 구성 파일은 아래의 도구 집합을 포함할 수 있습니다.  
  
```  
<msbuildToolsets default="12.0">  
   <toolset toolsVersion="12.0">  
      <property name="MSBuildToolsPath"   
        value="C:\SpecialPath" />  
   </toolset>  
</msbuildToolsets>  
```  
  
 또한 `<msbuildToolsets>` 는 구성파일내에 아래와 같이 반드시 지정됩니다.  
  
```  
<configSections>  
   <section name="msbuildToolsets"         
       Type="Microsoft.Build.BuildEngine.ToolsetConfigurationSection,   
       Microsoft.Build.Engine, Version=12.0.0.0, Culture=neutral,   
       PublicKeyToken=b03f5f7f11d50a3a"  
   </section>  
</configSections>  
```  
  
> [!NOTE]
>  정확히 읽히기 위해서 `<configSections>` 는 `<configuration>` 섹션에서 반드시 첫번째 세부항목이어야 합니다.  
  
 `ToolsetConfigurationSection`은 사용자 구성에 대한 MSBuild 호스트에 의해 사용될 수 있는 사용자 지정 구성 섹션입니다.  사용자 지정 도구 집합을 사용할 경우 다른 작업 없이 호스트는 구성 파일 항목을 제공하기만 하면 빌드 엔진을 초기화할 수 있습니다.  레지스트리의 엔트리를 정의함으로서 MSBuild.exe, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 및 MSBuild의 모든 호스트에 적용되는 컴퓨터 전체 도구 집합을 지정할 수 있습니다.  
  
> [!NOTE]
>  구성 파일이 레지스트리에 이미 정의된 `ToolsVersion` 에 대한 설정을 정의하는 경우, 두 정의는 병합되지 않습니다.  구성파일의 정의가 우선하며 `ToolsVersion` 에 대한 레지스트리의 설정은 무시됩니다.  
  
 다음 속성은 프로젝트에 사용되는 `ToolsVersion` 의 값에만 사용됩니다.  
  
-   **$\(MSBuildBinPath\)** 는 레지스트리 또는 `ToolsVersion` 가 정의된 구성 파일 중 하나에 지정된 `ToolsPath` 값에 설정됩니다.  레지스트리와 해당 구성 파일에서 `$(MSBuildToolsPath)` 설정은 핵심 작업과 대상의 위치를 지정합니다.  프로젝트 파일에서 $\(MSBuildBinPath\) 속성이나 $\(MSBuildToolsPath\) 속성으로 매핑됩니다.  
  
-   `$(MSBuildToolsPath)` 는 구성 파일에 지정된 MSBuildToolsPath 속성에 의해 제공되는 예악된 속성입니다. 이 속성은 `$(MSBuildBinPath)`를 대체합니다.  그러나 `$(MSBuildBinPath)`는 호환성을 위해 계속 제공됩니다. 사용자 지정 도구 집합은 같은 값을 가지지 않는 경우 `$(MSBuildToolsPath)` 또는 `$(MSBuildBinPath)` 중 하나를 반드시 정의해야 합니다.  
  
 MSBuildToolsPath 속성을 추가하기 위해 사용하는 것과 동일한 구문을 사용하여 구성 파일에 사용자 지정 ToolsVersion별 속성을 추가할 수도 있습니다.  이러한 사용자 지정 속성을 프로젝트 파일에서 사용할 수 있게하려면, 구성 파일에 정의된 값의 이름과 같은 이름을 사용합십시오.  구성 파일에 하위 도구 집합이 아닌 도구 집합을 정의할 수 있습니다.  
  
## 참고 항목  
 [도구 집합\(ToolsVersion\)](../msbuild/msbuild-toolset-toolsversion.md)