---
title: 프로젝트 및 구성 속성에 대 한 지원 | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- vs-ide-sdk
ms.topic: conceptual
helpviewer_keywords:
- project properties, supporting with Visual Studio SDK
- configuration properties, suppporting with Visual Studio SDK
ms.assetid: 9fcfaa0f-7b41-4b68-82ec-7a151dca5d7e
author: gregvanl
ms.author: gregvanl
manager: douge
ms.workload:
- vssdk
ms.openlocfilehash: 823bfa0453d3e33fea2daa51779b1fe4800a1a86
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="support-for-project-and-configuration-properties"></a>프로젝트 및 구성 속성에 대 한 지원
**속성** 창에는 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)] 통합된 개발 환경 (IDE) 프로젝트 및 구성 속성을 표시할 수 있습니다. 사용자 응용 프로그램에 대 한 속성을 설정할 수 있도록 고유한 프로젝트 형식에 대 한 속성 페이지를 제공할 수 있습니다.  
  
 프로젝트 노드를 선택 하 여 **솔루션 탐색기** 클릭 한 다음 **속성** 에 **프로젝트** 메뉴에서 프로젝트 및 구성 포함 된 대화 상자를 열 수 속성입니다. [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] 및 [!INCLUDE[vbprvb](../../code-quality/includes/vbprvb_md.md)], 하 고이 대화 상자가 나타납니다 탭된 페이지에 이러한 언어에서 파생 된 형식으로 프로젝션 된 [환경, 옵션 대화 상자, 일반](../../ide/reference/general-environment-options-dialog-box.md)합니다. 자세한 내용은 참조 [빌드에 없음: 연습: 구성 속성 (C#) 및 노출 하는 프로젝트](http://msdn.microsoft.com/en-us/d850d63b-25e2-4505-9f3d-eb038d7c1d0e)합니다.  
  
 프로젝트 (MPFProj)에 대 한 관리 되는 패키지 프레임 워크는 만들고 새 프로젝트 시스템을 관리 하기 위한 도우미 클래스를 제공 합니다. 코드 및 컴파일 지침에는 소스를 찾을 수 [프로젝트-Visual Studio 2013에 대 한 MPF](http://mpfproj12.codeplex.com/)합니다.  
  
## <a name="persistence-of-project-and-configuration-properties"></a>프로젝트 및 구성 속성의 지 속성  
 프로젝트 및 구성 속성은 예를 들어 프로젝트 형식과 연결 된 파일 이름 확장명,.csproj,.vbproj, 및.myproj 있는 프로젝트 파일에서 유지 됩니다. 언어 프로젝트는 일반적으로 프로젝트 파일을 생성 하려면 서식 파일을 사용 합니다. 그러나 실제로 여러 가지 방법으로 프로젝트 형식 및 서식 파일을 연결할 수 있습니다. 자세한 내용은 참조 [템플릿 디렉터리 설명 (합니다. Vsdir) 파일](../../extensibility/internals/template-directory-description-dot-vsdir-files.md)합니다.  
  
 프로젝트 및 구성 속성은 템플릿 파일에 항목을 추가 하 여 생성 됩니다. 이러한 속성은 다음이 템플릿을 사용 하는 프로젝트 형식을 사용 하 여 만든 모든 프로젝트에 사용할 수 있습니다. [!INCLUDE[csprcs](../../data-tools/includes/csprcs_md.md)] 프로젝트 및 둘 다 사용 MPFProj는 [빌드에 없음: MSBuild 개요](http://msdn.microsoft.com/en-us/b588fd73-a45b-4706-908f-cc131bccfbde) 템플릿 파일에 대 한 스키마입니다. 이러한 파일 각각의 구성에 대 한 소스 파일 섹션에 있습니다. 프로젝트의 속성 구성 인수가 null 문자열로 설정 하는 첫 번째 소스 파일 섹션에서 일반적으로 유지 됩니다.  
  
 다음 코드에서는 기본 MSBuild 프로젝트 파일의 시작 부분을 보여 줍니다.  
  
```  
<Project MSBuildVersion="2.0" DefaultTargets="Build" xmlns="http://schemas.microsoft.com/developer/msbuild/2003">  
  <PropertyGroup>  
    <Configuration Condition=" '$(Configuration)' == '' ">Debug</Configuration>  
    <Name>SomeProjectSix</Name>  
    <SchemaVersion>2.0</SchemaVersion>  
  </PropertyGroup>  
  <PropertyGroup Condition=" '$(Configuration)' == 'Debug' ">  
    <Optimize>false</Optimize>  
  </PropertyGroup>  
  <PropertyGroup Condition=" '$(Configuration)' == 'Release' ">  
    <Optimize>true</Optimize>  
```  
  
 이 프로젝트 파일에서 `<Name>` 및 `<SchemaVersion>` 은 프로젝트 속성 및 `<Optimize>` 구성 속성입니다.  
  
 프로젝트 파일의 프로젝트 및 구성 속성을 유지 하기 위해 프로젝트의 작업은  
  
> [!NOTE]
>  프로젝트의 기본 값과 다른 유지 유일한 속성 값에 의해 지 속성을 최적화할 수 있습니다.  
  
## <a name="support-for-project-and-configuration-properties"></a>프로젝트 및 구성 속성에 대 한 지원  
 `Microsoft.VisualStudio.Package.SettingsPage` 클래스는 프로젝트 및 구성 속성 페이지를 구현 합니다. 기본 구현은 `SettingsPage` 일반 속성 그리드에서 사용자에 게 공용 속성을 제공 합니다. `Microsoft.VisualStudio.Package.HierarchyNode.GetPropertyPageGuids` 메서드 선택에서 파생 된 클래스 `SettingsPage` 속성 표를 프로젝트에 대 한 합니다. `Microsoft.VisualStudio.Package.ProjectNode.GetConfigPropertyPageGuids` 메서드 선택에서 파생 된 클래스 `SettingsPage` 구성 속성 표에 대 한 합니다. 프로젝트 형식을 적절 한 속성 페이지를 선택 하려면 이러한 메서드를 재정의 해야 합니다.  
  
 `SettingsPage` 클래스 및 `Microsoft.VisualStudio.Package.ProjectNode` 클래스는 프로젝트 및 구성 속성을 유지 하도록 이러한 메서드를 제공 합니다.  
  
-   `Microsoft.VisualStudio.Package.ProjectNode.GetProjectProperty` 및 `Microsoft.VisualStudio.Package.ProjectNode.SetProjectProperty` 프로젝트 속성을 유지 합니다.  
  
-   `Microsoft.VisualStudio.Package.SettingsPage.GetConfigProperty` 및 `Microsoft.VisualStudio.Package.SettingsPage.SetConfigProperty` 구성 속성을 유지 합니다.  
  
    > [!NOTE]
    >  구현에서 `Microsoft.VisualStudio.Package.SettingsPage` 및 `Microsoft.VisualStudio.Package.ProjectNode` 사용 하는 클래스는 `Microsoft.Build.BuildEngine` 가져오고 프로젝트 파일에서 프로젝트 및 구성 속성을 설정 하는 메서드를 (MSBuild).  
  
 파생 되는 클래스 `SettingsPage` 구현 해야 `Microsoft.VisualStudio.Package.SettingsPage.ApplyChanges` 및 `Microsoft.VisualStudio.Package.SettingsPage.BindProperties` 프로젝트 파일의 프로젝트 또는 구성 속성이 유지 되도록 합니다.  
  
## <a name="provideobjectattribute-and-registry-path"></a>ProvideObjectAttribute 및 레지스트리 경로  
 클래스에서 파생 된 `SettingsPage` 은 Vspackage에서 공유할 수 있도록 합니다. 파생 된 클래스를 만드는 VSPackage에 대 한 수 있도록 `SettingsPage`, 추가 `Microsoft.VisualStudio.Shell.ProvideObjectAttribute` 에서 파생 된 클래스에 `Microsoft.VisualStudio.Shell.Package`합니다.  
  
 [!code-csharp[VSSDKSupportProjectConfigurationProperties#1](../../extensibility/internals/codesnippet/CSharp/support-for-project-and-configuration-properties_1.cs)]
 [!code-vb[VSSDKSupportProjectConfigurationProperties#1](../../extensibility/internals/codesnippet/VisualBasic/support-for-project-and-configuration-properties_1.vb)]  
  
 특성을 추가할 VSPackage 중요 하지 않습니다. VSPackage를 등록 될 때 [!INCLUDE[vsprvs](../../code-quality/includes/vsprvs_md.md)], 만들 수 있는 모든 개체의 클래스 id (CLSID)가 등록 있도록에 대 한 호출 <xref:Microsoft.VisualStudio.Shell.Interop.ILocalRegistry.CreateInstance%2A> 값을 만들 수 있습니다.  
  
 레지스트리 경로 만들 수 있는 개체의 조합에 의해 결정 됩니다 <xref:Microsoft.VisualStudio.Shell.Package.UserRegistryRoot%2A>, 단어, CLSID, 및 개체 유형의 guid입니다. 경우 `MyProjectPropertyPage` 클래스에 {3c693da2-5bca-49b3-bd95-ffe0a39dd723}의 guid는 UserRegistryRoot은 HKEY_CURRENT_USER\Software\Microsoft\VisualStudio\8.0Exp, 힙이고 레지스트리 경로 HKEY_CURRENT_USER\Software\Microsoft\VisualStudio 것 \8.0Exp\CLSID\\{3c693da2-5bca-49b3-bd95-ffe0a39dd723}.  
  
## <a name="project-and-configuration-property-attributes-and-layout"></a>프로젝트 및 구성 속성 특성 및 레이아웃  
 <xref:System.ComponentModel.CategoryAttribute>, <xref:System.ComponentModel.DisplayNameAttribute>, 및 <xref:System.ComponentModel.DescriptionAttribute> 특성 결정 레이아웃, 레이블 지정 및 일반 속성 페이지에서 프로젝트 및 구성 속성에 대해 설명 합니다. 이러한 특성 범주를 확인, 이름 및 설명의 옵션을를 각각 표시 합니다.  
  
> [!NOTE]
>  해당 특성, SRCategory, LocDisplayName, SRDescription, 지역화에 대 한 문자열 리소스를 사용 하 여 및에 정의 된 [프로젝트-Visual Studio 2013에 대 한 MPF](http://mpfproj12.codeplex.com/)합니다.  
  
 다음과 같은 코드 조각을 생각해 봅시다.  
  
 [!code-vb[VSSDKSupportProjectConfigurationProperties#2](../../extensibility/internals/codesnippet/VisualBasic/support-for-project-and-configuration-properties_2.vb)]
 [!code-csharp[VSSDKSupportProjectConfigurationProperties#2](../../extensibility/internals/codesnippet/CSharp/support-for-project-and-configuration-properties_2.cs)]  
  
 `MyConfigProp` 구성 속성이 구성 속성 페이지에 나타나는 **구성 속성에 내** 범주의 **내 범주**합니다. 옵션을 선택 하는 경우 설명을 **내 설명**, 설명 창에 나타납니다.  
  
## <a name="see-also"></a>참고 항목  
 [추가 하 고 속성 페이지를 제거 합니다.](../../extensibility/adding-and-removing-property-pages.md)   
 [프로젝트](../../extensibility/internals/projects.md)   
 [템플릿 디렉터리 설명(.Vsdir) 파일](../../extensibility/internals/template-directory-description-dot-vsdir-files.md)
