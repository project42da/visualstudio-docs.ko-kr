---
title: "방법: 마스터 페이지 또는 테마 가져오기 | Microsoft Docs"
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
helpviewer_keywords: 
  - "항목 가져오기[Visual Studio에서 SharePoint 개발]"
  - "Visual Studio에서 SharePoint 개발, 항목 가져오기"
ms.assetid: 8b446cca-2adb-457b-bbfd-891209290e80
caps.latest.revision: 18
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 14
---
# 방법: 마스터 페이지 또는 테마 가져오기
  마스터 페이지와 테마를 생성하고 사용하여 SharePoint 사이트의 페이지를 일관성 있는 모습으로 만들 수 있습니다.  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 이러한 요소들을 제공하진 않지만, SharePoint Designer에서 템플릿을 만든 다음 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]로 가져올 수 있습니다.  자세한 내용은 Microsoft 웹 사이트에서 [블록 구성: 페이지 및 사용자 인터페이스](http://go.microsoft.com/fwlink/?LinkID=182095) 을 참조하십시오.  
  
### 마스터 페이지나 테마를 가져오려면  
  
1.  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 SharePoint 프로젝트를 열거나 만듭니다.  
  
     SharePoint 프로젝트를 만드는 방법에 대한 자세한 내용은 [SharePoint 프로젝트 및 프로젝트 항목 템플릿](../sharepoint/sharepoint-project-and-project-item-templates.md) 를 참조하십시오.  
  
2.  메뉴 모음에서 **프로젝트**, **새 항목 추가**를 선택합니다.  
  
3.  **새 항목 추가** 대화 상자에서, **SharePoint** 노드를 확장한 후 **2010** 노드를 선택합니다.  
  
4.  SharePoint 템플릿 목록에서 **모듈** 템플릿을 선택한 다음 모듈 이름을 지정합니다.  
  
     모듈은 SharePoint의 지정된 위치에 배포하기 위한 파일 \(예 :마스터 페이지 또는 테마 파일\) 들을 포함합니다  
  
5.  모듈에서 Sample.txt 라는 기본 파일을 삭제 합니다.  
  
6.  모듈 노드를 선택합니다.  
  
7.  선택 메뉴 모음에서 **프로젝트**, **기존 항목 추가** 를 선택한 다음, 마스터 페이지나 테마 파일을 선택 합니다.  
  
     마스터 페이지 파일의 확장명은 .master이고 테마 파일의 확장명은 .thmx입니다.  
  
8.  변경 마스터 페이지를 추가한 경우, 모듈 속성에서 해당 **배포 충돌 해결** 설정을 **자동** 으로 변경합니다.  
  
    > [!NOTE]  
    >  마스터 페이지의 이름이 기본 마스터 페이지나 사용자 지정 마스터 페이지로 표시된 기존 마스터 페이지의 이름과 같은 경우 오류가 발생할 수 있습니다.  이 문제를 해결하는 방법에 대한 자세한 내용은 [연습: 사용자 지정 마스터 페이지 및 사이트 페이지를 이미지로 가져오기](../sharepoint/walkthrough-import-a-custom-master-page-and-site-page-with-an-image.md)를 참조하십시오.  
  
9. 모듈의 Elements.xml을 엽니다.  
  
     추가한 마스터 페이지 또는 테마를 참조하려면 Elements.xml 파일을 업데이트해야 합니다.  
  
10. 마스터 페이지의 경우 기존 모듈 태그를 다음 태그로 바꿉니다.  
  
    ```  
    <Module Name="[Module Name]" Url="_catalogs/masterpage">  
        <File Path="[Module Name]\[Master Page Name].master"   
          Url="[Master Page Name].master" Type="GhostableInLibrary" />  
    </Module>  
    ```  
  
     테마의 경우 기존 모듈 태그를 다음 태그로 바꿉니다.  
  
    ```  
    <Module Name="[Module Name]" Url="_catalogs/theme"   
        <File Path="[Module Name]\[Theme Name].thmx" Url="[Theme     
          Name].thmx" Type="GhostableInLibrary" />  
    </Module>  
    ```  
  
     자리 표시자 값을 모듈과 마스터 페이지 또는 테마의 실제 이름으로 바꿔야 합니다.  
  
     `Type="GhostableInLibrary"` 특성은 항목이 콘텐츠 데이터베이스에 추가되었음을 나타내고, 모듈의 `Url` 특성은 SharePoint 콘텐츠 데이터베이스에서 파일을 저장할 위치를 지정합니다.  
  
11. 마스터 페이지의 배포 범위를 변경 하려면 **솔루션 탐색기** 에서, 기능 디자이너의 기능 파일을 연 다음, 새 배포 범위를 **범위** 목록에서 선택합니다.  
  
     **웹** 값은 마스터 페이지가 프로젝트에서 현재 지정된 웹 사이트에만 적용됨을 의미합니다.  **사이트** 값은 마스터 페이지가 현재 사이트 컬렉션에 적용됨을 의미합니다. 여기에는 모든 하위 사이트와 루트 웹이 포함됩니다.  다른 값은 적용되지 않습니다.  
  
    > [!NOTE]  
    >  테마가 사이트 컬렉션 수준에만 적용되기 때문에 **사이트**가 아닌 다른 값으로 테마의 범위를 설정하지 않는 것이 좋습니다.  테마가 하위 사이트에서 사용되는 경우 오류가 발생할 수 있습니다.  
  
12. 메뉴 모음에서 **빌드**, **솔루션 배포**를 선택합니다.  
  
13. 파일이 올바르게 배포 된 여부를 확인 하려면, SharePoint 사이트를 열고, **사이트 작업** 메뉴를 선택한 다음, **사이트 설정** 명령을 선택하고, **마스터 페이지** 링크 또는 **테마** 링크를 선택합니다.  
  
     마스터 페이지 또는 테마의 목록이 나타나고 가져온 테마 또는 마스터 페이지를 포함 합니다.  
  
## 참고 항목  
 [마스터 페이지](http://go.microsoft.com/fwlink/?LinkId=184955)   
 [기존 SharePoint 사이트에서 항목 가져오기](../sharepoint/importing-items-from-an-existing-sharepoint-site.md)   
 [SharePoint에 대한 페이지 만들기](../sharepoint/creating-pages-for-sharepoint.md)   
 [모듈을 사용하여 솔루션에 파일 포함](../sharepoint/using-modules-to-include-files-in-the-solution.md)  
  
  