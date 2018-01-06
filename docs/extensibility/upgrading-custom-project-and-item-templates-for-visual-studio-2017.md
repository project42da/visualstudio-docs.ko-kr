---
title: "사용자 지정 프로젝트 및 항목 템플릿 Visual Studio 2017에 대 한 업그레이드 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-sdk
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: ad02477b-e101-4f32-aeb7-292bf95d5c2f
caps.latest.revision: "3"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 0c0843c8bfb899dc23bcb1ce31eb3f8b9eaffd54
ms.sourcegitcommit: 9357209350167e1eb7e50b483e44893735d90589
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/05/2018
---
# <a name="upgrading-custom-project-and-item-templates-for-visual-studio-2017"></a>사용자 지정 프로젝트 및 Visual Studio 2017에 대 한 항목 템플릿 업그레이드

Visual Studio 2017 년부터 Visual Studio은 Visual Studio의 이전 버전을 다른 방식으로.vsix 또는.msi 설치 된 프로젝트 및 항목 템플릿을 검색 합니다. 사용자 지정 프로젝트 또는 항목 템플릿을 사용 하는 확장을 소유 하는 경우 확장 프로그램을 업데이트 해야 합니다. 이 항목에서는 해야 할 사항을 설명 합니다.

이 변경 내용은 Visual Studio 2017을 결정 합니다. 이전 버전의 Visual Studio에는 영향을 주지 않습니다.

프로젝트 또는 항목 템플릿을 VSIX 확장의 일환으로 만들려는 경우 참조 [만드는 사용자 지정 프로젝트 및 항목 템플릿](../extensibility/creating-custom-project-and-item-templates.md)합니다.

## <a name="template-scanning"></a>서식 파일 검색

이전 버전의 Visual Studio에서 **devenv /setup** 또는 **devenv /installvstemplates** 프로젝트 템플릿과 항목 템플릿 찾기를 로컬 디스크를 검색 합니다. Visual Studio 2017 년부터 검색 없도록 위치에 대해서만 수행 됩니다. 기본 사용자 수준의 위치는 **%USERPROFILE%\Documents\\< Visual Studio 버전\>\Templates\\**합니다. 이 위치에 의해 생성 된 서식 파일에 사용 되는 **프로젝트** > **템플릿 내보내기...**  경우 명령에서 **템플릿을 Visual Studio로 자동으로 가져옵니다** 마법사에서 옵션을 선택 합니다.

(비 사용자)의 다른 위치에 대 한 위치 및 서식 파일의 다른 특성을 지정 하는 manifest(.vstman) 파일을 포함 해야 합니다. .Vstman 파일이.vstemplate 파일 서식 파일에 사용 되는 함께 생성 됩니다. .vsix를 사용 하 여 확장을 설치 하는 경우 Visual Studio 2017에서 확장을 다시 컴파일하여이 수행할 수 있습니다. 그러나 수동으로 변경 해야 하는.msi를 사용 하는 경우. 이러한 변경을 수행 하기 위해 수행 해야 할 작업 목록, 참조 **업그레이드와 함께 설치 된 확장에 대 한 프로그램입니다. MSI** 이 항목의 뒷부분에 나오는 합니다.  
  
## <a name="how-to-update-a-vsix-extension-with-project-or-item-templates"></a>프로젝트 또는 항목 템플릿을 VSIX 확장을 업데이트 하는 방법  

1.  Visual Studio 2017에서 솔루션을 엽니다. 코드를 업그레이드 하 라는 메시지가 표시 됩니다. **확인**을 클릭합니다.  
  
2.  업그레이드 완료 후 설치 대상의 버전을 변경 해야 합니다. VSIX 프로젝트에서 source.extension.vsixmanifest 파일을 열고 선택 된 **설치 대상** 탭 합니다. 경우는 **버전 범위** 필드는 **[14.0]**, 클릭 **편집** Visual Studio 2017을 포함 하도록 변경 합니다. 예를 들어, 설정할 수 **[14.0,15.0]** 또는 Visual Studio 2015 또는 Visual Studio 2017 년 중 하나에 확장을 설치 하 **[15.0]** 방금 Visual Studio 2017에 설치 합니다.  
  
3.  코드를 다시 컴파일해야 합니다.  
  
4.  Visual Studio를 닫습니다.  
  
5.  VSIX를 설치 합니다.  
  
6.  다음을 수행 하 여 업데이트를 테스트할 수 있습니다.  
  
    1.  파일 변경 검색 다음 레지스트리 키가 활성화 됩니다.  
  
         **reg은 hklm\software\microsoft\visualstudio\15.0\VSTemplate /v DisableTemplateScanning /t REG_DWORD /d 1 /reg:32 추가**  
  
    2.  키를 추가한 후에 실행 **devenv /installvstemplates**합니다.  
  
    3.  Visual Studio를 다시 엽니다. 예상된 위치에서 서식 파일을 찾아야 합니다.  
  
    > [!NOTE]
    >  레지스트리 키가 있는 Visual Studio 확장성 프로젝트 템플릿을 사용할 수 없는 경우 레지스트리 키를 삭제 해야 합니다 (다시 실행 **devenv /installvstemplates**) 사용 합니다.  
  
## <a name="other-recommendations-for-deploying-project-and-item-templates"></a>프로젝트 및 항목 템플릿 배포를 위한 기타 권장 사항  
  
-   압축 된 템플릿 파일을 사용 하지 마십시오. 파일 리소스 및 콘텐츠를 검색 하기 위해 압축에 필요한 서식 파일을 압축 하므로 됩니다 costlier 사용 하도록 합니다. 대신 템플릿 초기화 속도 향상을 위한 고유 디렉터리 아래 개별 파일로 프로젝트 템플릿과 항목 템플릿 배포 해야 합니다. VSIX 확장용 SDK 빌드 작업 자동으로 압축을 풉니다 압축 된 템플릿에 VSIX 파일을 만드는 중입니다.  
  
-   서식 파일 검색 중에 불필요 한 리소스 어셈블리 로드를 방지 하기 위해 템플릿 이름, 설명, 아이콘 또는 미리 보기에 대 한 패키지/리소스 ID 항목을 사용 하지 마십시오. 대신, 지역화 된 이름 또는 속성을 사용 하는 각 로캘에 대 한 템플릿 항목을 만드는 지역화 된 매니페스트를 사용할 수 있습니다.  
  
-   파일 항목으로 서식 파일을 포함 하는 경우 매니페스트 생성 제공 하지 않을 수 있습니다 예상된 결과입니다. 이 경우 수동으로 생성 된 매니페스트 VSIX 프로젝트를 추가 해야 합니다.  
  
## <a name="file-changes-in-project-and-item-templates"></a>프로젝트 및 항목 템플릿의 파일 변경  
새 파일을 올바르게 작성할 수 있도록 Visual Studio 2015와 Visual Studio 2017 버전의 템플릿 파일을 지점의 보여줍니다.  
  
 다음은 Visual Studio 2015에서 만든 기본 프로젝트.vstemplate 파일입니다.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<VSTemplate Version="3.0.0" Type="Project" xmlns="http://schemas.microsoft.com/developer/vstemplate/2005" xmlns:sdk="http://schemas.microsoft.com/developer/vstemplate-sdkextension/2010">  
  <TemplateData>  
    <Name>ProjectTemplate1</Name>  
    <Description>ProjectTemplate1</Description>  
    <Icon>ProjectTemplate1.ico</Icon>  
    <ProjectType>CSharp</ProjectType>  
    <RequiredFrameworkVersion>2.0</RequiredFrameworkVersion>  
    <SortOrder>1000</SortOrder>  
    <TemplateID>05b79cc9-2146-4716-a8e5-7e085cdd2221</TemplateID>  
    <CreateNewFolder>true</CreateNewFolder>  
    <DefaultName>ProjectTemplate1</DefaultName>  
    <ProvideDefaultName>true</ProvideDefaultName>  
  </TemplateData>  
  <TemplateContent>  
    <Project File="ProjectTemplate.csproj" ReplaceParameters="true">  
      <ProjectItem ReplaceParameters="true" TargetFileName="Properties\AssemblyInfo.cs">AssemblyInfo.cs</ProjectItem>  
      <ProjectItem ReplaceParameters="true" OpenInEditor="true">Class1.cs</ProjectItem>  
    </Project>  
  </TemplateContent>  
</VSTemplate>  
  
```  
  
 VSIX 프로젝트를 다시 작성에서 발생 하는.vstman 파일 (찾을 수에서 VSIX 프로젝트의 매니페스트 디렉터리)는 다음과 같습니다.  
  
```xml  
<VSTemplateManifest Version="1.0" Locale="1033" xmlns="http://schemas.microsoft.com/developer/vstemplatemanifest/2015">  
  <VSTemplateContainer TemplateType="Project">  
    <RelativePathOnDisk>CSharp\1033\ProjectTemplate1</RelativePathOnDisk>  
    <TemplateFileName>ProjectTemplate1.vstemplate</TemplateFileName>  
    <VSTemplateHeader>  
      <TemplateData xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
        <Name>ProjectTemplate1</Name>  
        <Description>ProjectTemplate1</Description>  
        <Icon>ProjectTemplate1.ico</Icon>  
        <ProjectType>CSharp</ProjectType>  
        <RequiredFrameworkVersion>2.0</RequiredFrameworkVersion>  
        <SortOrder>1000</SortOrder>  
        <TemplateID>05b79cc9-2146-4716-a8e5-7e085cdd2221</TemplateID>  
        <CreateNewFolder>true</CreateNewFolder>  
        <DefaultName>ProjectTemplate1</DefaultName>  
        <ProvideDefaultName>true</ProvideDefaultName>  
      </TemplateData>  
    </VSTemplateHeader>  
  </VSTemplateContainer>  
</VSTemplateManifest>  
  
```  
  
 제공한 정보는 [TemplateData](../extensibility/templatedata-element-visual-studio-templates.md) 요소 동일 하 게 유지 합니다.  **\<VSTemplateContainer >** 요소 관련된 서식 파일에 대 한.vstemplate 파일을 가리킵니다.  
  
 다음은 Visual Studio 2015에서 만든 기본 항목.vstemplate 파일입니다.  
  
```xml  
<?xml version="1.0" encoding="utf-8"?>  
<VSTemplate Version="3.0.0" Type="Item" xmlns="http://schemas.microsoft.com/developer/vstemplate/2005" xmlns:sdk="http://schemas.microsoft.com/developer/vstemplate-sdkextension/2010">  
  <TemplateData>  
    <Name>ItemTemplate1</Name>  
    <Description>ItemTemplate1</Description>  
    <Icon>ItemTemplate1.ico</Icon>  
    <TemplateID>bfeadf8e-a251-4109-b605-516b88e38c8d</TemplateID>  
    <ProjectType>CSharp</ProjectType>  
    <RequiredFrameworkVersion>2.0</RequiredFrameworkVersion>  
    <NumberOfParentCategoriesToRollUp>1</NumberOfParentCategoriesToRollUp>  
    <DefaultName>Class.cs</DefaultName>  
  </TemplateData>  
  <TemplateContent>  
    <References>  
      <Reference>  
        <Assembly>System</Assembly>  
      </Reference>  
    </References>  
    <ProjectItem ReplaceParameters="true">Class.cs</ProjectItem>  
  </TemplateContent>  
</VSTemplate>  
  
```  
  
 VSIX 프로젝트를 다시 작성에서 발생 하는.vstman 파일 (찾을 수에서 VSIX 프로젝트의 매니페스트 디렉터리)는 다음과 같습니다.  
  
```xml  
<VSTemplateManifest Version="1.0" Locale="1033" xmlns="http://schemas.microsoft.com/developer/vstemplatemanifest/2015">  
  <VSTemplateContainer TemplateType="Item">  
    <RelativePathOnDisk>CSharp\1033\ItemTemplate1</RelativePathOnDisk>  
    <TemplateFileName>ItemTemplate1.vstemplate</TemplateFileName>  
    <VSTemplateHeader>  
      <TemplateData xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
        <Name>ItemTemplate1</Name>  
        <Description>ItemTemplate1</Description>  
        <Icon>ItemTemplate1.ico</Icon>  
        <TemplateID>bfeadf8e-a251-4109-b605-516b88e38c8d</TemplateID>  
        <ProjectType>CSharp</ProjectType>  
        <RequiredFrameworkVersion>2.0</RequiredFrameworkVersion>  
        <NumberOfParentCategoriesToRollUp>1</NumberOfParentCategoriesToRollUp>  
        <DefaultName>Class.cs</DefaultName>  
      </TemplateData>  
    </VSTemplateHeader>  
  </VSTemplateContainer>  
</VSTemplateManifest>  
  
```  
  
 제공한 정보는  **\<TemplateData >** 요소 동일 하 게 유지 합니다.  **\<VSTemplateContainer >** 관련된 서식 파일에 대 한.vstemplate 파일을 가리키면 요소  
  
 .Vstman 파일의 다양 한 요소에 대 한 자세한 내용은 참조 [Visual Studio 템플릿 매니페스트 스키마 참조](../extensibility/visual-studio-template-manifest-schema-reference.md)합니다.  
  
## <a name="upgrades-for-extensions-installed-with-an-msi"></a>확장에 대 한 업그레이드와 함께 설치 된 프로그램입니다. MSI

다음과 같은 일반적인 템플릿 위치에 템플릿을 배포 하는 일부 MSI 기반 확장:

- **\<Visual Studio 설치 디렉터리 > \Common7\IDE\\< ProjectTemplates/ItemTemplates >**

- **\<Visual Studio 설치 디렉터리 > \Common7\IDE\Extensions\\< ExtensionName\>\\< 프로젝트/ItemTemplates >**

확장 프로그램에서 MSI 기반 배포를 수행 하는 경우 템플릿 매니페스트를 수동으로 생성 및 확장 설치에 포함 되어 있는지 확인 해야 합니다. 위에 나열 된.vstman 예제 비교 및 [Visual Studio 템플릿 매니페스트 스키마 참조](../extensibility/visual-studio-template-manifest-schema-reference.md)합니다.

프로젝트 및 항목 템플릿에 대 한 별도 매니페스트를 만들어야 하 고 루트 템플릿 지정 된 대로 위의 디렉터리를 가리켜야 합니다. 확장 및 로캘 당 한 매니페스트를 만듭니다.

## <a name="see-also"></a>참고 항목

[템플릿 검색 문제 해결](troubleshooting-template-discovery.md)  
[사용자 지정 프로젝트 및 항목 템플릿 만들기](creating-custom-project-and-item-templates.md)