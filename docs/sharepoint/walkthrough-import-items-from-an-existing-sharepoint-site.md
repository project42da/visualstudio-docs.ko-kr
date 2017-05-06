---
title: "연습: 기존 SharePoint 사이트에서 항목 가져오기"
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
  - "항목 가져오기[Visual Studio에서 SharePoint 개발]"
  - "Visual Studio에서 SharePoint 개발, 항목 가져오기"
ms.assetid: faac3309-88d7-4fb2-8392-feda07fc00e5
caps.latest.revision: 21
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 20
---
# 연습: 기존 SharePoint 사이트에서 항목 가져오기
  이 연습에서는 기존 SharePoint 사이트의 항목을 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] SharePoint 프로젝트로 가져오는 방법을 보여 줍니다.  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   사용자 지정 사이트 열\(*필드*라고도 함\)을 추가하여 SharePoint 사이트 사용자 지정  
  
-   SharePoint 사이트를 .wsp 파일로 내보내기  
  
-   .wsp 가져오기 프로젝트를 사용하여 .wsp 파일을 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] SharePoint로 가져오기  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## 사전 요구 사항  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   지원되는 [!INCLUDE[TLA#tla_win](../sharepoint/includes/tlasharptla-win-md.md)] 및 SharePoint 버전.  자세한 내용은 [SharePoint 솔루션 개발 요구 사항](../sharepoint/requirements-for-developing-sharepoint-solutions.md)을 참조하십시오.  
  
-   Visual Studio  
  
## SharePoint 사이트 사용자 지정  
 이 예제에서는 새 사이트 열을 추가하고 나중에 사용할 다른 하위 사이트를 만들어 SharePoint 하위 사이트를 만들고 사용자 지정합니다.  나중에 첫 번째 하위 사이트를 .wsp 파일로 내보낸 다음 .wsp 가져오기 프로젝트를 사용하여 사용자 지정 사이트 열을 두 번째 하위 사이트로 가져옵니다.  
  
#### SharePoint 사이트를 만들고 사용자 지정하려면  
  
1.  웹 브라우저를 사용하여 SharePoint 사이트\(예: http:\/\/*system name*\/SitePages\/Home.aspx\)를 엽니다.  
  
2.  **사이트 작업** 메뉴를 열고 **새 사이트** 를 선택하여 기본 SharePoint 사이트에서 하위 사이트를 만듭니다.  
  
3.  사이트의 **만들기** 대화 상자에서 **빈 사이트** 형식을 선택합니다.  
  
4.  **제목** 상자에 Site Column Test 1을 입력하고 **URL 이름** 상자에 columntest1을 입력한 다음 다른 설정은 기본값 그대로 둔 채 **만들기** 버튼을 선택합니다.  
  
5.  사이트를 만든 후 브라우저에서 기본 사이트인 http:\/\/*system name*\/SitePages\/Home.aspx로 다시 이동합니다.  
  
6.  **사이트 작업** 메뉴에서 **새 사이트**를 선택하고 **새 사이트** 형식을 선택하여 기본 SharePoint 사이트에서 다시 빈 하위 사이트를 만듭니다.  
  
7.  **제목** 상자에 Site Column Test 2를 입력하고 **URL 이름** 상자에 columntest2를 입력한 다음 다른 설정은 기본값 그대로 둔 채 **만들기** 버튼을 선택합니다.  
  
8.  첫 번째 하위 사이트인 http:\/\/*SystemName*\/columntest1\/default.aspx 로 이동합니다.  
  
9. **사이트 작업** 메뉴에서 **사이트 설정** 을 선택하여 사이트 설정 페이지를 표시합니다.  
  
10. **갤러리** 섹션에서 **사이트 열** 링크를 선택합니다.  
  
11. **사이트 열 갤러리** 창의 맨 위에 있는 **만들기** 버튼을 선택합니다.  
  
12. **열 이름** 상자에 Test Column을 입력하고, 다른 기본값은 유지한 다음, **확인** 버튼을 선택합니다.  
  
13. 사이트 열 갤러리의 사용자 지정 열 제목 아래에 **테스트 열** 열이 표시됩니다.  
  
## SharePoint 사이트 내보내기  
 다음으로, [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] SharePoint 프로젝트로 가져올 SharePoint 항목과 요소가 포함된 SharePoint 설치 파일\(.wsp\)을 가져옵니다.  .wsp 파일이 아직 없으면 기존 SharePoint 사이트에서 새로 만들어야 합니다.  이 예제에서는 기본 SharePoint 사이트를 .wsp 파일로 내보냅니다.  
  
> [!IMPORTANT]  
>  다음 절차를 수행하는 동안 런타임 오류가 표시되는 경우 SharePoint 사이트에 액세스할 수 있는 시스템에서 절차를 수행해야 합니다.  
  
#### 기존 SharePoint 사이트를 내보내려면  
  
1.  SharePoint 사이트에서 **사이트 작업** 탭의 **사이트 설정** 을 선택하여 사이트 설정 페이지를 표시합니다.  
  
2.  사이트 설정 페이지의 **사이트 작업** 섹션에서 **템플릿으로 저장** 링크를 선택합니다.  
  
3.  **파일 이름** 상자에 ExampleSite를 입력하고 **템플릿 이름** 상자에 Example Site를 입력합니다.  
  
4.  이 예제에서는 **콘텐츠 포함** 확인란을 선택 취소된 상태로 둡니다.  
  
     이 상자를 선택하면 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 목록 및 문서 라이브러리와 해당 내용을 .wsp 파일에 저장합니다.  이 기능이 유용한 경우도 있지만 이 예제에서는 필요하지 않습니다.  
  
5.  작업이 완료되면 **사용자 솔루션 갤러리** 링크를 선택하여 .wsp 파일을 봅니다.  
  
     나중에 솔루션 갤러리를 보려면 **사이트 설정** 탭에서 **사이트 작업**을 선택하고 **사이트 컬렉션 관리** 섹션에서 **최상위 사이트 설정으로 이동** 링크를 선택한 다음 **갤러리** 섹션에서 **솔루션** 링크를 선택합니다.  
  
6.  솔루션 갤러리에서 **ExampleSite** 링크를 선택합니다.  
  
7.  **파일 다운로드** 대화 상자에서 **저장** 버튼을 선택하여 파일을 로컬 시스템에, 기본적으로 다운로드 폴더에 파일을 저장합니다.  
  
## .wsp 파일 가져오기  
 이제 다시 사용하려는 항목\(사용자 지정 사이트 열인 테스트 열\)이 포함된 .wsp 파일이 있으므로 .wsp 파일을 가져와 액세스합니다.  
  
#### .wsp 파일을 가져오려면  
  
1.  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 의 메뉴 모음에서 **파일**, **새로 만들기**, **프로젝트** 를 선택하여 **새 프로젝트** 대화 상자를 표시합니다.  IDE가 Visual Basic 개발 설정을 사용하도록 설정된 경우, 메뉴 표시줄에서 **파일**, **새 프로젝트** 를 선택합니다.  
  
2.  **Visual C\#** 또는 **Visual Basic** 아래의 **SharePoint** 노드를 확장한 다음 **2010** 을 선택합니다.  
  
3.  **템플릿** 창에서 **SharePoint 2010 솔루션 패키지 가져오기** 템플릿을 선택하고, 프로젝트 이름을 WspImportProject1로 유지한 다음 **확인** 버튼을 선택합니다.  
  
     **SharePoint 사용자 지정 마법사**가 나타납니다.  
  
4.  **디버깅에 사용할 사이트 및 보안 수준 지정** 페이지에서 이전에 만든 두 번째 SharePoint 하위 사이트로 [!INCLUDE[TLA2#tla_url](../sharepoint/includes/tla2sharptla-url-md.md)] 을 입력합니다.  새 사용자 지정 필드 항목이 http:\/\/*system name*\/columntest2 을 해당 하위 사이트에 추가됩니다.  
  
5.  **이 SharePoint 솔루션의 신뢰 수준을 선택하십시오.** 섹션에서 선택 항목을 **샌드박스가 적용된 솔루션으로 배포**로 유지합니다.  
  
6.  **새 프로젝트 소스 지정** 페이지에서 이전에 .wsp 파일을 저장한 시스템 위치로 이동한 후 **다음** 버튼을 선택합니다.  
  
    > [!NOTE]  
    >  이페이지에서 **완료** 버튼을 선택할 경우, .wsp 파일에서 사용 가능한 모든 항목들이 불려옵니다.  
  
7.  **가져올 항목 선택** 상자에서 **테스트 열**을 제외하고 목록의 모든 확인 란을 선택 취소한 다음 **마침** 버튼을 선택합니다.  
  
     목록이 많은 항목을 포함하기 때문에, Ctrl \+ A 키를 눌러 모든 항목을 선택하고, 스페이스바 키를 눌러 모든 확인란을 선택 해제 한 다음, **테스트 열** 항목 옆의 확인란만 선택할 수 있습니다.  
  
     가져오기 작업이 완료되면 **필드**라는 폴더가 포함된 **WspImportProject1** 프로젝트가 새로 만들어집니다.  이 폴더에는 사용자 지정 사이트 열인 **테스트 열**과 해당 정의 파일 Elements.xml이 들어 있습니다.  
  
## 프로젝트 배포  
 마지막으로, 이전에 만든 두 번째 SharePoint 하위 사이트에 **WspImportProject1**을 배포하여 사용자 지정 사이트 열을 봅니다.  
  
#### 프로젝트를 배포하려면  
  
1.  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에서 F5 키를 눌러 .wsp 가져오기 프로젝트를 배포하고 실행합니다.  
  
2.  SharePoint 사이트에서 **사이트 작업** 메뉴를 연 후 **사이트 설정** 을 선택하여 사이트 설정 페이지를 표시 합니다.  
  
3.  **갤러리** 섹션에서 **사이트 열** 링크를 선택합니다.  
  
4.  **사용자 지정 열** 섹션까지 아래로 스크롤합니다.  
  
     첫 번째 SharePoint 사이트에서 가져온 사용자 지정 사이트 열이 목록에 표시됩니다.  
  
## 참고 항목  
 [기존 SharePoint 사이트에서 항목 가져오기](../sharepoint/importing-items-from-an-existing-sharepoint-site.md)   
 [Developing SharePoint Solutions](../sharepoint/developing-sharepoint-solutions.md)   
 [웹 파트 또는 응용 프로그램 페이지를 위해 재사용 가능한 컨트롤 만들기](../sharepoint/creating-reusable-controls-for-web-parts-or-application-pages.md)  
  
  