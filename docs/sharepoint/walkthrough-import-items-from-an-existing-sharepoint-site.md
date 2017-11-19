---
title: "연습: 기존 SharePoint 사이트에서 항목을 가져오는 | Microsoft Docs"
ms.custom: 
ms.date: 02/02/2017
ms.reviewer: 
ms.suite: 
ms.technology: office-development
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, importing items
- importing items [SharePoint development in Visual Studio]
ms.assetid: faac3309-88d7-4fb2-8392-feda07fc00e5
caps.latest.revision: "21"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 602615426a8aeca118f6faba65e21778136b0ce6
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="walkthrough-import-items-from-an-existing-sharepoint-site"></a>연습: 기존 SharePoint 사이트에서 항목 가져오기
  이 연습에서는 기존 SharePoint 사이트에서 항목을 가져오는 방법을 보여 줍니다.는 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] SharePoint 프로젝트.  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   사용자 지정 사이트 열을 추가 하 여 SharePoint 사이트를 사용자 지정 (라고도 *필드*합니다.  
  
-   SharePoint 사이트를.wsp 파일로 내보내는 중입니다.  
  
-   .Wsp 파일을 가져오는 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] .wsp 가져오기 프로젝트를 사용 하 여 SharePoint 합니다.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>필수 구성 요소  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   지원 되는 버전 [!INCLUDE[TLA#tla_win](../sharepoint/includes/tlasharptla-win-md.md)] 및 SharePoint 합니다. 자세한 내용은 참조 [SharePoint 솔루션 개발 요구 사항](../sharepoint/requirements-for-developing-sharepoint-solutions.md)합니다.  
  
-   Visual Studio.  
  
## <a name="customizing-a-sharepoint-site"></a>SharePoint 사이트를 사용자 지정  
 이 예에서는 만들고 새 사이트 열을 추가 하 여 및 나중에 사용 하기 위해 다른 하위 사이트를 만들어 SharePoint 하위 사이트를 사용자 지정 합니다. 이상에서는 첫 번째 하위 사이트를.wsp 파일로 내보낼 쿼리하고 사용자 지정 사이트 열.wsp 가져오기 프로젝트를 사용 하 여 두 번째 하위 가져올 합니다.  
  
#### <a name="to-create-and-customize-a-sharepoint-site"></a>만들기 및 SharePoint 사이트를 사용자 지정 하려면  
  
1.  Http:// 등의 웹 브라우저를 사용 하 여 SharePoint 사이트를 열고*시스템 이름*/SitePages/Home.aspx 합니다.  
  
2.  기본 SharePoint 사이트에서 하위 사이트를 열어 만들기는 **사이트 작업** 메뉴를 선택한 다음 **새 사이트**합니다.  
  
3.  사이트의 **만들기** 대화 상자에서 선택 하는 **빈 사이트** 유형입니다.  
  
4.  에 **제목** 상자에 입력 **사이트 열 테스트 1**;에 **URL 이름** 상자에 입력 **columntest1**; 다른 설정을 기본값으로 둡니다 값이 있습니다. 선택한 후는 **만들기** 단추입니다.  
  
5.  사이트를 만든 후 주 사이트로 브라우저에서 탐색 http://*시스템 이름*/SitePages/Home.aspx 합니다.  
  
6.  다시 열어 기본 SharePoint 사이트에서 빈 하위 사이트를 만들는 **사이트 작업** 메뉴 선택 **새 사이트**를 선택한 다음는 **빈 사이트** 유형입니다.  
  
7.  에 **제목** 상자에 입력 **사이트 열 Test 2**;에 **URL 이름** 상자에 입력 **columntest2**; 다른 설정을 기본값으로 둡니다 값이 있습니다. 선택한 후는 **만들기** 단추입니다.  
  
8.  첫 번째 하위 사이트를 다시 탐색 http://*SystemName*/columntest1/default.aspx 합니다.  
  
9. 에 **사이트 작업** 메뉴 선택 **사이트 설정** 사이트 설정 페이지를 표시 합니다.  
  
10. 에 **갤러리** 섹션에서 선택 된 **사이트 열** 링크 합니다.  
  
11. 맨 위에 있는 **사이트 열 갤러리** 페이지에서 선택 된 **만들기** 단추입니다.  
  
12. 에 **열 이름** 상자에 입력 **테스트 열**다른 기본값을 유지 하 고 선택 합니다는 **확인** 단추입니다.  
  
13. **테스트 열** 열 머리글에 사용자 지정 열에 따라 사이트 열 갤러리에 있습니다.  
  
## <a name="exporting-the-sharepoint-site"></a>SharePoint 사이트를 내보내기  
 다음으로 SharePoint 항목 및로 가져올 복사할 요소를 포함 하는 SharePoint 설치 프로그램 (.wsp) 파일을 가져올 사용자 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] SharePoint 프로젝트. .Wsp 파일이 아직 없는 경우 다음 만들어야 기존 SharePoint 사이트에서 하나입니다. 이 예제에 대 한 기본 SharePoint 사이트를.wsp 파일로 내보냅니다.  
  
> [!IMPORTANT]  
>  다음 절차를 수행 하는 런타임 오류가 발생 하는 경우 SharePoint 사이트에 액세스할 수 있는 시스템에서 절차를 수행 해야 합니다.  
  
#### <a name="to-export-an-existing-sharepoint-site"></a>기존 SharePoint 사이트를 내보내려면  
  
1.  SharePoint 사이트에서 선택 **사이트 설정** 에 **사이트 작업** 탭 사이트 설정 페이지를 표시 합니다.  
  
2.  에 **사이트 작업** 섹션 사이트 설정 페이지의 선택은 **템플릿으로 저장 사이트** 링크 합니다.  
  
3.  에 **파일 이름** 상자에 입력 **ExampleSite**, 및는 **템플릿 이름** 상자에 입력 **예제 사이트**합니다.  
  
4.  이 예제에서는 상태로 둡니다는 **콘텐츠 포함** 확인란을 선택 취소 합니다.  
  
     이 확인란을 선택 하는 경우 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] .wsp 파일에 목록 및 문서 라이브러리와 해당 내용을 저장 합니다. 이 제한은 유용 하지만 일부 경우에,이 예에서는 필요 하지 않습니다.  
  
5.  선택 작업이 성공적으로 완료 되는 **솔루션 갤러리** .wsp 파일을 보려면 링크를 합니다.  
  
     이후, 열린 솔루션 갤러리 페이지를 보려면는 **사이트 작업** 메뉴 선택 **사이트 설정**, 선택는 **최상위 사이트 설정으로 이동** 연결에  **사이트 컬렉션 관리** 섹션을 선택한 다음 선택에서 **솔루션** 연결에 **갤러리** 섹션.  
  
6.  솔루션 갤러리에서 선택 된 **ExampleSite** 링크 합니다.  
  
7.  에 **파일 다운로드** 대화 상자에서 선택 하는 **저장** Downloads 폴더에 기본적으로 로컬 시스템에서 파일을 저장 하려면 단추입니다.  
  
## <a name="importing-the-wsp-file"></a>.Wsp 파일 가져오기  
 이제가 있는 경우 (사용자 지정 사이트 열 테스트 열)를 다시 사용 하려고 하는 항목을 포함 하는.wsp 파일에 액세스할 수.wsp 파일을 가져옵니다.  
  
#### <a name="to-import-a-wsp-file"></a>.Wsp 파일을 가져오려면  
  
1.  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], 메뉴 모음에서 **파일**, **새로**, **프로젝트** 표시 하는 **새 프로젝트** 대화 상자. IDE에는 메뉴 모음에서 Visual Basic 개발 설정을 사용 하도록 설정 된, 선택 **파일**, **새 프로젝트**합니다.  
  
2.  확장 하 고는 **SharePoint** 노드 아래의 **Visual C#** 또는 **Visual Basic**를 선택한 후는 **2010** 노드.  
  
3.  선택 된 **SharePoint 2010 솔루션 패키지 가져오기** 에서 서식 파일의 **템플릿** 창 WspImportProject1,으로 프로젝트의 이름을 선택한 후는 **확인** 단추입니다.  
  
     **SharePoint 사용자 지정 마법사** 나타납니다.  
  
4.  에 **디버깅에 대 한 사이트 및 보안 수준을 지정** 페이지에서 입력은 [!INCLUDE[TLA2#tla_url](../sharepoint/includes/tla2sharptla-url-md.md)] 앞에서 만든 두 번째 SharePoint 하위 사이트에 대 한 합니다. 추가한 새 사용자 지정 필드 항목, http://*시스템 이름*/columntest2 해당 하위 사이트에 있습니다.  
  
5.  에 **이 SharePoint 솔루션에 대 한 신뢰 수준을?** 섹션에서으로 남겨 둡니다 **샌드박스 솔루션으로 배포**합니다.  
  
6.  에 **새 프로젝트 소스 지정** 페이지, 이전에.wsp 파일을 저장 하는 시스템에 위치를 찾아 선택한 후는 **다음** 단추입니다.  
  
    > [!NOTE]  
    >  선택 하는 경우는 **마침** 단추가 페이지에서는.wsp 파일에서 사용 가능한 모든 항목을 가져옵니다.  
  
7.  에 **가져올 항목 선택** 상자에서 모든을 제외 하 고 목록에 있는 확인란의 선택을 취소 **테스트 열**, 선택한 후는 **마침** 단추입니다.  
  
     목록에서 모든 항목을 선택 하 고 Ctrl + A 키 모든 확인란의 선택을 취소 스페이스바 키를 선택 하 고 다음 옆에 확인란만을 선택 목록 항목 수 있어서 선택할 수 있습니다는 **테스트 열** 항목입니다.  
  
     가져오기 작업이 완료 되 면 라는 새 프로젝트 **WspImportProject1** 만들어집니다 라는 폴더를 포함 하는 **필드**합니다. 이 폴더에는 사용자 지정 사이트 열 **테스트 열** 및 Elements.xml 정의 파일입니다.  
  
## <a name="deploying-the-project"></a>프로젝트를 배포 하면  
 마지막으로 배포 **WspImportProject1** 두 번째 SharePoint에 사용자 지정 사이트 열을 보려면 이전 만든 하위 사이트입니다.  
  
#### <a name="to-deploy-the-project"></a>프로젝트를 배포 하려면  
  
1.  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)], 배포 및.wsp 가져오기 프로젝트를 실행 하려면 F5 키를 선택 합니다.  
  
2.  SharePoint 사이트에서 엽니다는 **사이트 작업** 메뉴를 선택한 후 **사이트 설정** 사이트 설정 페이지를 표시 합니다.  
  
3.  에 **갤러리** 섹션에서 선택 된 **사이트 열** 링크 합니다.  
  
4.  으로 아래로 스크롤하여는 **사용자 지정 열** 섹션.  
  
     첫 번째 SharePoint 사이트에서 가져온 사용자 지정 사이트 열 목록에 나타나는지 확인 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [기존 SharePoint 사이트에서 항목 가져오기](../sharepoint/importing-items-from-an-existing-sharepoint-site.md)   
 [SharePoint 솔루션 개발](../sharepoint/developing-sharepoint-solutions.md)   
 [웹 파트 또는 응용 프로그램 페이지를 위해 재사용 가능한 컨트롤 만들기](../sharepoint/creating-reusable-controls-for-web-parts-or-application-pages.md)  
  
  