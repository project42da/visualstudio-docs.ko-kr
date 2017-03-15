---
title: "VSIX 확장 스키마 2.0 참조 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-sdk"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "vsix"
  - "확장 스키마"
ms.assetid: 0da81b98-f5e3-40d3-ba9a-94551378d0b4
caps.latest.revision: 25
caps.handback.revision: 25
ms.author: "gregvanl"
manager: "ghogen"
---
# VSIX 확장 스키마 2.0 참조
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

VSIX 배포 매니페스트 파일에는 VSIX 패키지의 내용을 설명합니다. 스키마 파일 형식이 적용 됩니다. 이 스키마의 버전 2.0 추가 하는 사용자 지정 형식 및 특성을 지원 합니다.  매니페스트의 스키마가 확장 가능 합니다. 매니페스트 로더 이해 하지 못하는 XML 요소 및 특성을 무시 합니다.  
  
> [!IMPORTANT]
>  Visual Studio 2015는 Visual Studio 2010, Visual Studio 2012 또는 Visual Studio 2013 형식에서 VSIX 파일을 로드할 수 있습니다.  
  
## 패키지 매니페스트 스키마  
 매니페스트 XML 파일의 루트 요소는 `<PackageManifest>`, 를 단일 특성을 가진 `Version`, 을 매니페스트 형식 버전입니다. 형식에 주요 변경 내용을 버전 형식을 변경 됩니다. 이 항목에에서 설명 된 매니페스트를 설정 하 여 매니페스트 형식 버전 2.0에 설명는 `Version` 특성 버전 값 \= "2.0"입니다.  
  
### PackageManifest 요소  
 내는 `<PackageManifest>` 루트 요소는 다음과 같은 요소를 사용할 수 있습니다.  
  
-   `<Metadata>` \-메타 데이터 및 패키지 자체에 대 한 광고 정보를 제공 합니다. 하나의 `Metadata` 매니페스트에 요소를 사용할 수 있습니다.  
  
-   `<Installation>` \-이 섹션에는이 확장 패키지를 설치할 수에 설치할 수 있는 응용 프로그램 Sku를 포함 하는 방법을 정의 합니다. 단일 `Installation` 매니페스트에 요소를 사용할 수 있습니다. 매니페스트 있어야는 `Installation` SKU에 요소 또는이 패키지 설치 되지 않습니다.  
  
-   `<Dependencies>` \-이 패키지에 대 한 종속성의 선택적 목록 여기에서 정의 됩니다.  
  
-   `<Assets>` \-이 섹션에는이 패키지 내에 포함 된 자산을 모두 포함 됩니다. 이 섹션에서는 없이이 패키지 콘텐츠를 노출 되지 않습니다.  
  
-   `<AnyElement>*` \-매니페스트 스키마는 다른 요소 수 있을 만큼 유연 합니다. 매니페스트 로더 인식 되지 않으므로 모든 자식 요소는 추가 XmlElement 개체도 확장 관리자 API에서 노출 됩니다. VSIX 확장 이러한 자식 요소를 사용 하 여 Visual Studio에서 실행 되는 코드는 런타임에 액세스할 수 있는 매니페스트 파일에 추가 데이터를 정의할 수 있습니다.<xref:Microsoft.VisualStudio.ExtensionManager.IExtension.AdditionalElements%2A> 및 <xref:Microsoft.VisualStudio.ExtensionManager.IExtension.LocalizedAdditionalElements%2A>을 참조하십시오.  
  
### 메타 데이터 요소  
 이 섹션은 패키지, 해당 id 및 광고 정보에 대 한 메타 데이터입니다.`<Metadata>` 다음과 같은 요소가 포함 되어 있습니다.  
  
-   `<Identity>` \-이 패키지에 대 한 식별 정보를 정의 하 고 다음 특성을 포함 합니다.  
  
    -   `Id` \-이 특성을 만든 사람이 선택한 패키지에 대 한 고유 ID 여야 합니다. 이름은 CLR 유형은 스페이스 동일한 방식으로 정규화 되어야: Company.Product.Feature.Name 합니다.`Id` 특성은 100 자로 제한 됩니다.  
  
    -   `Version` \-이 패키지와 해당 내용의 버전을 정의 합니다. 이 특성은 CLR 어셈블리 버전 관리 형식을 따릅니다: Major.Minor.Build.Revision \(1.2.40308.00\). 더 높은 버전 번호를 사용 하 여 패키지는 패키지에 대 한 업데이트 것으로 간주 됩니다 및 기존 설치 된 버전 위에 설치할 수 있습니다.  
  
    -   `Language` –이 패키지에 대 한 기본 언어 특성과이 매니페스트에에서 텍스트 데이터에 해당 합니다. 이 특성 리소스 어셈블리에 대 한 예를 들어 CLR 로캘 코드 규칙을 따릅니다: en\-, en, fr fr 합니다. 지정할 수 있습니다 `neutral` 를 모든 버전의 Visual Studio에서 실행 되는 언어 중립적인 확장을 선언 합니다. 기본값은 `neutral`입니다.  
  
    -   `Publisher` \-이 특성 회사 또는 개별 이름을이 패키지의 게시자를 식별 합니다.`Publisher` 특성은 100 자로 제한 됩니다.  
  
-   `<DisplayName>` \-이 요소는 확장 관리자 UI에 표시 되는 친숙 한 패키지 이름을 지정 합니다.`DisplayName` 콘텐츠는 최대 100 자입니다.  
  
-   `<Description>` \-이 선택적 요소는 확장 관리자 UI에 표시 되는 패키지와 해당 내용을의 간단한 설명입니다.`Description` 내용은 원하는 되었지만 텍스트를 포함할 수 1000 자로 제한 됨.  
  
-   `<MoreInfo>` \-선택적 요소인이 페이지에 온라인이 패키지에 대 한 전체 설명이 포함 된 URL을 보여 줍니다. 프로토콜은 http로 지정 되어야 합니다.  
  
-   `<License>` \-선택적 요소인이 패키지에 포함 된 라이센스 파일 \(.txt,.rtf\)의 상대 경로 보여 줍니다.  
  
-   `<ReleaseNotes>` \-이 선택적 요소는 릴리스 정보를 표시 하는 웹 사이트에 대 한 URL 또는 else \(.txt,.rtf\) 패키지에 포함 된 릴리스 정보 파일에 상대 경로입니다.  
  
-   `<Icon>` \-선택적 요소인이 패키지에 포함 된 이미지 파일 \(png, bmp, jpeg, ico\)의 상대 경로 보여 줍니다. 32 x 32 픽셀 이어야 합니다 \(또는 해당 크기를 축소할\) 아이콘 이미지 listview UI에에서 나타납니다. 없으면 `Icon` 기본값을 사용 하 여 UI, 요소를 지정 합니다.  
  
-   `<PreviewImage>` \-선택적 요소인이 패키지에 포함 된 이미지 파일 \(png, bmp, jpeg\)의 상대 경로 보여 줍니다. 미리 보기 이미지 200 x 200 픽셀이 고 세부 정보 UI에에서 표시 됩니다. 없으면 `PreviewImage` 기본값을 사용 하 여 UI, 요소를 지정 합니다.  
  
-   `<Tags>` \-이 선택적 요소는 검색 힌트에 사용 되는 추가 세미콜론으로 구분 된 텍스트 태그를 나열 합니다.`Tags` 요소는 최대 100 자입니다.  
  
-   `<GettingStartedGuide>` \-이 선택적 요소는 HTML 파일의 상대 경로 또는 확장 또는이 패키지에 포함 된 콘텐츠를 사용 하는 방법에 대 한 정보를 포함 하는 웹 사이트에 대 한 URL입니다. 이 가이드는 설치 과정의 일부로 실행 됩니다.  
  
-   `<AnyElement>*` \-매니페스트 스키마는 다른 요소 수 있을 만큼 유연 합니다. 매니페스트 로더에 의해 인식 되지 않는 모든 자식 요소는 XmlElement 개체의 목록으로 노출 됩니다. VSIX 확장 수 이러한 자식 요소를 사용 하 여 매니페스트 파일에 추가 데이터를 정의 및 런타임 시이 열거 합니다.  
  
### 설치 요소  
 이 섹션에는이 패키지를 설치 하는 방법 및 응용 프로그램 Sku에 설치할 수를 정의 합니다. 이 섹션에는 다음과 같은 특성이 포함 되어 있습니다.  
  
-   `Experimental` \-이 특성을 모든 사용자에 대해 현재 설치 된 확장 있지만 동일한 컴퓨터에 업데이트 된 버전을 개발 하는 경우 true로 설정 합니다. 예를 들어 모든 사용자에 대해 MyExtension 1.0을 설치 하지만 동일한 컴퓨터에 MyExtension 2.0 디버그, 실험적 설정 하려는 경우 \= "true"입니다. 이 특성은 이상 Visual Studio 2015 업데이트 1에서 사용할 수 있습니다.  
  
-   `Scope` \-이 특성 값은 "Global" 또는 "ProductExtension"를 사용할 수 있습니다.  
  
    -   "전역" 지정 설치를 특정 SKU로 범위가 지정 되지 않습니다. 예를 들어이 값을 확장 SDK를 설치할 때 사용 됩니다.  
  
    -   "ProductExtension"는 전통적인 VSIX 확장 \(버전 1.0\) 개별 Visual Studio Sku 범위 지정이 설치 되어 있는지를 지정 합니다. 기본값입니다.  
  
-   `AllUsers` \-이 선택적 특성이이 패키지에 대 한 모든 사용자가 설치할 것인지 여부를 지정 합니다. 기본적으로이 특성은 false를 지정 하는 패키지 사용자 당입니다. \(이 값을 true로 설정 하면 설치 하는 사용자 권한을 상승 해야 생성 되는 VSIX를 설치 하려면 관리자 권한 수준에 있습니다.  
  
-   `InstalledByMsi` \-이 선택적 특성이이 패키지는 MSI가 설치 되어 있는지를 지정 합니다. MSI가 설치 된 패키지 설치 되 고 관리 되는 MSI \(프로그램 및 기능\)가와 하지 하 여 Visual Studio 확장 관리자입니다.  기본적으로이 특성은 false, 지정 하는 패키지는 MSI가 설치 되지 않도록 합니다.  
  
-   `SystemComponent` \-이 선택적 특성 고려할지 여부를이 패키지는 시스템 구성 요소를 지정 합니다. 시스템 구성 요소 확장 관리자 UI에서 표시 안 함 및 업데이트할 수 없습니다. 기본적으로이 특성은 false 이면 지정 하는 패키지는 시스템 구성 요소는 없습니다.  
  
-   `AnyAttribute*` – `Installation` 요소는 이름\-값 쌍 사전으로 런타임에 노출 될 특성의 개방형 집합을 수락 합니다.  
  
-   `<InstallationTarget>` –이 요소는 VSIX 설치 관리자는 패키지를 설치 하는 위치를 제어 합니다. 하는 경우의 값은 `Scope` 특성은 "ProductExtension" 패키지 확장에 가용성을 광고 하기 위해 해당 내용의 일부로 매니페스트 파일을 설치에 SKU를 대상으로 해야 합니다.`<InstallationTarget>` 요소는 다음과 같은 경우 특성은 `Scope` 특성에 명시적 값 또는 기본값을 "ProductExtension":  
  
    -   `Id` \-이 특성 패키지를 식별합니다.  특성의 네임 스페이스 규칙을 따릅니다: Company.Product.Feature.Name 합니다.`Id` 특성 영숫자 문자만 포함할 수 있으며 최대 100 자입니다. 예상 값:  
  
        -   Microsoft.VisualStudio.IntegratedShell  
  
        -   Microsoft.VisualStudio.Pro  
  
        -   Microsoft.VisualStudio.Premium  
  
        -   Microsoft.VisualStudio.Ultimate  
  
        -   Microsoft.VisualStudio.VWDExpress  
  
        -   Microsoft.VisualStudio.VPDExpress  
  
        -   Microsoft.VisualStudio.VSWinExpress  
  
        -   Microsoft.VisualStudio.VSLS  
  
        -   My.Shell.App  
  
    -   `Version` \-이 특성이이 SKU의 최소 및 최대 지원된 버전으로 버전 범위를 지정합니다. 패키지 수는 버전의 지원 되는 Sku 자세히 설명 합니다. 버전 범위 노테이션을 \[10.0 – 11.0\], 위치  
  
        -   \[\-최소 버전을 포함 합니다.  
  
        -   \] – 최대 버전을 포함 합니다.  
  
        -   \(\-단독 최소 버전.  
  
        -   \)\-최대 버전을 제외 합니다.  
  
        -   단일 버전 \#\-지정된 된 버전입니다.  
  
        > [!IMPORTANT]
        >  VSIX 스키마의 버전 2.0은 Visual Studio 2012에서 도입 되었습니다. 이 스키마를 사용 하 여 Visual Studio 2012 또는 나중에 컴퓨터에 설치 되어 있고 있어야 해당 제품의 일부인 VSIXInstaller.exe를 사용 하 여 합니다. 이전 버전의 Visual Studio는 Visual Studio 2012 또는 이후 VSIXInstaller 있지만 이후 버전의 설치 관리자를 사용해 서만 대상으로 지정할 수 있습니다.  
  
    -   `AnyAttribute*` – `<InstallationTarget>` 요소를 사용 하면 이름\-값 쌍 사전으로 런타임에 노출 될 수 있는 특성의 개방형 집합입니다.  
  
### Dependencies 요소  
 이 요소는이 패키지를 선언 하는 종속성 목록을 포함 합니다. 종속성을 지정 하는 경우 해당 패키지 \(로 식별 되 자신의 `Id`\) 해야 하기 전에 설치 된 합니다.  
  
-   `<Dependency>` 요소 –이 자식 요소에는 다음 특성이 있습니다.  
  
    -   `Id` \-이 특성에는 종속 패키지에 대 한 고유 ID 여야 합니다. Id 값이 일치 해야는 `<Metadata><Identity>Id` 이 패키지에 종속 된 패키지의 특성입니다.`Id` 특성의 네임 스페이스 규칙을 따릅니다: Company.Product.Feature.Name 합니다. 특성은 영숫자 문자만 포함할 수 있으며 100 자로 제한 됩니다.  
  
    -   `Version` \-이 특성이이 SKU의 최소 및 최대 지원된 버전으로 버전 범위를 지정합니다. 패키지 수는 버전의 지원 되는 Sku 자세히 설명 합니다. 버전 범위 표기법은 \[12.0, 13.0\], 위치:  
  
        -   \[\-최소 버전을 포함 합니다.  
  
        -   \] – 최대 버전을 포함 합니다.  
  
        -   \(\-단독 최소 버전.  
  
        -   \)\-최대 버전을 제외 합니다.  
  
        -   단일 버전 \#\-지정된 된 버전입니다.  
  
    -   `DisplayName` \-이 특성은 대화 상자와 오류 메시지와 같은 UI 요소에 사용 되는 종속 패키지의 표시 이름. 특성 종속 패키지 MSI가 설치 되어 있지 않으면 선택 사항입니다.  
  
    -   `Location` \-이 선택적 특성 중첩된 VSIX 패키지에이 VSIX 내에서 상대 경로 또는 종속성에 대 한 다운로드 위치에 대 한 URL을 지정합니다. 이 특성은 필수 구성 요소 패키지를 찾는 데 사용 됩니다.  
  
    -   `AnyAttribute*` – `Dependency` 요소는 이름\-값 쌍 사전으로 런타임에 노출 될 특성의 개방형 집합을 수락 합니다.  
  
### 자산 요소  
 이 요소 목록이 포함 `<Asset>` 각 확장 또는 콘텐츠 요소에 대 한 태그가이 패키지를 표시 합니다.  
  
-   `<Asset>` \-이 요소는 다음과 같은 특성 및 요소가 포함 되어 있습니다.  
  
    -   `Type` –이 확장 또는이 요소가 나타내는 콘텐츠 형식입니다. 각 `<Asset>` 요소는 단일 있어야 합니다. `Type`, 여러 있지만 `<Asset>` 요소는 동일한 가질 수 `Type`합니다. 네임 스페이스 규칙에 따라이 특성을 정규화 된 이름으로 나타나야 합니다. 알려진된 형식은 다음과 같습니다.  
  
        1.  Microsoft.VisualStudio.VsPackage  
  
        2.  Microsoft.VisualStudio.MefComponent  
  
        3.  Microsoft.VisualStudio.ToolboxControl  
  
        4.  Microsoft.VisualStudio.Samples  
  
        5.  Microsoft.VisualStudio.ProjectTemplate  
  
        6.  Microsoft.VisualStudio.ItemTemplate  
  
        7.  Microsoft.VisualStudio.Assembly  
  
         고유한 형식을 만들고 고유한 이름을 부여할 수 있습니다. Visual Studio 내 실행 시 코드 열거 하 고 확장 관리자 API를 통해 이러한 사용자 지정 형식에 액세스 합니다.  
  
    -   경로\-파일 또는 폴더는 자산을 포함 하는 패키지 내에 상대 경로입니다.  
  
    -   `AnyAttribute*` –의 개방형 집합 이름\-값 쌍 사전으로 런타임에 노출 될 수 있는 특성입니다.  
  
         `<AnyElement>*` – 모든 구조화 된 내용이 간 허용 되는 `<Asset>` 시작 및 끝 태그입니다. 모든 요소는 XmlElement 개체의 목록으로 노출 됩니다. VSIX 확장 매니페스트 파일의 구조적된 형식 관련 메타 데이터를 정의 하 고 런타임 시이 열거할 수 있습니다.  
  
### 샘플 매니페스트  
  
```  
<?xml version="1.0" encoding="utf-8"?>  
<PackageManifest Version="2.0.0" xmlns="http://schemas.microsoft.com/developer/vsx-schema/2011" xmlns:d="http://schemas.microsoft.com/developer/vsx-schema-design/2011">  
  <Metadata>  
    <Identity Id="0000000-0000-0000-0000-000000000000" Version="1.0" Language="en-US" Publisher="Company" />  
    <DisplayName>Test Package</DisplayName>  
    <Description>Information about my package</Description>  
    <MoreInfo>http://www.fabrikam.com/Extension1/</MoreInfo>  
    <License>eula.rtf</License>  
    <ReleaseNotes>notes.txt</ReleaseNotes>  
    <Icon>Images\icon.png</Icon>  
    <PreviewImage>Images\preview.png</PreviewImage>  
  </Metadata>  
  <Installation InstalledByMsi="false" AllUsers="false" SystemComponent="false" Scope="ProductExtension">  
    <InstallationTarget Id="Microsoft.VisualStudio.Pro" Version="[11.0, 12.0]" />  
  </Installation>  
  <Dependencies>  
    <Dependency Id="Microsoft.Framework.NDP" DisplayName="Microsoft .NET Framework" d:Source="Manual" Version="[4.5,)" />  
    <Dependency Id="Microsoft.VisualStudio.MPF.12.0" DisplayName="Visual Studio MPF 12.0" d:Source="Installed" Version="[12.0]" />  
  </Dependencies>  
  <Assets>  
    <Asset Type="Microsoft.VisualStudio.VsPackage" d:Source="Project" d:ProjectName="%CurrentProject%" Path="|%CurrentProject%;PkgdefProjectOutputGroup|" />  
  </Assets>  
</PackageManifest>  
```  
  
## 참고 항목  
 [배송 Visual Studio 확장](../extensibility/shipping-visual-studio-extensions.md)