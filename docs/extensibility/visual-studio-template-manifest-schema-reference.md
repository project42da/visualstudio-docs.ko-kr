---
title: "Visual Studio 템플릿 매니페스트 스키마 참조 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bc7d0a81-0df5-41a9-a912-1b30e5da1d13
caps.latest.revision: "3"
author: gregvanl
ms.author: gregvanl
manager: ghogen
ms.workload: vssdk
ms.openlocfilehash: 87f676ef30da7c667c4ce2b688520a49ed1931c3
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="visual-studio-template-manifest-schema-reference"></a>Visual Studio 템플릿 매니페스트 스키마 참조
이 스키마는 Visual Studio 프로젝트 또는 항목 템플릿에서 생성 하는 Visual Studio 템플릿 매니페스트 (.vstman) 파일의 형식을 설명 하 고 위치 및 서식 파일에 대 한 기타 관련 정보를 설명 합니다.  
  
 : 있기 때문에 별도 항목 및 프로젝트 템플릿 디렉터리, 매니페스트 프로젝트 및 항목 템플릿의 혼합이 없어야 합니다.  
  
> [!IMPORTANT]
>  이 매니페스트는 Visual Studio 2017부터 사용할 수 있습니다.  
  
## <a name="vstemplatemanifest-element"></a>VSTemplateManifest 요소  
 매니페스트 루트 요소입니다.  
  
### <a name="attributes"></a>특성  
  
-   **버전**: 템플릿 매니페스트의 버전을 나타내는 문자열입니다. 필수.  
  
-   **로캘**: 로캘 또는 로캘의 템플릿 매니페스트를 나타내는 문자열입니다. 로캘 값 각 로캘에 대 한 별도 매니페스트를 사용 해야 하므로 모든 서식 파일에 적용 됩니다. 선택 사항입니다.  
  
### <a name="child-elements"></a>자식 요소  
  
-   **VSTemplateContainer** 선택 사항입니다.  
  
-   **VSTemplateDir** 선택 사항입니다.  
  
### <a name="parent-element"></a>부모 요소  
 없음  
  
## <a name="vstemplatecontainer"></a>VSTemplateContainer  
 요소 매니페스트 하는 서식 파일의 컨테이너입니다. 매니페스트를 정의 하는 각 템플릿에 대 한 하나의 템플릿 컨테이너를 있습니다.  
  
### <a name="attributes"></a>특성  
 **VSTemplateType** : 서식 파일의 유형을 지정 하는 문자열 값 (`"Project"`, `"Item"`, 또는 `"ProjectGroup"`). 필수  
  
### <a name="child-elements"></a>자식 요소  
  
-   **RelativePathOnDisk**: 디스크에 있는 템플릿 파일의 상대 경로입니다. 이 위치에 표시 된 서식 파일 트리에서 또한 서식 파일의 위치를 정의 고 **새 프로젝트** 또는 **새 항목** 대화 상자. 디렉터리 및 개별 파일을 배포 하는 템플릿에 대 한이 경로 템플릿 파일을 포함 하는 디렉터리를 가리킵니다. 템플릿의.zip 파일로 배포 된 경우이 경로는.zip 파일을 경로 여야 합니다.  
  
-   **VSTemplateHeader** : A [TemplateData](../extensibility/templatedata-element-visual-studio-templates.md) 헤더를 설명 하는 요소입니다.  
  
### <a name="parent-element"></a>부모 요소  
 **VSTemplateManifest**  
  
## <a name="vstemplatedir"></a>VSTemplateDir  
 템플릿이 있는 디렉터리에 설명 합니다. 매니페스트는 여러 개 포함할 수 **VSTemplateDir** 지역화 된 이름 및 정렬 순서 디렉터리에 대 한 템플릿 범주 트리에서 모양을 제어 하는 항목입니다.  
  
 디자인으로 인해 **VSTemplateDir** -로캘 지정한 매니페스트에만 항목이 표시 됩니다.  
  
### <a name="attributes"></a>특성  
 없음  
  
### <a name="child-elements"></a>자식 요소  
  
-   **RelativePath**: 서식 파일의 경로입니다. 모든 매니페스트에 대 한 첫 번째 승리 되므로 경로 변수당 하나의 항목이 수 있습니다.  
  
-   **LocalizedName**: A **NameDescriptionIcon** 지역화 된 이름을 지정 하는 요소입니다. 선택 사항입니다.  
  
-   **SortOrder** : 정렬 순서를 지정 하는 문자열입니다. 선택 사항입니다.  
  
-   **ParentFolderOverrideName**: 부모 폴더의 재정의 된 이름입니다. 선택 사항입니다. 이 요소에는 **이름** 특성 이름을 지정 하는 문자열 값입니다.  
  
### <a name="parent-element"></a>부모 요소  
 **VSTemplateManifest**  
  
## <a name="namedescriptionicon"></a>NameDescriptionIcon  
 이름 및 설명을 지역화 된 템플릿에 대 수를 지정합니다. 참조 **LocalizedName** 위에 있습니다.  
  
### <a name="attributes"></a>특성  
  
-   **패키지**: 패키지를 지정 하는 문자열 값입니다. 선택 사항입니다.  
  
-   **ID**: ID를 지정 하는 문자열 값 선택 사항입니다.  
  
### <a name="child-elements"></a>자식 요소  
 없음  
  
### <a name="parent-element"></a>부모 요소  
 **LocalizedName**  
  
## <a name="examples"></a>예제  
 다음은 프로젝트 템플릿.vstman 파일의 예입니다.  
  
```xml  
<VSTemplateManifest Version="1.0" Locale="1033" xmlns="http://schemas.microsoft.com/developer/vstemplatemanifest/2015">  
  <VSTemplateContainer TemplateType="Project">  
    <RelativePathOnDisk>CSharp\1033\TestProjectTemplate</RelativePathOnDisk>  
    <TemplateFileName>TestProjectTemplate.vstemplate</TemplateFileName>  
    <VSTemplateHeader>  
      <TemplateData xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
        <Name>TestProjectTemplate</Name>  
        <Description>TestProjectTemplate</Description>  
        <Icon>TestProjectTemplate.ico</Icon>  
        <ProjectType>CSharp</ProjectType>  
        <RequiredFrameworkVersion>2.0</RequiredFrameworkVersion>  
        <SortOrder>1000</SortOrder>  
        <TemplateID>aac0aeea-7883-4003-992f-937d53d70ab1</TemplateID>  
        <CreateNewFolder>true</CreateNewFolder>  
        <DefaultName>TestProjectTemplate</DefaultName>  
        <ProvideDefaultName>true</ProvideDefaultName>  
      </TemplateData>  
    </VSTemplateHeader>  
  </VSTemplateContainer>  
</VSTemplateManifest>  
  
```  
  
 다음은 항목 템플릿.vstman 파일의 예입니다.  
  
```  
VSTemplateManifest Version="1.0" Locale="1033" xmlns="http://schemas.microsoft.com/developer/vstemplatemanifest/2015">  
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