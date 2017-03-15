---
title: "Visual Studio 템플릿을 매니페스트 스키마 참조 | Microsoft 문서"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: bc7d0a81-0df5-41a9-a912-1b30e5da1d13
caps.latest.revision: 3
ms.author: gregvanl
manager: ghogen
translation.priority.mt:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 512014c5070e4314ad2b7d0e8c5c404c43f32cd9
ms.openlocfilehash: 0f4abf286dc8b1cf00e47468ddaa4831747a059d
ms.lasthandoff: 02/22/2017

---
# <a name="visual-studio-template-manifest-schema-reference"></a>Visual Studio 템플릿 매니페스트 스키마 참조
이 스키마는 Visual Studio 프로젝트 또는 항목 템플릿에서 생성 하는 Visual Studio 템플릿 (.vstman) 매니페스트 파일의 형식을 설명 하 고 위치 및 템플릿에 대 한 기타 관련 정보에 설명 합니다.  
  
 : 있기 때문에 별도 항목 및 프로젝트 서식 파일 디렉터리, 매니페스트 항목 및 프로젝트 템플릿 혼합이 없어야 합니다.  
  
> [!IMPORTANT]
>  이 매니페스트는 Visual Studio 2017부터 사용할 수 있습니다.  
  
## <a name="vstemplatemanifest-element"></a>VSTemplateManifest 요소  
 매니페스트의 루트 요소입니다.  
  
### <a name="attributes"></a>특성  
  
-   **버전**: 템플릿 매니페스트의 버전을 나타내는 문자열입니다. 필수 요소.  
  
-   **로캘**: 로캘 또는 로캘의 템플릿 매니페스트의 나타내는 문자열입니다. 로캘 값은 각 로캘에 대해 별도 매니페스트를 사용 해야 하므로 모든 서식 파일에 적용 됩니다. 선택적 요소.  
  
### <a name="child-elements"></a>자식 요소  
  
-   **VSTemplateContainer** 선택 사항입니다.  
  
-   **VSTemplateDir** 선택 사항입니다.  
  
### <a name="parent-element"></a>부모 요소  
 없음  
  
## <a name="vstemplatecontainer"></a>VSTemplateContainer  
 서식 파일의 컨테이너 요소 매니페스트. 매니페스트를 정의 하는 각 템플릿에 대 한 템플릿 컨테이너를 있습니다.  
  
### <a name="attributes"></a>특성  
 **VSTemplateType** : 서식 파일의 형식을 지정 하는 문자열 값 (`"Project"`, `"Item"`, 또는 `"ProjectGroup"`). 필수  
  
### <a name="child-elements"></a>자식 요소  
  
-   **RelativePathOnDisk**: 디스크에 있는 템플릿 파일의 상대 경로입니다. 이 위치에 표시 된 템플릿 트리에서 또한 서식 파일의 위치를 정의 **새 프로젝트** 또는 **새 항목** 대화 합니다. 디렉터리 및 개별 파일을 배포 하는 템플릿의 경우이 경로 템플릿 파일을 포함 하는 디렉터리를 가리킵니다. 템플릿 배포를.zip 파일로,이 경로.zip 파일의 경로를 이어야 합니다.  
  
-   **VSTemplateHeader** : A [TemplateData](../extensibility/templatedata-element-visual-studio-templates.md) 헤더를 설명 하는 요소입니다.  
  
### <a name="parent-element"></a>부모 요소  
 **VSTemplateManifest**  
  
## <a name="vstemplatedir"></a>VSTemplateDir  
 템플릿이 있는 디렉터리에 설명 합니다. 매니페스트는 여러 개 포함할 수 **VSTemplateDir** 지역화 된 이름 및 정렬 순서 디렉터리에 대 한 템플릿 범주 트리에서 모양을 제어 하는 항목입니다.  
  
 자신의 디자인으로 인해 **VSTemplateDir** 항목이 아닌 로캘 지정한 매니페스트에만 표시 됩니다.  
  
### <a name="attributes"></a>특성  
 없음  
  
### <a name="child-elements"></a>자식 요소  
  
-   **RelativePath**: 서식 파일의 경로입니다. 있을 수 경로 당 항목이 하나만 있으므로 모든 매니페스트에 대 한 첫 번째 우선 합니다.  
  
-   **LocalizedName**: A **NameDescriptionIcon** 지역화 된 이름을 지정 하는 요소입니다. 선택적 요소.  
  
-   **SortOrder** : 정렬 순서를 지정 하는 문자열입니다. 선택적 요소.  
  
-   **ParentFolderOverrideName**: 부모 폴더의 이름을 재정의 합니다. 선택적 요소. 이 요소에는 **이름** 특성 이름을 지정 하는 문자열 값입니다.  
  
### <a name="parent-element"></a>부모 요소  
 **VSTemplateManifest**  
  
## <a name="namedescriptionicon"></a>NameDescriptionIcon  
 이름과 지역화 된 템플릿 수에 대 한 설명을 지정합니다. 참조 **LocalizedName** 위에 있습니다.  
  
### <a name="attributes"></a>특성  
  
-   **패키지**: 패키지를 지정 하는 문자열 값입니다. 선택적 요소.  
  
-   **ID**: ID를 지정 하는 문자열 값 선택적 요소.  
  
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
