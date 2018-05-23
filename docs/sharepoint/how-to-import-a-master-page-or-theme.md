---
title: '방법: 마스터 페이지 또는 테마 가져오기 | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, importing items
- importing items [SharePoint development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: d28d178e5592d9cdf6d4aba6f642a869c12cc78f
ms.sourcegitcommit: 1466ac0f49ebf7448ea4507ae3f79acb25d51d3e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/22/2018
---
# <a name="how-to-import-a-master-page-or-theme"></a>방법: 마스터 페이지 또는 테마 가져오기
  제공할 수 있습니다 페이지 SharePoint 사이트에서 일관 된 모양을 만들고 마스터 페이지 및 테마를 사용 하 여 합니다. [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 이러한 요소에 대 한 템플릿을 제공 하지 않지만 SharePoint Designer에서 만들로 가져올 수 있습니다 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]합니다. 자세한 내용은 참조 [문서 블록: 페이지 및 사용자 인터페이스](http://go.microsoft.com/fwlink/?LinkID=182095) Microsoft 웹 사이트입니다.  
  
### <a name="to-import-a-master-page-or-theme"></a>마스터 페이지 또는 테마 가져오기  
  
1.  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]를 만들거나 SharePoint 프로젝트를 엽니다.  
  
     SharePoint 프로젝트를 만드는 방법에 대 한 정보를 참조 하십시오. [SharePoint 프로젝트 및 프로젝트 항목 템플릿](../sharepoint/sharepoint-project-and-project-item-templates.md)합니다.  
  
2.  메뉴 모음에서 **프로젝트**, **새 항목 추가**합니다.  
  
3.  에 **새 항목 추가** 대화 상자에서 **SharePoint** 노드를 선택한 후는 **2010** 노드.  
  
4.  SharePoint 템플릿의 목록에서 선택 된 **모듈** 서식 파일을 모듈에 대 한 이름을 지정 합니다.  
  
     모듈 파일 (예: 마스터 페이지 또는 테마 파일) 배포를 SharePoint에서 지정한 위치에 포함 되어 있습니다.  
  
5.  모듈에서 Sample.txt 라고 하는 기본 파일을 삭제 합니다.  
  
6.  모듈 노드를 선택 합니다.  
  
7.  메뉴 모음에서 **프로젝트**, **기존 항목 추가**, 마스터 페이지 또는 테마 파일을 선택 합니다.  
  
     마스터 페이지 파일 확장명이.master 고 테마 파일은.thmx 확장입니다.  
  
8.  마스터 페이지를 추가한 경우 변경 해당 **배포 충돌 해결** 설정을 **자동** 모듈의 속성에 있습니다.  
  
    > [!NOTE]  
    >  마스터 페이지의 이름이 기본 마스터 페이지 또는 사용자 지정 마스터 페이지로 표시 된 기존 마스터 페이지 이름과 동일한 경우 오류가 발생할 수 있습니다. 이 문제를 해결 하는 방법에 대 한 정보를 참조 하십시오. [연습: 사용자 지정 마스터 페이지 및 사이트 페이지를 이미지로 가져오기](../sharepoint/walkthrough-import-a-custom-master-page-and-site-page-with-an-image.md)합니다.  
  
9. 모듈에서 Elements.xml을 엽니다.  
  
     마스터 페이지 또는 테마를 추가한 참조 Elements.xml 파일을 업데이트 해야 합니다.  
  
10. 마스터 페이지에 대 한 기존 모듈 태그를 다음 태그로 바꿉니다.  
  
    ```xml  
    <Module Name="[Module Name]" Url="_catalogs/masterpage">  
        <File Path="[Module Name]\[Master Page Name].master"   
          Url="[Master Page Name].master" Type="GhostableInLibrary" />  
    </Module>  
    ```  
  
     테마에 대 한 기존 모듈 태그를 다음 태그로 바꿉니다.  
  
    ```xml  
    <Module Name="[Module Name]" Url="_catalogs/theme"   
        <File Path="[Module Name]\[Theme Name].thmx" Url="[Theme     
          Name].thmx" Type="GhostableInLibrary" />  
    </Module>  
    ```  
  
     자리 표시자 값 모듈 및 마스터 페이지 또는 테마의 실제 이름으로 대체 해야 합니다.  
  
     특성 `Type="GhostableInLibrary"` 항목 콘텐츠 데이터베이스에 추가 됩니다 나타냅니다 및 `Url` 모듈의 특성을 SharePoint 콘텐츠 데이터베이스에 파일을 저장할 위치를 지정 합니다.  
  
11. 마스터 페이지에 대 한 배포 범위를 변경 하려면 **솔루션 탐색기**를 기능 디자이너에서 기능 파일을 열고에서 새 배포 범위를 선택 합니다는 **범위** 목록입니다.  
  
     값이 **웹** 마스터 페이지는 현재 프로젝트에 지정 되어 있는 웹 사이트에만 적용 됩니다.을 의미 합니다. 값이 **사이트** 마스터 페이지 적용 현재 사이트 모음의 모든 하위 사이트 및 루트 웹을 포함 하는 것을 의미 합니다. 다른 값을 적용 하지 않습니다.  
  
    > [!NOTE]  
    >  사이트 모음 수준에만 테마를 적용 하기 때문에 설정 하지 않으면 테마의 범위 어디에 아닌 다른 것이 좋습니다 **사이트**합니다. 테마 하위 사이트에 사용 되는 경우 오류가 발생할 수 있습니다.  
  
12. 메뉴 모음에서 **빌드**, **솔루션 배포**합니다.  
  
13. 파일이 올바르게 배포 되었는지 확인 하려면를 SharePoint 사이트를 열고는 **사이트 작업** 메뉴에서 선택 된 **사이트 설정** 명령을 실행 하 고 다음 중 하나를 선택는 **마스터 페이지**  링크 또는 **테마** 링크 합니다.  
  
     마스터 페이지 또는 테마 목록이 나타나고 가져온 테마 또는 마스터 페이지를 포함 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [마스터 페이지](http://go.microsoft.com/fwlink/?LinkId=184955)   
 [기존 SharePoint 사이트에서 항목 가져오기](../sharepoint/importing-items-from-an-existing-sharepoint-site.md)   
 [SharePoint에 대 한 페이지 만들기](../sharepoint/creating-pages-for-sharepoint.md)   
 [모듈을 사용하여 솔루션에 파일 포함](../sharepoint/using-modules-to-include-files-in-the-solution.md)  
  
  