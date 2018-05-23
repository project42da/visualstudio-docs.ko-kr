---
title: '연습: 사이트 열, 콘텐츠 형식 및 SharePoint에 대 한 목록 만들기 | Microsoft Docs'
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- VS.SharePointTools.ListDesigner.GeneralMessageHelp
- Microsoft.VisualStudio.SharePoint.Designers.ListDesigner.ViewModels.ListViewModel.SortingAndGrouping
- VS.SharePointTools.ListDesigner.SortingGrouping
dev_langs:
- VB
- CSharp
- VB
- CSharp
helpviewer_keywords:
- SharePoint development in Visual Studio, list definitions
- SharePoint development in Visual Studio, list instances
- SharePoint development in Visual Studio, fields
- SharePoint development in Visual Studio, content types
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 0dfcf3166e3fe4aa5ce17f51d696187cc060639b
ms.sourcegitcommit: 1466ac0f49ebf7448ea4507ae3f79acb25d51d3e
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/22/2018
---
# <a name="walkthrough-create-a-site-column-content-type-and-list-for-sharepoint"></a>연습: SharePoint용 사이트 열, 콘텐츠 형식 및 목록 만들기
  다음 절차에는 사용자 지정 SharePoint 사이트 열을 만드는 방법을 보여 줍니다-또는 *필드*-사이트 열을 사용 하는 콘텐츠 형식 뿐만 아니라 합니다. 또한 새 콘텐츠 형식을 사용 하는 목록을 만드는 방법을 보여 줍니다.  
  
 이 연습에는 다음 작업이 포함됩니다.  
  
-   [사용자 지정 사이트 열을 만드는](#BKMK_CreatingCustSiteCols)합니다.  
  
-   [사용자 지정 콘텐츠 형식을 만드는](#BKMK_CreateCustContType)합니다.  
  
-   [목록 만들기](#BKMK_CreateList)합니다.  
  
-   [목록 만들기](#BKMK_CreateList)합니다.  
  
-   [응용 프로그램 테스트](#BKMK_TestApp)합니다.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>전제 조건  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   Windows 및 SharePoint 버전의 지원. 자세한 내용은 참조 [SharePoint 솔루션 개발 요구 사항](../sharepoint/requirements-for-developing-sharepoint-solutions.md)합니다.  
  
-   Visual Studio.  
  
##  <a name="BKMK_CreatingCustSiteCols"></a> 사용자 지정 사이트 열 만들기  
 이 예제에는 환자 병원에 관리에 대 한 목록을 만듭니다. 먼저 SharePoint 프로젝트에 만들어야 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] 사이트 열, 다음과 같이 추가 하 고 있습니다.  
  
#### <a name="to-create-the-project"></a>프로젝트를 만들려면  
  
1.  에 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)] **파일** 메뉴 선택 **새로**, **프로젝트**합니다.  
  
2.  에 **새 프로젝트** 대화 상자에서 아래에서 **Visual C#** 또는 **Visual Basic**를 확장 하 고는 **SharePoint** 노드를 를선택합니다**2010**합니다.  
  
3.  에 **템플릿** 창에서 선택 **SharePoint 2010 프로젝트**, 프로젝트의 이름을 변경 **Clinic**를 선택한 후는 **확인** 단추입니다.  
  
     SharePoint 2010 프로젝트 템플릿은 사이트 열과 나중에 추가 된 기타 프로젝트 항목을 포함 하도록이 예제에 사용 되는 빈 프로젝트입니다.  
  
4.  에 **디버깅에 대 한 사이트 및 보안 수준을 지정** 페이지, 새 사용자 지정 필드 항목을 추가 하려면 로컬 SharePoint 사이트에 대 한 URL을 입력 하거나 기본 위치를 사용 하 여 (`http://<`*SystemName* `>/)`.  
  
5.  에 **이 SharePoint 솔루션에 대 한 신뢰 수준을?** 섹션에서 기본값을 사용 하 여 **샌드박스 솔루션으로 배포**합니다.  
  
     샌드박스가 적용 된에 대 한 자세한 내용은 팜 솔루션, 참조 및 [샌드박스 솔루션 고려 사항](../sharepoint/sandboxed-solution-considerations.md)합니다.  
  
6.  선택 된 **마침** 단추입니다. 이제 프로젝트에 표시 해야 **솔루션 탐색기**합니다.  
  
#### <a name="to-add-site-columns"></a>사이트 열을 추가 하려면  
  
1.  새 사이트 열을 추가 합니다. 이 수행 하려면 **솔루션 탐색기**, 바로 가기 메뉴를 열고 **Clinic**를 선택한 후 **추가**, **새 항목**합니다.  
  
2.  에 **새 항목 추가** 대화 상자에서 선택 **사이트 열**, 하도록 이름을 변경 **환자 이름**, 선택한 후는 **추가** 단추입니다.  
  
3.  사이트 열의 Elements.xml 파일에서 그대로 둡니다는 **형식** 로 설정 **텍스트**, 변경 하 고는 **그룹** 설정을 **Clinic 사이트 열**합니다. 완료 되 면 사이트 열의 Elements.xml 파일은 다음 예제와 같아야 합니다.  
  
    ```xml  
    <Field  
         ID="{f9ba60d1-5631-41fb-b016-a38cf48eef63}"  
         Name="Clinic - Patient Name"  
         DisplayName="Patient Name"  
         Type="Text"  
         Required="FALSE"  
         Group="Clinic Site Columns">  
    </Field>  
    ```  
  
4.  동일한 절차를 사용 하 여 두 개 이상의 사이트 열 프로젝트에 추가: **환자 ID** (유형 = "정수") 및 **의사 이름이** (유형 = "Text"). 그룹 값이 설정 **Clinic 사이트 열**합니다.  
  
##  <a name="BKMK_CreateCustContType"></a> 사용자 지정 콘텐츠 형식 만들기  
 다음으로, 콘텐츠 형식 만들기-연락처 콘텐츠 형식에 따라-이전 절차에서 만든 사이트 열을 포함 하는 합니다. 기존 콘텐츠 형식, 콘텐츠 형식을 기반으로 기본 콘텐츠 형식에서 새 콘텐츠 형식 사용 하기 위해 여러 사이트 열을 제공 하기 때문에 시간을 절약할 수 있습니다.  
  
#### <a name="to-create-a-custom-content-type"></a>사용자 지정 콘텐츠 형식을 만들려면  
  
1.  콘텐츠 형식을 프로젝트에 추가 합니다. 이 수행 하려면 **솔루션 탐색기**, 프로젝트 노드를 선택 합니다.  
  
2.  메뉴 모음에서 **프로젝트**, **새 항목 추가**합니다.  
  
3.  아래의 **Visual C#** 또는 **Visual Basic**를 확장 하 고는 **SharePoint** 노드를 선택한 후는 **2010** 노드.  
  
4.  에 **템플릿** 창 선택는 **콘텐츠 형식** 서식 파일을 하도록 이름을 변경 **환자 정보**, 선택한 후는 **추가** 단추입니다.  
  
     **SharePoint 사용자 지정 마법사** 열립니다.  
  
5.  에 **이 콘텐츠 형식에서 상속 해야 하는 기본 콘텐츠 형식도** 목록에서 선택 **연락처** 새 콘텐츠 형식의 기반이 고 눌러 할 콘텐츠 형식으로는 **마침**단추입니다.  
  
     이 작업 이전에 정의 된 사이트 열 외에 연락처 콘텐츠 형식에서 다른 유용할 수 있는 사이트 열에 액세스할을 수 있습니다.  
  
6.  콘텐츠 형식 다음 디자이너에 표시 됩니다는 **열** 탭에서 이전에 정의한 열을 세 개의 사이트 추가: **환자 이름**, **환자 ID**, 및 **의사 이름이**합니다. 이러한 열을 추가 하려면 첫 번째 목록 상자에서 사이트 열 목록에서 선택 **표시 이름**, 한 번에 하나의 목록에 각 사이트 열을 선택 합니다.  
  
    > [!TIP]  
    >  사이트 열을 보다 신속 하 게 선택 하려면 열 이름의 처음 몇 문자를 입력 하 여 목록을 필터링 합니다.  
  
7.  세 개의 사용자 지정 사이트 열 외에도 추가 **주석** 사이트 열 목록에서 사이트 열입니다.  
  
8.  선택는 **필요한** 에 대 한 확인란은 **환자 이름** 및 **환자 ID** 하면 사이트 열 필수 필드입니다.  
  
9. 에 **콘텐츠 형식** 탭, 콘텐츠 형식 이름 인지 확인 **환자 정보**, 한 다음 설명을 변경 **환자 정보 카드**합니다.  
  
10. 변경 **그룹 이름** 를 **Clinic 콘텐츠 형식을**, 및 기타 설정을 기본값으로 그대로 둡니다.  
  
11. 메뉴 모음에서 **파일**, **모두 저장**, 콘텐츠 형식 디자이너를 닫습니다.  
  
##  <a name="BKMK_CreateList"></a> 목록 만들기  
 이제 새 콘텐츠 유형 및 사이트 열을 사용 하는 목록을 만듭니다.  
  
#### <a name="to-create-a-list"></a>목록을 만들려면  
  
1.  프로젝트에 목록을 추가 합니다. 이 수행 하려면 **솔루션 탐색기**, 프로젝트 노드를 선택 합니다.  
  
2.  메뉴 모음에서 **프로젝트**, **새 항목 추가**합니다.  
  
3.  아래의 **Visual C#** 또는 **Visual Basic**를 확장 하 고는 **SharePoint** 노드를 선택한 후는 **2010** 노드.  
  
4.  에 **템플릿** 창 선택는 **목록** 서식 파일을 하도록 이름을 변경 **환자**, 선택한 후는 **추가** 단추입니다.  
  
5.  둡니다는 **목록을 기반으로 사용자 지정** 로 설정 **기본값 (비어 있음)**, 선택한 후는 **마침** 단추입니다.  
  
6.  목록 디자이너에서 선택 된 **콘텐츠 형식을** 표시 하려면 단추는 **콘텐츠 형식 설정** 대화 상자.  
  
7.  새 행을 선택 합니다.를 선택는 **환자 정보** 콘텐츠 콘텐츠 형식의 형식 목록에서 선택한 후는 **확인** 단추입니다.  
  
     사이트 열에서의 모든 추가 이렇게는 **환자 정보** 콘텐츠 목록에는 형식입니다.  
  
8.  다음을 제외한 목록에서 사이트 열을 모두 삭제 합니다.  
  
    -   환자 ID  
  
    -   환자 이름  
  
    -   집 전화  
  
    -   전자 메일  
  
    -   Doctor 이름  
  
    -   설명  
  
9. 아래 **열 표시 이름**, 빈 행을 선택, 사용자 지정 목록 열을 추가 하 고 이름을 **병원**합니다. 해당 데이터 형식으로 두고 **한 줄 텍스트**합니다.  
  
     사용자 지정 목록 열이이 목록에만 적용 됩니다. 사용자 지정 목록 열 목록에 추가 하면 목록에 추가 된 모든 열을 포함 하 여 새 목록 콘텐츠 형식은 만들고 기본 목록으로 설정 합니다.  
  
    > [!TIP]  
    >  사이트 열 목록에서 열을 선택 하는 경우 기존 사이트 열이 사용 됩니다. 그러나 모든 열 목록에서 선택 하지 않고 열 이름 값을 입력 하는 경우 사용자 지정 목록 열 만들어지면 같은 이름의 열이 목록에 이미 있는 경우에 합니다.  
  
     사용자 지정 목록 열에 대 한 데이터 형식을 설정 하는 대신 필요에 따라 **한 줄 텍스트**, 조회, 대신이 열에 대 한 데이터 형식을 설정할 수 있습니다 및 테이블 또는 다른 목록에서 해당 값을 검색할 수는 있습니다. 조회 열에 대 한 정보를 참조 하십시오. [SharePoint 2010에서 목록 관계](http://go.microsoft.com/fwlink/?LinkId=224994) 및 [조회 및 목록 관계](http://go.microsoft.com/fwlink/?LinkID=224995)합니다.  
  
10. 옆에 **환자 ID** 및 **환자 이름** 선택 상자에서 **필요한** 확인란 합니다.  
  
11. 에 **뷰** 탭 보기를 만드는 빈 행을 선택 합니다. 입력 **환자 세부 정보**합니다.  
  
     에 **뷰** 탭, SharePoint 목록에 표시 하려는 열을 지정할 수 있습니다.  
  
12. 새 선택 **환자 세부 정보** 행을 선택한 후는 **기본값으로 설정** 단추입니다.  
  
     새 보기가 목록에 대 한 기본 보기입니다.  
  
13. 다음 열을 추가 **선택한 열** 다음과 같은 순서로 목록:  
  
    -   환자 ID  
  
    -   환자 이름  
  
    -   집 전화  
  
    -   전자 메일  
  
    -   Doctor 이름  
  
    -   병원  
  
    -   설명  
  
14. 에 **속성** 목록에서 선택는 **정렬 및 그룹화** 속성을 다음 줄임표 단추를 선택 하 고 ![줄임표 아이콘](../sharepoint/media/ellipsisicon.gif "줄임표 아이콘")표시 하는 **정렬 및 그룹화** 대화 상자.  
  
15. 에 **열 이름** 목록에서 선택 **환자 이름**, 있는지 확인은 **정렬** 열으로 설정 된 **오름차순**는 를선택합니다 **정상** 단추입니다.  
  
##  <a name="BKMK_TestApp"></a> 응용 프로그램 테스트  
 사용자 지정 사이트 열, 콘텐츠 형식 및 목록 준비 되 면 했으므로를 SharePoint에 배포 하 고 테스트를 위해 응용 프로그램을 실행 합니다.  
  
#### <a name="to-test-the-application"></a>응용 프로그램을 테스트하려면  
  
1.  메뉴 모음에서 **파일**, **모두 저장**을 차례로 선택합니다.  
  
2.  F5 키를 선택하여 응용 프로그램을 실행합니다.  
  
     응용 프로그램이 컴파일되고 해당 기능을 SharePoint 배포 되 고 활성화 되는 다음 합니다.  
  
3.  빠른 탐색 모음에서 선택 된 **환자** 표시 하려면 링크는 **환자** 목록.  
  
     목록에서 열 이름에 입력 한 것과 일치 해야는 **뷰** 탭에서 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]합니다.  
  
4.  선택 된 **새 항목 추가** 환자 정보 카드를 만들려면 링크 합니다.  
  
5.  필드에 정보를 입력 한 다음 선택에서 **저장** 단추입니다.  
  
     새 레코드의 목록에 나타납니다.  
  
## <a name="see-also"></a>참고 항목  
 [SharePoint 용 사이트 열, 콘텐츠 형식 및 목록 만들기](../sharepoint/creating-site-columns-content-types-and-lists-for-sharepoint.md)   
 [SharePoint 솔루션 개발](../sharepoint/developing-sharepoint-solutions.md)   
 [방법: 사용자 지정 필드 형식 만들기](http://go.microsoft.com/fwlink/?LinkId=192079)   
 [콘텐츠 형식](http://go.microsoft.com/fwlink/?LinkId=192080)   
 [열](http://go.microsoft.com/fwlink/?LinkId=192081)  
  
  