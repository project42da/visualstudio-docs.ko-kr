---
title: "방법: 모듈을 사용하여 파일 포함 | Microsoft Docs"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "VB"
  - "CSharp"
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "모듈[Visual Studio에서 SharePoint 개발]"
  - "Visual Studio에서 SharePoint 개발, 모듈"
ms.assetid: 16ac3c3b-8219-466c-8550-6109357f2f9a
caps.latest.revision: 12
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 11
---
# 방법: 모듈을 사용하여 파일 포함
  *모듈*\([!INCLUDE[vbprvb](../sharepoint/includes/vbprvb-md.md)] 모듈과 혼동하면 안 됨\)은 ASPX 마스터 페이지, 텍스트 파일, 이미지 등의 파일을 SharePoint에 배포할 수 있도록 하는 컨테이너입니다.  
  
 파일을 문서 라이브러리에 배포하거나 문서 라이브러리 외부에 일반 파일\(예: default.aspx\)로 배포할 수 있습니다.  파일을 문서 라이브러리에 추가하려면 `Type="GhostableInLibrary"`를 **File** 요소의 특성으로 지정합니다.  이렇게 설정하면 SharePoint에서는 파일이 라이브러리에 추가될 때 파일과 함께 제공할 목록 항목을 만듭니다.  파일을 문서 라이브러리 외부에 배포하려면 `Type="Ghostable"`을 지정하거나 **Type** 특성을 생략합니다.  
  
## SharePoint 솔루션에 모듈 추가  
  
#### 모듈을 추가하려면  
  
1.  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 SharePoint 프로젝트를 열거나 만듭니다.  
  
     자세한 내용은 [SharePoint 프로젝트 및 프로젝트 항목 템플릿](../sharepoint/sharepoint-project-and-project-item-templates.md)을 참조하십시오.  
  
2.  **솔루션 탐색기**에서 프로젝트 노드를 선택한 다음 메뉴 모음에서 **프로젝트**, **화면 추가**를 선택합니다.  
  
     **새 항목 추가** 대화 상자가 열립니다.  
  
3.  SharePoint 템플릿 목록에서, **모듈** 템플릿을 선택한 다음 **확인** 버튼을 선택합니다.  
  
     이 단계에서 Module1이라는 새 노드가 프로젝트에서 만들어집니다.  
  
4.  Module1에서, Sample.txt 파일을 삭제 합니다.  
  
     Sample.txt는 예제로 사용하기 위해 모든 새 모듈에 포함되어 있으며 필요하지 않습니다. 이 파일을 삭제하면 모듈의 Elements.xml 파일에서 해당 항목도 제거됩니다.  
  
5.  SharePoint의 특정 폴더 구조에 파일을 배포하고 싶은 경우, Module1 노드를 선택하여 해당 폴더를 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 의 Module1에 만든 다음, 메뉴 모음에서 **프로젝트**, **새 폴더** 를 선택합니다.  
  
6.  파일을 추가할 폴더를 선택한 다음, 메뉴 모음에서 **프로젝트**, **기존 항목 추가**를 선택합니다.  
  
7.  SharePoint에 배포할 파일을 하나 이상 선택하고 **추가** 버튼을 선택합니다.  
  
     프로젝트에 파일을 추가하면 파일에 대한 항목이 모듈의 Elements.xml 파일에 자동으로 추가됩니다.  프로젝트가 배포되면 파일이 SharePoint 서버에 복사됩니다. 복사되는 위치는 프로젝트의 루트 디렉터리에 상대적이며 **File** 요소의 **Url** 특성으로 지정됩니다\(예: `Url="Module1/New Folder/SomeFile.doc`\).  파일의 배포 위치를 변경하려면 **솔루션 탐색기**에서 파일을 다른 폴더로 이동하거나 파일의 **Url** 설정을 변경합니다.  
  
8.  문서 라이브러리에 표시할 파일에 대해 Elements.xml에서 `Type="GhostableInLibrary"` 특성을 파일의 항목에 추가합니다.  예를 들면 다음과 같습니다.  
  
    ```  
    <File Path="Module1\Some Folder\SomePage.aspx" Url="Module1/Some Folder/SomePage.aspx" Type="GhostableInLibrary" />  
    ```  
  
9. 프로젝트를 배포합니다.  
  
     파일이 SharePoint에서 지정된 위치에 복사됩니다.  
  
## 참고 항목  
 [SharePoint 솔루션 패키징 및 배포](../sharepoint/packaging-and-deploying-sharepoint-solutions.md)   
 [Developing SharePoint Solutions](../sharepoint/developing-sharepoint-solutions.md)  
  
  