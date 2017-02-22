---
title: "방법: 다중 파일 항목 템플릿 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-general"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "항목 템플릿, 다중 파일 항목 템플릿 만들기"
  - "다중 파일 항목 템플릿"
  - "Visual Studio 템플릿, 다중 파일 항목 템플릿 만들기"
ms.assetid: fe3c4257-e383-4c80-b8af-c5c521959c33
caps.latest.revision: 12
caps.handback.revision: 12
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
---
# 방법: 다중 파일 항목 템플릿 만들기
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

항목 템플릿은 하나의 항목만 지정할 수 있지만, 항목은 여러 파일로 구성되는 경우가 있습니다.  예를 들어Windows Forms항목템플릿Visual Basic에 대해 다음 세 가지 파일이 필요합니다.  
  
-   폼에 대한 코드가 들어 있는 .vb 파일  
  
-   폼에 대한 디자이너 정보가 들어 있는 .designer .vb 파일  
  
-   폼에 대한 포함된 리소스가 들어 있는 .resx 파일  
  
 다중 파일 항목 템플릿의 경우 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]에서 항목이 만들어질 때 올바른 파일 확장명이 사용되도록 매개 변수를 사용해야 합니다.  **템플릿 내보내기** 마법사를 사용하여 항목 템플릿을 만드는 경우 이러한 매개 변수가 자동으로 생성되므로 추가로 편집할 필요가 없습니다.  다음 단계에서는 매개 변수를 사용하여 올바른 파일 확장명이 만들어지도록 하는 방법을 설명합니다.  
  
### 다중 파일 항목 템플릿을 수동으로 만들려면  
  
1.  단일 파일 항목 템플릿을 만드는 것과 동일한 방식으로 항목 템플릿을 만듭니다.  자세한 내용은 [방법: 항목 템플릿 만들기](../ide/how-to-create-item-templates.md)를 참조하십시오.  
  
2.  모든 `ProjectItem` 요소에 `TargetFileName` 특성을 추가합니다.  `TargetFileName` 특성의 값을 $fileinputname$.*FileExtension*으로 설정합니다. 여기서 *FileExtension*은 템플릿에 포함될 파일의 파일 확장명입니다.  예를 들면 다음과 같습니다.  
  
    ```  
    <ProjectItem TargetFileName="$fileinputname$.vb">  
        Form1.vb  
    </ProjectItem>  
    <ProjectItem TargetFileName="$fileinputname$.Designer.vb">  
        Form1.Designer.vb  
    </ProjectItem>  
    <ProjectItem TargetFileName="$fileinputname$.resx">  
        Form1.resx  
    </ProjectItem>  
    ```  
  
     이 템플릿에서 파생된 항목이 프로젝트에 추가되는 경우 파일 이름은 사용자가 **새 항목 추가** 대화 상자에 입력한 이름을 기반으로 생성됩니다.  
  
3.  템플릿에 포함할 파일을 선택하고 선택 영역을 마우스 오른쪽 단추로 클릭한 다음 **보내기**를 클릭하고 **압축\(ZIP\) 폴더**를 클릭합니다.  선택한 파일이 .zip 파일로 압축됩니다.  
  
4.  .zip 파일을 사용자 항목 템플릿 위치에 넣습니다.  기본적으로 디렉터리 \\My Documents\\Visual Studio입니다*버전*\\Templates\\ItemTemplates\\.   자세한 내용은 [방법: 템플릿 찾기 및 구성](../ide/how-to-locate-and-organize-project-and-item-templates.md)을 참조하십시오.  
  
## 예제  
 다음 예제에서는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] Windows Forms 템플릿을 보여 줍니다.  항목이 이 템플릿을 기반으로 하여 만들어지는 경우 만들어진 세 파일의 이름은 **새 항목 추가** 대화 상자에 입력된 이름과 일치합니다.  
  
```  
<VSTemplate Version="2.0.0" Type="Item"  
    xmlns="http://schemas.microsoft.com/developer/vstemplate/2005">  
    <TemplateData>  
        <Name>Multi-file Item Template</Name>  
        <Icon>Icon.ico</Icon>  
        <Description>An example of a multi-file item template</Description>  
        <ProjectType>VisualBasic</ProjectType>  
    </TemplateData>  
    <TemplateContent>  
        <ProjectItem TargetFileName="$fileinputname$.vb" SubType="Form">  
            Form1.vb  
        </ProjectItem>  
        <ProjectItem TargetFileName="$fileinputname$.Designer.vb">  
            Form1.Designer.vb  
        </ProjectItem>  
        <ProjectItem TargetFileName="$fileinputname$.resx">  
            Form1.resx  
        </ProjectItem>  
    </TemplateContent>  
</VSTemplate>  
```  
  
## 참고 항목  
 [사용자 지정 프로젝트 및 ItemTemplate 만들기](../ide/creating-project-and-item-templates.md)   
 [방법: 항목 템플릿 만들기](../ide/how-to-create-item-templates.md)   
 [템플릿 매개 변수](../ide/template-parameters.md)   
 [방법: 템플릿 매개 변수 대체](../ide/how-to-substitute-parameters-in-a-template.md)