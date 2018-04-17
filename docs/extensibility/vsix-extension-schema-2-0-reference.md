---
title: VSIX 확장 2.0 스키마 참조 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- vsix
- extension schema
ms.assetid: 0da81b98-f5e3-40d3-ba9a-94551378d0b4
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 7459b4292220e6bb1e5a00b912efe7eb99cce825
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="vsix-extension-schema-20-reference"></a>VSIX 확장 2.0 스키마 참조
VSIX 배포 매니페스트 파일에는 VSIX 패키지의 내용을 설명합니다. 스키마 파일 형식이 적용 됩니다. 이 스키마의 버전 2.0에 추가 하는 사용자 지정 형식 및 특성을 지원 합니다.  매니페스트 스키마가 확장 가능 합니다. 매니페스트 로더 이해 하지 못하는 XML 요소 및 특성을 무시 합니다.  
  
> [!IMPORTANT]
>  Visual Studio 2015는 Visual Studio 2010, Visual Studio 2012 또는 Visual Studio 2013 형식에서 VSIX 파일을 로드할 수 있습니다.  
  
## <a name="package-manifest-schema"></a>패키지 매니페스트 스키마  
 매니페스트 XML 파일의 루트 요소는 `<PackageManifest>`, 단일 특성 `Version`, 매니페스트 형식 버전입니다. 형식에 주요 변경 되 면 버전 형식이 변경 됩니다. 이 항목에서는 설정 하 여 매니페스트에 지정 된 매니페스트 형식 버전 2.0에서는 설명는 `Version` 특성 버전 값으로 "2.0" = 합니다.  
  
### <a name="packagemanifest-element"></a>PackageManifest 요소  
 내에서 `<PackageManifest>` 루트 요소를 다음과 같은 요소를 사용할 수 있습니다.  
  
-   `<Metadata>` -메타 데이터 및 패키지 자체에 대 한 알림 정보가 있습니다. 하나의 `Metadata` 매니페스트에 요소를 사용할 수 있습니다.  
  
-   `<Installation>` -이 섹션에는이 확장 패키지를 설치할 수에 설치할 수 있는 응용 프로그램 Sku를 포함 하 여는 방법을 정의 합니다. 단일 `Installation` 매니페스트에 요소를 사용할 수 있습니다. 매니페스트 있어야는 `Installation` 요소 또는이 패키지에 SKU가 설치 되지 않습니다.  
  
-   `<Dependencies>` -이 패키지에 대 한 종속성 an 옵션 목록이 여기에 정의 됩니다.  
  
-   `<Assets>` -이 섹션에는이 패키지에 포함 된 자산을 모두 포함 됩니다. 이 섹션에서는 없이이 패키지 콘텐츠를 노출 되지 않습니다.  
  
-   `<AnyElement>*` -매니페스트 스키마는 다른 모든 요소의 수 있을 만큼 유연 합니다. 모든 자식 요소 매니페스트 로더 인식 되지 않으므로 추가 XmlElement 개체도 확장 관리자 API에 노출 됩니다. VSIX 확장 이러한 하위 요소를 사용 하 여 Visual Studio에서 실행 되는 코드는 런타임에 액세스할 수 있는 매니페스트 파일에 추가 데이터를 정의할 수 있습니다. <xref:Microsoft.VisualStudio.ExtensionManager.IExtension.AdditionalElements%2A> 및 <xref:Microsoft.VisualStudio.ExtensionManager.IExtension.LocalizedAdditionalElements%2A>을 참조하십시오.  
  
### <a name="metadata-element"></a>메타 데이터 요소  
 이 섹션은 패키지, 해당 id 및 정보를 보급 하는 방법에 대 한 메타 데이터입니다. `<Metadata>` 다음과 같은 요소가 포함 되어 있습니다.  
  
-   `<Identity>` -이이 패키지에 대 한 식별 정보를 정의 하 고 다음 특성을 포함 합니다.  
  
    -   `Id` -이 특성을 만든 사람이 선택한 패키지에 대 한 고유 ID 여야 합니다. 이름에 CLR 네임 스페이스 지정 된 유형은 같은 방법으로 정규화 되어야 합니다: Company.Product.Feature.Name 합니다. `Id` 특성은 100 자로 제한 됩니다.  
  
    -   `Version` -이 버전의이 패키지 및 해당 내용을 정의합니다. 이 특성에는 CLR 어셈블리 버전 관리 형식을 따릅니다: Major.Minor.Build.Revision (1.2.40308.00). 더 높은 버전 번호를 사용 하 여 패키지는 패키지에 대 한 업데이트 것으로 간주 됩니다 및 기존 설치 된 버전을 통해 설치할 수 있습니다.  
  
    -   `Language` -이 특성은 패키지에 대 한 기본 언어 및이 매니페스트에에서 텍스트 데이터에 해당 합니다. 이 특성 리소스 어셈블리에 대 한 예를 들어 CLR 로캘 코드 규칙을 따르는: en-우리, en, fr-fr 합니다. 지정할 수 있습니다 `neutral` 를 모든 버전의 Visual Studio에서 실행 되는 중립 언어 확장을 선언 합니다. 기본값은 `neutral`입니다.  
  
    -   `Publisher` -이 특성은 회사 또는 개별 이름을이 패키지의 게시자를 식별합니다. `Publisher` 특성은 100 자로 제한 됩니다.  
  
-   `<DisplayName>` -이 요소는 확장 관리자 UI에 표시 되는 사용자에 게 친숙 패키지 이름을 지정 합니다. `DisplayName` 콘텐츠는 50 자로 제한 됩니다.  
  
-   `<Description>` -이 선택적 요소는 확장 관리자 UI에 표시 되는 패키지 및 해당 내용을 간단한 설명입니다. `Description` 원하는 텍스트에 포함할 수 1, 000 자로 제한 됨.  
  
-   `<MoreInfo>` -이 선택적 요소는이 패키지에 대 한 자세한 내용은 포함 하는 페이지를 온라인에 대 한 URL입니다. 프로토콜은 http로 지정 되어야 합니다.  
  
-   `<License>` -이 선택적 요소는 상대 경로 패키지에 포함 된 라이선스 파일 (.txt,.rtf)입니다.  
  
-   `<ReleaseNotes>` -이 선택적 요소는 릴리스 정보를 표시 하는 웹 사이트에 대 한 URL 또는 else (.txt,.rtf) 패키지에 포함 된 릴리스 정보 파일에 상대 경로입니다.  
  
-   `<Icon>` -이 선택적 요소는 상대 경로 패키지에 포함 된 이미지 파일 (png, bmp, jpeg, ico)입니다. 32 x 32 픽셀 이어야 합니다 (또는 해당 크기를 축소할 수) 아이콘 이미지 UI listview에 나타납니다. 되지 않은 경우 `Icon` 기본값을 사용 하 여 UI, 요소를 지정 합니다.  
  
-   `<PreviewImage>` -이 선택적 요소는 상대 경로 패키지에 포함 된 이미지 파일 (png, bmp, jpeg)입니다. 미리 보기 이미지는 200 x 200 픽셀 이어야 하 고 UI 세부 정보에 표시 합니다. 되지 않은 경우 `PreviewImage` 기본값을 사용 하 여 UI, 요소를 지정 합니다.  
  
-   `<Tags>` -이 선택적 요소 검색 힌트에 사용 되는 추가 세미콜론으로 구분 된 텍스트 태그를 나열 합니다. `Tags` 요소는 100 자로 제한 됩니다.  
  
-   `<GettingStartedGuide>` -이 선택적 요소는 HTML 파일의 상대 경로 또는 확장명 또는이 패키지 내에서 콘텐츠를 사용 하는 방법에 대 한 정보를 포함 하는 웹 사이트에 대 한 URL입니다. 이 가이드는 설치 과정의 일부로 실행 됩니다.  
  
-   `<AnyElement>*` -매니페스트 스키마는 다른 모든 요소의 수 있을 만큼 유연 합니다. 매니페스트 로더에 의해 인식 되지 않는 모든 자식 요소는 XmlElement 개체의 목록으로 노출 됩니다. VSIX 확장 하 이러한 하위 요소를 사용 하 여 매니페스트 파일에 추가 데이터를 정의 고 런타임 시이 열거 합니다.  
  
### <a name="installation-element"></a>설치 요소  
 이 섹션에 설치할 수 있는 응용 프로그램 Sku 및이 패키지를 설치 하는 방법을 정의 합니다. 이 섹션에는 다음과 같은 특성이 포함 되어 있습니다.  
  
-   `Experimental` -이 특성을 모든 사용자에 대해 현재 설치 되어 있는 확장 있지만 동일한 컴퓨터에 업데이트 된 버전을 개발 하는 경우 true로 설정 합니다. 예를 들어 모든 사용자에 대해 MyExtension 1.0을 설치 했지만 MyExtension 2.0 동일한 컴퓨터에서 디버깅할 실험적 설정 하려는 경우 = "true"입니다. 이 특성에는 Visual Studio 2015 업데이트 1에서 사용할 수 이상입니다.  
  
-   `Scope` -이 특성 값은 "Global" 또는 "ProductExtension"를 사용할 수 있습니다.  
  
    -   "전역" 설치를 특정 SKU로 범위가 한정 되지 지정 합니다. 예를 들어이 값은 확장명 SDK를 설치할 때 사용 됩니다.  
  
    -   "ProductExtension" 개별 Visual Studio Sku에 범위가 지정 된 기존 VSIX 확장 (버전 1.0)가 설치 되어 있는지를 지정 합니다. 기본값입니다.  
  
-   `AllUsers` -이 선택적 특성이이 패키지에 대 한 모든 사용자가 설치할 것인지 여부를 지정 합니다. 기본적으로이 특성은 false를 지정 하는 패키지 사용자 당입니다. (이 값을 true로 설정 하면 설치 하는 사용자 높여야 결과 VSIX를 설치 하려면 관리자 권한 수준으로 됩니다.  
  
-   `InstalledByMsi` -선택적 특성이는이 패키지는 MSI가 설치 되어 있는지를 지정 합니다. MSI가 설치 된 패키지 설치 되 고 관리 되는 MSI (프로그램 및 기능)에서 및 하지는 Visual Studio 확장 관리자 별로 합니다.  기본적으로이 특성은 false, 패키지는 MSI가 설치 되지 않았는지를 지정 하는입니다.  
  
-   `SystemComponent` -이 선택적 특성 고려할지 여부를이 패키지는 시스템 구성 요소를 지정 합니다. 시스템 구성 요소 확장명 관리자 UI에 표시 안 함 및 업데이트할 수 없습니다. 기본적으로이 특성은 false, 시스템 구성 요소 패키지 없음을 지정 하는입니다.  
  
-   `AnyAttribute*` - `Installation` 요소 이름-값 쌍 사전으로 서 런타임에 노출 하는 특성의 개방형 집합을 수락 합니다.  
  
-   `<InstallationTarget>` -이 요소는 VSIX 설치 관리자는 패키지를 설치 하는 위치를 제어 합니다. 하는 경우의 값은 `Scope` 특성은 "ProductExtension" 패키지 매니페스트 파일 내용 확장과 가용성을 알릴 수의 일부로 설치에 SKU를 대상으로 해야 합니다. `<InstallationTarget>` 요소는 다음과 같은 경우 특성은 `Scope` 특성에 명시적 또는 기본값 "ProductExtension":  
  
    -   `Id` -이 특성은 패키지를 식별합니다.  특성 네임 스페이스 규칙을 따릅니다: Company.Product.Feature.Name 합니다. `Id` 특성 영숫자 문자만 포함 될 수 있습니다 및 100 자로 제한 됩니다. 예상 값:  
  
        -   Microsoft.VisualStudio.IntegratedShell  
  
        -   Microsoft.VisualStudio.Pro  
  
        -   Microsoft.VisualStudio.Premium  
  
        -   Microsoft.VisualStudio.Ultimate  
  
        -   Microsoft.VisualStudio.VWDExpress  
  
        -   Microsoft.VisualStudio.VPDExpress  
  
        -   Microsoft.VisualStudio.VSWinExpress  
  
        -   Microsoft.VisualStudio.VSLS  
  
        -   My.Shell.App  
  
    -   `Version` -이 특성이이 SKU의 최소 및 최대 지원 되는 버전으로 버전 범위를 지정합니다. 패키지 수는 버전의 지원 되는 Sku 자세히 설명 합니다. 버전 범위 노테이션을 [10.0-11.0]는 위치  
  
        -   [-최소 버전 (포함).  
  
        -   ]-최대 버전을 포함 합니다.  
  
        -   (-단독 최소 버전입니다.  
  
        -   )-최대 버전을 제외 합니다.  
  
        -   단일 버전 #-지정된 된 버전입니다.  
  
        > [!IMPORTANT]
        >  VSIX 스키마의 버전 2.0은 Visual Studio 2012에서 도입 되었습니다. 이 스키마를 사용 하려면 Visual Studio 2012 또는 나중에 컴퓨터에 설치 되어 있고 있어야 해당 제품의 일부인 VSIXInstaller.exe를 사용 하 여 합니다. 이전 버전의 Visual Studio는 Visual Studio 2012 또는 이후 VSIXInstaller 있지만 이후 버전의 설치 관리자를 사용 해야만 지정할 수 있습니다.  
  
    -   `AnyAttribute*` - `<InstallationTarget>` 이름-값 쌍 사전으로 서 런타임에 노출 될 수 있는 특성의 개방형 집합 요소를 사용 합니다.  
  
### <a name="dependencies-element"></a>Dependencies 요소  
 이 요소는이 패키지를 선언 하는 종속성 목록을 포함 합니다. 모든 종속 관계를 지정 하는 경우 이러한 패키지 (으로 식별 자신의 `Id`) 이어야 합니다 하기 전에 설치 된 합니다.  
  
-   `<Dependency>` 요소-이 자식 요소에는 다음 특성이 있습니다.  
  
    -   `Id` -이 특성에 종속 된 패키지에 대 한 고유 ID 여야 합니다. Id 값이 일치 해야 합니다는 `<Metadata><Identity>Id` 이 패키지에 종속 되어 있는 패키지의 특성입니다. `Id` 특성 네임 스페이스 규칙을 따릅니다: Company.Product.Feature.Name 합니다. 특성에는 영숫자 문자만 포함 될 수 있습니다 및 100 자로 제한 됩니다.  
  
    -   `Version` -이 특성이이 SKU의 최소 및 최대 지원 되는 버전으로 버전 범위를 지정합니다. 패키지 수는 버전의 지원 되는 Sku 자세히 설명 합니다. 버전 범위 표기법 [12.0, 13.0] 여기서:  
  
        -   [-최소 버전 (포함).  
  
        -   ]-최대 버전을 포함 합니다.  
  
        -   (-단독 최소 버전입니다.  
  
        -   )-최대 버전을 제외 합니다.  
  
        -   단일 버전 #-지정된 된 버전입니다.  
  
    -   `DisplayName` -이 특성은 대화 상자와 오류 메시지 등의 UI 요소에 사용 되는 종속 패키지의 표시 이름입니다. 특성 종속 패키지 MSI가 설치 되어 있지 않으면 선택 사항입니다.  
  
    -   `Location` -이 선택적 특성 내에 중첩 된 VSIX 패키지가이 VSIX에서 상대 경로 또는 종속성에 대 한 다운로드 위치에 대 한 URL을 지정합니다. 이 특성은 사용자 필수 구성 요소 패키지를 찾을 수 있도록 사용 됩니다.  
  
    -   `AnyAttribute*` - `Dependency` 요소 이름-값 쌍 사전으로 서 런타임에 노출 하는 특성의 개방형 집합을 수락 합니다.  
  
### <a name="assets-element"></a>자산 요소  
 이 요소 목록이 포함 `<Asset>` 이 패키지에서 각 확장명 또는 콘텐츠 요소에 대 한 태그를 표시 합니다.  
  
-   `<Asset>` -이 요소는 다음과 같은 특성 및 요소가 포함 되어 있습니다.  
  
    -   `Type` -확장 또는이 요소가 나타내는 콘텐츠 형식입니다. 각 `<Asset>` 요소는 단일 있어야 `Type`, 하지만 여러 `<Asset>` 요소는 동일한 가질 수 `Type`합니다. 이 특성 네임 스페이스 규칙에 따라 정규화 된 이름으로 나타내야 합니다. 알려진 형식은 다음과 같습니다.  
  
        1.  Microsoft.VisualStudio.VsPackage  
  
        2.  Microsoft.VisualStudio.MefComponent  
  
        3.  Microsoft.VisualStudio.ToolboxControl  
  
        4.  Microsoft.VisualStudio.Samples  
  
        5.  Microsoft.VisualStudio.ProjectTemplate  
  
        6.  Microsoft.VisualStudio.ItemTemplate  
  
        7.  Microsoft.VisualStudio.Assembly  
  
         형식을 사용자를 만들고 고유 이름을 부여할 수 있습니다. Visual Studio 내부 런타임 시 코드 열거 하 고 확장 관리자 API를 통해 이러한 사용자 지정 형식에 액세스할 수 있습니다.  
  
    -   경로-파일 또는 폴더는 자산을 포함 하는 패키지 내에 상대 경로입니다.  
  
    -   `AnyAttribute*` -의 개방형 집합 이름-값 쌍 사전으로 서 런타임에 노출 될 수 있는 특성입니다.  
  
         `<AnyElement>*` -모든 구조화 된 내용이 간 허용 되는 `<Asset>` 시작 및 끝 태그입니다. 모든 요소는 XmlElement 개체의 목록으로 노출 됩니다. VSIX 확장 매니페스트 파일에 구조적된 유형별 메타 데이터를 정의 하 고 런타임 시이 열거할 수 있습니다.  
  
### <a name="sample-manifest"></a>샘플 매니페스트  
  
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
  
## <a name="see-also"></a>참고 항목  
 [Visual Studio 확장 전달](../extensibility/shipping-visual-studio-extensions.md)