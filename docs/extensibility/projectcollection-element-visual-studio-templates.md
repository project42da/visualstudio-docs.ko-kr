---
title: "ProjectCollection 요소(Visual Studio 템플릿) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "http://schemas.microsoft.com/developer/vstemplate/2005#ProjectCollection"
helpviewer_keywords: 
  - "<ProjectCollection> 요소[Visual Studio 템플릿]"
  - "ProjectCollection 요소[Visual Studio 템플릿]"
ms.assetid: deb27180-2035-49ed-b835-c47bb3cd2f8f
caps.latest.revision: 8
ms.author: "gregvanl"
manager: "ghogen"
caps.handback.revision: 8
---
# ProjectCollection 요소(Visual Studio 템플릿)
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

다중 프로젝트 템플릿의 구성과 내용을 지정합니다.  
  
## 구문  
  
```  
<ProjectCollection>  
    <ProjectTemplateLink> ... </ProjectTemplateLink>  
    <SolutionFolder> ... </SolutionFolder>  
</ProjectCollection>  
```  
  
## 특성 및 요소  
 다음 단원에서는 특성, 자식 요소 및 부모 요소에 대해 설명합니다.  
  
### 특성  
 없음  
  
### 자식 요소  
  
|요소|설명|  
|--------|--------|  
|[ProjectTemplateLink](../extensibility/projecttemplatelink-element-visual-studio-templates.md)|선택적 요소입니다.<br /><br /> 다중 프로젝트 템플릿에 있는 프로젝트를 지정합니다.|  
|[SolutionFolder](../extensibility/solutionfolder-element-visual-studio-templates.md)|선택적 요소입니다.<br /><br /> 다중 프로젝트 템플릿의 프로젝트를 그룹화합니다.|  
  
### 부모 요소  
  
|요소|설명|  
|--------|--------|  
|[TemplateContent](../extensibility/templatecontent-element-visual-studio-templates.md)|필수적 요소입니다.<br /><br /> 템플릿 내용을 지정합니다.|  
  
## 설명  
 다중 프로젝트 템플릿은 두 개 이상의 프로젝트에 대한 컨테이너로 사용됩니다.  `ProjectCollection` 요소는 템플릿에 포함할 프로젝트를 지정하는 데 사용됩니다.  다중 프로젝트 템플릿에 대한 자세한 내용은 [방법: 다중 프로젝트 템플릿 만들기](../ide/how-to-create-multi-project-templates.md)를 참조하십시오.  
  
## 예제  
 이 예제에서는 단순한 다중 프로젝트 루트 .vstemplate 파일을 보여 줍니다.  이 예제에서 템플릿에는 `My Windows Application` 프로젝트와 `My Class Library` 프로젝트가 들어 있습니다.  `ProjectTemplateLink` 요소의 `ProjectName` 특성은 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]가 이 프로젝트에 할당할 이름을 설정합니다.  `ProjectName` 특성이 없으면 .vstemplate 파일의 이름이 프로젝트 이름으로 사용됩니다.  
  
```  
<VSTemplate Version="3.0.0" Type="ProjectGroup"  
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <Name>Multi-Project Template Sample</Name>  
        <Description>An example of a multi-project template</Description>  
        <Icon>Icon.ico</Icon>  
        <ProjectType>VisualBasic</ProjectType>  
    </TemplateData>  
    <TemplateContent>  
        <ProjectCollection>  
            <ProjectTemplateLink ProjectName="My Windows Application">  
                WindowsApp\MyTemplate.vstemplate  
            </ProjectTemplateLink>  
            <ProjectTemplateLink ProjectName="My Class Library">  
                ClassLib\MyTemplate.vstemplate  
            </ProjectTemplateLink>  
        </ProjectCollection>  
    </TemplateContent>  
</VSTemplate>  
```  
  
## 참고 항목  
 [Visual Studio 템플릿 스키마 참조](../extensibility/visual-studio-template-schema-reference.md)   
 [사용자 지정 프로젝트 및 ItemTemplate 만들기](../ide/creating-project-and-item-templates.md)   
 [방법: 다중 프로젝트 템플릿 만들기](../ide/how-to-create-multi-project-templates.md)