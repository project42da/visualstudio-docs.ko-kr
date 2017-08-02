---
title: "연습: SharePoint용 사이트 열, 콘텐츠 형식 및 목록 만들기"
ms.custom: ""
ms.date: "02/02/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VS.SharePointTools.ListDesigner.GeneralMessageHelp"
  - "Microsoft.VisualStudio.SharePoint.Designers.ListDesigner.ViewModels.ListViewModel.SortingAndGrouping"
  - "VS.SharePointTools.ListDesigner.SortingGrouping"
dev_langs: 
  - "VB"
  - "CSharp"
  - "VB"
  - "CSharp"
helpviewer_keywords: 
  - "Visual Studio에서 SharePoint 개발, 콘텐츠 형식"
  - "Visual Studio에서 SharePoint 개발, 필드"
  - "Visual Studio에서 SharePoint 개발, 목록 정의"
  - "Visual Studio에서 SharePoint 개발, 목록 인스턴스"
ms.assetid: caebacc2-616c-4373-8e21-edc7979338e7
caps.latest.revision: 54
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 53
---
# 연습: SharePoint용 사이트 열, 콘텐츠 형식 및 목록 만들기
  다음 절차는 사용자 지정 SharePoint 사이트 열을 만드는 방법을 보여준다\-또는 *필드*\- 또한 사이트 열을 이용한 콘텐츠 타입을 만드는 방법을 보여준다.  또한 새 콘텐츠 형식을 사용 하는 목록을 만드는 방법을 보여 줍니다.  
  
 이 연습에는 다음 작업이 포함됩니다.  
  
-   [사용자 지정 사이트 열 만들기](#BKMK_CreatingCustSiteCols).  
  
-   [사용자 지정 콘텐츠 형식 만들기](#BKMK_CreateCustContType).  
  
-   [목록 만들기](#BKMK_CreateList).  
  
-   [목록 만들기](#BKMK_CreateList).  
  
-   [응용 프로그램 테스트](#BKMK_TestApp).  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## 사전 요구 사항  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   지원되는 Windows 및 SharePoint 버전.  자세한 내용은 [SharePoint 솔루션 개발 요구 사항](../sharepoint/requirements-for-developing-sharepoint-solutions.md)을 참조하십시오.  
  
-   Visual Studio  
  
##  <a name="BKMK_CreatingCustSiteCols"></a> 사용자 지정 사이트 열 만들기  
 병원의 환자 관리에 대한 목록을 만드는 예제입니다.  먼저 SharePoint 프로젝트를 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 에 만들어야 하며 사이트 열을 다음과 같이 추가 합니다.  
  
#### 프로젝트를 만들려면  
  
1.  [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] **파일** 메뉴에서, **New**, **프로젝트**를 선택합니다.  
  
2.  **새 프로젝트** 대화 상자에서 **Visual C\#** 또는 **Visual Basic** 폴더, **SharePoint** 를 차례로 확장한 다음 **2010**을 클릭합니다.  
  
3.  **템플릿** 창에서 **SharePoint 2010 프로젝트**를 클릭하고 프로젝트 이름을 Clinic으로 변경한 다음 **확인** 을 클릭합니다.  
  
     SharePoint 2010 프로젝트 템플릿은 사이트 열 및 나중에 추가 된 다른 프로젝트 항목을 포함 하도록 하는 이 예제에 사용 되는 빈 프로젝트입니다.  
  
4.  **디버깅에 사용할 사이트 및 보안 수준 지정** 페이지에서 새 사용자 지정 필드 항목을 추가할 SharePoint 서버 사이트의 URL을 입력하거나 기본 위치\(`http://<`*SystemName*`>/)`를 사용합니다.  
  
5.  **이 SharePoint 솔루션의 신뢰 수준을 선택하십시오.** 섹션에서 기본값인 **샌드박스가 적용된 솔루션으로 배포**를 사용합니다.  
  
     샌드박스가 적용된 솔루션과 팜 솔루션에 대한 자세한 내용은 [샌드박스가 적용된 솔루션 고려 사항](../sharepoint/sandboxed-solution-considerations.md)을 참조하십시오.  
  
6.  **마침** 단추를 선택합니다.  이제 프로젝트는 **솔루션 탐색기**에 있어야 합니다.  
  
#### 사이트 열을 추가 하려면  
  
1.  새 사이트 열을 추가 합니다.  이를위해 **솔루션 탐색기**에서 **Clinic** 폴더의 바로 가기 메뉴를 열고 **추가**, **새 항목**을 선택합니다.  
  
2.  새 항목 **추가 대화 상자에서** 이름 필드를 선택하고 **제품을** 입력한 후에 **추가** 버튼을 선택하십시오.  
  
3.  사이트 열 Elements.xml 파일에서 **형식** 을 **텍스트**로 설정합니다, 그리고 **그룹** 을 Clinic 사이트 열로 설정 합니다.  완료 되면 사이트 열의 Elements.xml 파일은 다음 예제와 같아야 합니다.  
  
    ```  
    <Field  
         ID="{f9ba60d1-5631-41fb-b016-a38cf48eef63}"  
         Name="Clinic - Patient Name"  
         DisplayName="Patient Name"  
         Type="Text"  
         Required="FALSE"  
         Group="Clinic Site Columns">  
    </Field>  
    ```  
  
4.  동일한 절차를 사용하여, 프로젝트에 환자에 환자 ID \(유형 \= "정수"\) 및 병원 이름 \(유형 \= "텍스트"\) 을 추가합니다.  그룹 값을 클리닉 사이트 열로 설정 합니다.  
  
##  <a name="BKMK_CreateCustContType"></a> 사용자 지정 콘텐츠 형식 만들기  
 그런 다음, 이전 절차에서 만든 사이트 열을 포함하는 연락처 콘텐츠 형식을 기본으로 하는 콘텐츠 형식을 만듭니다.  기존 콘텐츠 형식에서의 콘텐츠 형식을 기반으로 하면, 기본 콘텐츠 형이 에 새 콘텐츠 형식에서의 사용을 위해 여러 사이트 열을 제공하기 때문에 시간이 절약될 수 있습니다.  
  
#### 사용자 지정 콘텐츠 형식을 만들려면  
  
1.  프로젝트에 콘텐츠 형식을 추가합니다.  이것을 하려면 **솔루션 탐색기**에서 프로젝트 노드를 선택합니다.  
  
2.  메뉴 모음에서 **프로젝트**, **새 항목 추가**를 선택합니다.  
  
3.  **Visual C\#** 또는 **Visual Basic** 아래의 **SharePoint** 노드를 확장한 다음 **2010** 노드를 선택합니다.  
  
4.  **템플릿** 창에서 **콘텐츠 형식** 템플릿을 선택하고, 이름을 환자 정보로 변경한 다음 **추가** 버튼을 선택합니다.  
  
     **SharePoint 사용자 지정 마법사** 가 열립니다.  
  
5.  **이 콘텐츠 형식에서 상속 해야 하는 기본 콘텐츠 형식** 목록에서, 새 콘텐츠 형식을 기본으로 하는 콘텐츠 형식으로 **연락처** 를 선택한 다음, **완료** 버튼을 선택합니다.  
  
     이렇게 하면, 미리 정의된 사이트 열과 함께 연락처 콘텐츠 형식에서 다른 잠재적으로 유용한 사이트 열로의 액세스를 부여합니다.  
  
6.  콘텐츠 형식 디자이너가 표시되고 난 후, **열** 탭에서 이전에 정의한 **환자 이름**, **환자 ID** 및 **의사 이름** 열을 추가합니다.  이러한 열을 추가 하려면, **표시 이름** 아래의 사이트 열에서 첫 번째 목록 상자를 선택한 다음, 목록에서 각 사이트 열을 한번에 선택합니다.  
  
    > [!TIP]  
    >  사이트 열을 빠르게 선택 하려면, 열 이름 중 처음 몇 글자를 입력하여 목록을 필터링 합니다.  
  
7.  세 개의 사용자 지정 사이트 열 뿐만 아니라, 사이트 열 목록에서 **주석** 사이트 열을 추가합니다.  
  
8.  필수 필드로 만들기 위하여 **환자 이름** 및 **환자 ID** 사이트 열의 **필수** 확인란을 선택합니다.  
  
9. **콘텐츠 형식** 탭에서 콘텐츠 형식 이름이 **환자 정보** 인지 확인하고, 환자 정보 카드에 대한 설명을 변경 합니다.  
  
10. **그룹 이름** 을 클리닉 콘텐츠 형식으로 변경하고, 기타 설정은 기본값으로 그대로 둡니다.  
  
11. 메뉴 표시줄에서 **파일**, **모두 저장** 을 선택한 다음, 콘텐츠 형식 디자이너를 닫습니다.  
  
##  <a name="BKMK_CreateList"></a> 목록 만들기  
 이제 새 콘텐츠 형식 및 사이트 열을 사용하는 목록을 만듭니다.  
  
#### 목록을 만들려면  
  
1.  프로젝트에 목록을 추가합니다.  이것을 하려면 **솔루션 탐색기**에서 프로젝트 노드를 선택합니다.  
  
2.  메뉴 모음에서 **프로젝트**, **새 항목 추가**를 선택합니다.  
  
3.  **Visual C\#** 또는 **Visual Basic** 아래의 **SharePoint** 노드를 확장한 다음 **2010** 노드를 선택합니다.  
  
4.  **템플릿** 창에서 **리스트** 템플릿을 선택하고, 이름을 환자로 변경한 다음 **추가** 버튼을 선택합니다.  
  
5.  **목록의 사용자 지정을 하는 기준** 설정을 **기본 \(비어 있음\)** 으로 냅두고, **완료** 버튼을 선택합니다.  
  
6.  목록 디자이너에서 **콘텐츠 형식** 버튼을 선택하여 **콘텐츠 형식 설정** 대화 상자를 표시합니다.  
  
7.  새 행을 선택하고, 콘텐츠 형식 목록에서 **환자 정보** 콘텐츠 형식을 선택한 다음, **확인** 버튼을 선택합니다.  
  
     이것을 하면 모든 사이트 열이 **환자 정보** 콘텐츠 형식에서 목록에 추가됩니다.  
  
8.  다음을 제외하고 목록에서 사이트 열을 모두 삭제 합니다.  
  
    -   환자 ID  
  
    -   환자 이름  
  
    -   집 전화  
  
    -   전자 메일  
  
    -   의사 이름  
  
    -   설명  
  
9. **열 표시 이름** 에서 빈 행을 선택하고, 사용자 지정 목록 열을 추가한 다음, 이것을 병원 으로 명명합니다.  해당 데이터 형식을 **단일 텍스트 줄** 로 지정합니다.  
  
     사용자 지정 목록 열은 이 목록에만 적용 됩니다.  목록에 사용자 지정 목록 열을 추가 할 때, 목록에 추가된 모든 열을 포함하는 새 목록 콘텐츠 형식이 생성되고 기본 리스트로 설정됩니다.  
  
    > [!TIP]  
    >  사이트 열 목록에서 열을 선택 하는 경우, 기존 사이트 열이 사용 됩니다.  그러나, 목록의 모든 열을 선택 하지 않고 열 이름 값을 입력 하면, 목록에 이미 같은 이름을 가진 열이 있다 하더라도 사용자 지정 목록 열이 만들어 집니다.  
  
     필요에 따라, 사용자 지정 목록 열의 데이터 형식을 **단일 텍스트 줄** 로 설정 하는 대신, 이 열에 대한 데이터 형식을 조회로 설정할 수 있고, 해당 값은 테이블 또는 다른 목록으로 부터 조회될 것입니다.  조회 열에 대한 자세한 내용은 [2010 SharePoint에서의 목록 관계](http://go.microsoft.com/fwlink/?LinkId=224994) 및 [조회 및 목록 관계](http://go.microsoft.com/fwlink/?LinkID=224995) 를 참조하십시오.  
  
10. **환자 ID** 와 **환자 이름** 상자 옆에 있는 **필수** 확인란을 선택합니다.  
  
11. **보기** 탭에서 보기를 만들 수 있는 빈 행을 선택 합니다.  환자 정보를 입력 합니다.  
  
     **보기** 탭에서, SharePoint 목록에 표시할 열을 지정할 수 있습니다.  
  
12. 새 **환자 정보** 행을 선택한 다음 **기본으로 설정** 버튼을 선택합니다.  
  
     새 보기는 이제 목록의 기본 보기가 됩니다.  
  
13. 다음과 같은 순서로 다음 열을 **선택된 열** 에 추가합니다:  
  
    -   환자 ID  
  
    -   환자 이름  
  
    -   집 전화  
  
    -   전자 메일  
  
    -   의사 이름  
  
    -   병원  
  
    -   설명  
  
14. **속성** 목록에서, **정렬 및 그룹화** 속성을 선택한 다음, 줄임표 버튼 ![가변 매개 변수 아이콘](~/sharepoint/media/ellipsisicon.gif "가변 매개 변수 아이콘") 을 선택하여 **정렬 및 그룹화** 대화 상자를 표시합니다.  
  
15. **열 이름** 목록에서 **환자 이름** 을 선택하고, **정렬** 열이 **오름차순** 으로 설정되어 있는지 확인한 다음, **확인** 버튼을 선택합니다.  
  
##  <a name="BKMK_TestApp"></a> 응용 프로그램 테스트  
 이제 사용자 지정 사이트 열, 콘텐츠 형식 및 목록이 준비가 되었으므로, 이것들을 SharePoint에 배포하고 테스트 하기 위해 응용 프로그램을 실행합니다.  
  
#### 응용 프로그램을 테스트하려면  
  
1.  메뉴 모음에서 **파일**, **모두 저장**을 차례로 선택합니다.  
  
2.  F5 키를 선택하여 응용 프로그램을 실행합니다.  
  
     응용 프로그램이 컴파일되고 기능이 SharePoint에 배포 및 활성화 합니다.  
  
3.  빠른 탐색 모음에서 **환자** 링크를 선택하여 **환자** 목록을 표시합니다.  
  
     목록에서 열 이름들은 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 에서 **보기** 탭에 입력한 것들과 일치해야 합니다.  
  
4.  **새 항목 추가** 링크를 선택하여 환자 정보 카드를 만듭니다.  
  
5.  필드에 정보를 입력한 다음 **저장** 버튼을 선택합니다.  
  
     목록에 새 기록이 표시됩니다.  
  
## 참고 항목  
 [SharePoint용 사이트 열, 콘텐츠 형식 및 목록 만들기](../sharepoint/creating-site-columns-content-types-and-lists-for-sharepoint.md)   
 [Developing SharePoint Solutions](../sharepoint/developing-sharepoint-solutions.md)   
 [방법: 사용자 정의 필드 형식 만들기](http://go.microsoft.com/fwlink/?LinkId=192079)   
 [콘텐츠 형식](http://go.microsoft.com/fwlink/?LinkId=192080)   
 [Columns](http://go.microsoft.com/fwlink/?LinkId=192081)  
  
  