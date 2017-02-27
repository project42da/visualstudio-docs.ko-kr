---
title: "방법: 수동으로 웹 템플릿 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "프로젝트 템플릿[Visual Studio], 웹"
  - "템플릿[Visual Studio], 웹"
  - "Visual Studio 템플릿, 웹"
  - "웹 템플릿[Visual Studio]"
ms.assetid: 731c4027-a152-48c5-bfc4-93490bf1949f
caps.latest.revision: 17
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 17
---
# 방법: 수동으로 웹 템플릿 만들기
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

웹 템플릿은 다른 종류의 템플릿과 약간 다르게 만듭니다.  웹 프로젝트 템플릿은 **새 웹 사이트 추가** 대화 상자에 나타나고 웹 프로젝트 항목은 프로그래밍 언어별로 분류되므로 .vstemplate 파일에서 템플릿을 웹 템플릿으로 지정하고 프로그래밍 언어를 식별해야 합니다.  
  
> [!NOTE]
>  웹 템플릿에는 `Project` 요소의 `File` 특성을 사용하여 지정되는 빈 .webproj 파일이 들어 있어야 합니다.  웹 프로젝트에 프로젝트 파일이 필요하지 않더라도 웹 템플릿이 제대로 작동하기 위해서는 이 파일이 필요합니다.  
  
### 웹 템플릿을 수동으로 만들려면  
  
1.  웹 프로젝트를 만듭니다.  
  
2.  프로젝트에서 파일을 수정 또는 삭제하거나 프로젝트에 새 파일을 추가합니다.  
  
3.  XML 파일을 만들고 .vstemplate 파일 확장명을 사용하여 프로젝트와 같은 디렉터리에 이 파일을 저장합니다.  [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서는 이 파일을 프로젝트에 추가하지 마십시오.  
  
4.  프로젝트 템플릿 메타데이터를 제공하도록 .vstemplate XML 파일을 작성합니다.  자세한 내용은 다음 단원의 예제를 참조하십시오.  
  
5.  .vstemplate 파일에서 `ProjectType` 요소를 찾고 텍스트 값을 `Web`으로 설정합니다.  
  
6.  `ProjectType` 요소 뒤에 `ProjectSubType` 요소를 추가하고 텍스트 값을 템플릿의 프로그래밍 언어로 설정합니다.  프로그래밍 언어는 다음  값 중 하나로 설정될 수 있습니다.  
  
    -   CSharp  
  
    -   VisualBasic  
  
     예를 들면 다음과 같습니다.  
  
    ```  
    <TemplateData>  
        ...  
        <ProjectType>Web</ProjectType>  
        <ProjectSubType>CSharp</ProjectSubType>  
        ...  
    </TemplateData>  
    ```  
  
7.  .vstemplate 파일이 포함되어 있는 템플릿에서 파일을 선택하고 선택 영역을 마우스 오른쪽 단추로 클릭한 다음 **보내기**를 클릭하고 **압축\(ZIP\) 폴더**를 클릭합니다.  파일이 .zip 파일로 압축됩니다.  
  
8.  .zip 템플릿 파일을 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 프로젝트 템플릿 디렉터리에 넣습니다.  기본적으로이 디렉터리 \\My Documents\\Visual Studio입니다*버전*\\My Exported Templates\\.  
  
## 예제  
 다음 예제에서는 웹 프로젝트 템플릿에 대한 기본 .vstemplate 파일을 보여 줍니다.  
  
```  
<VSTemplate Version="2.0.0" Type="Project"  
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">>  
    <TemplateData>  
        <Name>MyWebProjecStarterKit</Name>  
        <Description>A simple Web template</Description>  
        <Icon>icon.ico</Icon>  
        <ProjectType>Web</ProjectType>  
        <ProjectSubType>CSharp</ProjectSubType>  
        <DefaultName>WebSite</DefaultName>  
    </TemplateData>  
    <TemplateContent>  
        <Project File="WebApplication.webproj">  
            <ProjectItem>icon.ico</ProjectItem>  
            <ProjectItem OpenInEditor="true">Default.aspx</ProjectItem>  
            <ProjectItem>Default.aspx.cs</ProjectItem>  
        </Project>  
    </TemplateContent>  
</VSTemplate>  
```  
  
## 참고 항목  
 [사용자 지정 프로젝트 및 ItemTemplate 만들기](../ide/creating-project-and-item-templates.md)   
 [Visual Studio 템플릿 스키마 참조](../extensibility/visual-studio-template-schema-reference.md)