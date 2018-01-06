---
title: "연습: 비즈니스 데이터를 사용 하 여 SharePoint에 외부 목록 만들기 | Microsoft Docs"
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
- Business Data Connectivity service [SharePoint development in Visual Studio], business data in a Web Part
- BDC [SharePoint development in Visual Studio], external list
- Business Data Connectivity service [SharePoint development in Visual Studio], business data in a SharePoint list
- BDC [SharePoint development in Visual Studio], business data in a SharePoint list
- BDC [SharePoint development in Visual Studio], business data in a Web Part
- BDC [SharePoint development in Visual Studio], entity backed list
- Business Data Connectivity service [SharePoint development in Visual Studio], entity backed list
- Business Data Connectivity service [SharePoint development in Visual Studio], external list
ms.assetid: 046cf234-705a-4a6f-91f8-c5c569ae0dd0
caps.latest.revision: "38"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 8ecc80a3c26b97b9754f998bd0903471d00cd1d7
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-creating-an-external-list-in-sharepoint-by-using-business-data"></a>연습: 비즈니스 데이터를 사용하여 SharePoint에 외부 목록 만들기
  BDC 비즈니스 데이터 연결 () 서비스는 SharePoint을 백 엔드 서버 응용 프로그램, 웹 서비스 및 데이터베이스의 비즈니스 데이터를 표시할 수 있습니다.  
  
 이 연습에서는 샘플 데이터베이스의 연락처에 대 한 정보를 반환 하는 BDC 서비스에 대 한 모델을 만드는 방법을 보여 줍니다. 이 모델을 사용 하 여 SharePoint에는 외부 목록을 생성 합니다 하십시오.  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   프로젝트를 만듭니다.  
  
-   모델에 엔터티를 추가 합니다.  
  
-   Finder 메서드를 추가 합니다.  
  
-   특정 finder 메서드를 추가 합니다.  
  
-   프로젝트를 테스트 합니다.  
  
## <a name="prerequisites"></a>필수 구성 요소  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   Windows 및 SharePoint 버전의 지원. 자세한 내용은 참조 [SharePoint 솔루션 개발 요구 사항](../sharepoint/requirements-for-developing-sharepoint-solutions.md)합니다.  
  
-   [!INCLUDE[vsPro](../sharepoint/includes/vspro-md.md)], [!INCLUDE[vsUltLong](../sharepoint/includes/vsultlong-md.md)] 또는 [!INCLUDE[vsPreLong](../sharepoint/includes/vsprelong-md.md)].  
  
-   AdventureWorks 예제 데이터베이스에 액세스 합니다. AdventureWorks 데이터베이스를 설치 하는 방법에 대 한 자세한 내용은 참조 [SQL Server 예제 데이터베이스](http://go.microsoft.com/fwlink/?LinkID=117483)합니다.  
  
## <a name="creating-a-project-that-contains-a-bdc-model"></a>BDC 모델이 포함된 프로젝트 만들기  
  
#### <a name="to-create-a-project-that-contains-a-bdc-model"></a>BDC 모델이 포함된 프로젝트를 만들려면  
  
1.  Visual Studio의 메뉴 모음에서 **파일**, **새로**, **프로젝트**합니다.  
  
     **새 프로젝트** 대화 상자가 열립니다.  
  
2.  아래에서 **Visual C#** 또는 **Visual Basic**를 확장 하 고는 **SharePoint** 노드를 선택한 후는 **2010** 항목입니다.  
  
3.  에 **템플릿** 창 선택 **SharePoint 2010 프로젝트**, 프로젝트 이름을 **AdventureWorksTest**를 선택한 후는 **확인** 단추 .  
  
     **SharePoint 사용자 지정 마법사** 나타납니다. 이 마법사에서 프로젝트를 디버그 하 고 솔루션의 신뢰 수준을 설정 하는 데 사용할 사이트를 지정할 수 있습니다.  
  
4.  선택 된 **팜 솔루션으로 배포** 옵션 단추를 신뢰 수준을 설정 합니다.  
  
5.  선택 된 **마침** 단추 기본 로컬 SharePoint 사이트를 허용 하도록 합니다.  
  
6.  **솔루션 탐색기**을 SharePoint 프로젝트 노드를 선택 합니다.  
  
7.  메뉴 모음에서 **프로젝트**, **새 항목 추가**합니다.  
  
     **새 항목 추가** 대화 상자가 열립니다.  
  
8.  에 **템플릿** 창에서 선택 **비즈니스 데이터 연결 모델 (팜 솔루션에만 해당)**, 프로젝트 이름을 **adventureworkscontacts로 지정한**는 선택**추가** 단추입니다.  
  
## <a name="adding-data-access-classes-to-the-project"></a>프로젝트에 데이터 액세스 클래스 추가  
  
#### <a name="to-add-data-access-classes-to-the-project"></a>프로젝트에 데이터 액세스 클래스를 추가 하려면  
  
1.  메뉴 모음에서 **도구**, **연결할 데이터베이스**합니다.  
  
     **연결 추가** 대화 상자가 열립니다.  
  
2.  SQL Server AdventureWorks 예제 데이터베이스에 대 한 연결을 추가 합니다.  
  
     자세한 내용은 참조 [연결 추가/수정 (Microsoft SQL Server)](http://msdn.microsoft.com/en-us/fa400910-26c3-4df7-b9d1-115e688b4ea3)합니다.  
  
3.  **솔루션 탐색기**에서 프로젝트 노드를 선택합니다.  
  
4.  메뉴 모음에서 **프로젝트**, **새 항목 추가**합니다.  
  
5.  에 **설치 된 템플릿** 창에서 선택 된 **데이터** 노드.  
  
6.  에 **템플릿** 창 선택 **LINQ to SQL 클래스**합니다.  
  
7.  에 **이름** 상자를 지정 **AdventureWorks**를 선택한 후는 **추가** 단추입니다.  
  
     .dbml 파일이 프로젝트에 추가되고 O/R 디자이너(개체 관계형 디자이너)가 열립니다.  
  
8.  메뉴 모음에서 **보기**, **서버 탐색기**합니다.  
  
9. **서버 탐색기**, AdventureWorks 예제 데이터베이스를 나타내는 노드를 확장 한 다음 확장은 **테이블** 노드.  
  
10. 추가 **Contact (Person)** O/R 디자이너에 끌어 테이블입니다.  
  
     엔터티 클래스가 만들어져 디자인 화면에 표시됩니다. 엔터티 클래스에 Contact (Person) 테이블의 열에 매핑되는 속성이 있습니다.  
  
## <a name="removing-the-default-entity-from-the-bdc-model"></a>기본 엔터티를 BDC 모델에서 제거  
 **비즈니스 데이터 연결 모델** 프로젝트는 모델에 Entity1 이라는 기본 엔터티를 추가 합니다. 이 엔터티를 제거 합니다. 나중에 새 엔터티를 추가 합니다. 빈 모델 부터는 연습을 완료 하는 데 필요한 단계 수가 줄어듭니다.  
  
#### <a name="to-remove-the-default-entity-from-the-model"></a>기본 엔터티를 모델에서 제거 하려면  
  
1.  **솔루션 탐색기**를 확장 하 고는 **BdcModel1** 노드와 다음 BdcModel1.bdcm 파일을 엽니다.  
  
2.  BDC 디자이너에서 비즈니스 데이터 연결 모델 파일이 열립니다.  
  
3.  디자이너에서에 대 한 바로 가기 메뉴를 열고 **Entity1**를 선택한 후 **삭제**합니다.  
  
4.  **솔루션 탐색기**, Entity1.vb (Visual Basic) 또는 Entity1.cs (C#)를 실행 하는 것에 대 한 바로 가기 메뉴를 열고 선택한 후 **삭제**합니다.  
  
5.  Entity1Service.vb (Visual Basic) 또는 Entity1Service.cs (C#)를 실행 하는 것에 대 한 바로 가기 메뉴를 연 다음 선택 **삭제**합니다.  
  
## <a name="adding-an-entity-to-the-model"></a>모델에 엔터티 추가  
 모델에 엔터티를 추가 합니다. Visual Studio에서 엔터티를 추가할 수 있습니다 **도구 상자** BDC 디자이너에 있습니다.  
  
#### <a name="to-add-an-entity-to-the-model"></a>모델에 엔터티를 추가 하려면  
  
1.  메뉴 모음에서 **보기**, **도구 상자**를 차례로 선택합니다.  
  
2.  에 **BusinessDataConnectivity** 탭은 **도구 상자**, 추가 **엔터티** BDC 디자이너에 있습니다.  
  
     새 엔터티 디자이너에 표시 됩니다. Visual Studio에서에서 EntityService.vb (Visual Basic) 또는 EntityService.cs (C#) 프로젝트에 있는 파일을 추가 합니다.  
  
3.  메뉴 모음에서 **보기**, **속성**, **창**합니다.  
  
4.  에 **속성** 창에서 설정 된 **이름** 속성 값을 **연락처**합니다.  
  
5.  디자이너에서 엔터티에 대 한 바로 가기 메뉴를 열고 **추가**를 선택한 후 **식별자**합니다.  
  
     새 식별자는 항목에 나타납니다.  
  
6.  에 **속성** 창 식별자의 이름을 변경 **ContactID**합니다.  
  
7.  에 **유형 이름** 목록에서 선택 **System.Int32**합니다.  
  
## <a name="adding-a-specific-finder-method"></a>특정 Finder 메서드 추가  
 특정 연락처를 표시 하려면 BDC 서비스를 사용 하려면 특정 Finder 메서드를 추가 해야 합니다. BDC 서비스에서 특정 Finder 메서드 호출 하는 경우 사용자는 목록에서 항목을 선택 하 고 다음 선택에서 **보기 항목** 리본의 단추입니다.  
  
 특정 Finder 메서드를 사용 하 여 연락처 엔터티에 추가 **BDC 메서드 세부 정보** 창. 특정 엔터티를 반환 하려면 메서드에 코드를 추가 합니다.  
  
#### <a name="to-add-a-specific-finder-method"></a>특정 Finder 메서드를 추가 하려면  
  
1.  BDC 디자이너에서 선택 된 **연락처** 엔터티.  
  
2.  메뉴 모음에서 **보기**, **다른 창**, **BDC 메서드 세부 정보**합니다.  
  
     BDC 메서드 세부 정보 창이 열립니다.  
  
3.  에 **메서드 추가** 목록에서 선택 **Specificfinder 메서드 만들기**합니다.  
  
     Visual Studio는 모델에 다음과 같은 요소를 추가합니다. 이러한 요소에 표시 된 **BDC 메서드 세부 정보** 창.  
  
    -   ReadItem 라는 메서드가 있습니다.  
  
    -   메서드에 대 한 입력된 매개 변수입니다.  
  
    -   메서드에 대 한 반환 매개 변수입니다.  
  
    -   각 매개 변수에 대해 형식 설명자입니다.  
  
    -   메서드에 대 한 메서드 인스턴스입니다.  
  
4.  에 **BDC 메서드 세부 정보** 창에 대해 표시 되 고 목록을 연는 **연락처** 설명자를 입력 한 다음 **편집**합니다.  
  
     **BDC 탐색기** 열리고 모델의 계층적 뷰를 제공 합니다.  
  
5.  에 **속성** 창 옆에 있는 목록을 연는 **TypeName** 속성을 선택 된 **현재 프로젝트** 탭을 선택 합니다는 **연락처**속성입니다.  
  
6.  에 **BDC 탐색기**의 바로 가기 메뉴를 열고는 **연락처**를 선택한 후 **형식 설명자 추가**합니다.  
  
     이라는 새 형식 설명자 **TypeDescriptor1** 에 표시 된 **BDC 탐색기**합니다.  
  
7.  에 **속성** 창에서 설정 된 **이름** 속성 값을 **ContactID**합니다.  
  
8.  옆에 있는 목록을 연는 **TypeName** 속성을 선택한 후 **Int32**합니다.  
  
9. 옆에 있는 목록을 연는 **식별자** 속성을 선택한 후 **ContactID**합니다.  
  
10. 다음 각 필드에 대 한 형식 설명자를 만들려면 6 단계를 반복 합니다.  
  
    |name|형식 이름|  
    |----------|---------------|  
    |FirstName|System.String|  
    |LastName|System.String|  
    |전화 번호|System.String|  
    |전자 메일 주소|System.String|  
    |EmailPromotion|System.Int32|  
    |NameStyle|System.Boolean|  
    |PasswordHash|System.String|  
    |PasswordSalt|System.String|  
  
11. BDC 디자이너에서에 **연락처** 열기 엔터티는 **ReadItem** 메서드.  
  
     연락처 서비스 코드 파일이 코드 편집기에서 열립니다.  
  
12. 에 `ContactService` 클래스, 대체 된 `ReadItem` 메서드를 다음 코드로 합니다. 이 코드는 다음 작업을 수행합니다.  
  
    -   AdventureWorks 데이터베이스의 Contact 테이블에서 레코드를 검색합니다.  
  
    -   BDC 서비스에는 연락처 엔터티를 반환합니다.  
  
    > [!NOTE]  
    >  값을 바꿉니다는 `ServerName` 필드와 사용자 서버의 이름입니다.  
  
     [!code-csharp[SP_BDC#3](../sharepoint/codesnippet/CSharp/SP_BDC/bdcmodel1/contactservice.cs#3)]
     [!code-vb[SP_BDC#3](../sharepoint/codesnippet/VisualBasic/sp_bdc/bdcmodel1/contactservice.vb#3)]  
  
## <a name="adding-a-finder-method"></a>Finder 메서드 추가  
 BDC 서비스 목록에서 연락처를 표시할 수 있도록 Finder 메서드를 추가 해야 합니다. Finder 메서드를 사용 하 여 연락처 엔터티에 추가 **BDC 메서드 세부 정보** 창. BDC 서비스에 엔터티 컬렉션 반환, 메서드에 코드를 추가 합니다.  
  
#### <a name="to-add-a-finder-method"></a>Finder 메서드를 추가 하려면  
  
1.  BDC 디자이너에서 선택 된 **연락처** 엔터티.  
  
2.  에 **BDC 메서드 세부 정보** 창 축소는 **ReadItem** 노드.  
  
3.  에 **메서드 추가** 목록에서 **ReadList** 메서드를 선택 **Finder 메서드 만들기**합니다.  
  
     Visual Studio는 메서드, 반환 매개 변수 및 형식 설명자에 추가합니다.  
  
4.  BDC 디자이너에서에 **연락처** 열기 엔터티는 **ReadList** 메서드.  
  
     코드 편집기에서 Contact 서비스의 코드 파일이 열립니다.  
  
5.  에 `ContactService` 클래스, 대체 된 `ReadList` 메서드를 다음 코드로 합니다. 이 코드는 다음 작업을 수행합니다.  
  
    -   AdventureWorks 데이터베이스의 Contacts 테이블에서 데이터를 검색합니다.  
  
    -   연락처 엔터티 목록을 BDC 서비스에 반환합니다.  
  
    > [!NOTE]  
    >  값을 바꿉니다는 `ServerName` 필드와 사용자 서버의 이름입니다.  
  
     [!code-csharp[SP_BDC#2](../sharepoint/codesnippet/CSharp/SP_BDC/bdcmodel1/contactservice.cs#2)]
     [!code-vb[SP_BDC#2](../sharepoint/codesnippet/VisualBasic/sp_bdc/bdcmodel1/contactservice.vb#2)]  
  
## <a name="testing-the-project"></a>프로젝트 테스트  
 프로젝트를 실행 하면 SharePoint 사이트가 열리고 Visual Studio을 비즈니스 데이터 연결 서비스 모델에 추가 합니다. 연락처 엔터티를 참조 하는 SharePoint에 외부 목록 만들기 AdventureWorks 데이터베이스에 있는 연락처에 대 한 데이터 목록에 표시 합니다.  
  
> [!NOTE]  
>  솔루션을 디버그할 수 있으려면 SharePoint의 보안 설정을 수정 해야 합니다.  자세한 내용은 참조 [비즈니스 데이터 연결 모델 디자인](../sharepoint/designing-a-business-data-connectivity-model.md)합니다.  
  
#### <a name="to-test-the-project"></a>프로젝트를 테스트하려면  
  
1.  **F5** 키를 선택합니다.  
  
     SharePoint 사이트가 열립니다.  
  
2.  에 **사이트 작업** 메뉴에서 선택 된 **기타 옵션** 명령입니다.  
  
3.  에 **만들기** 페이지를 선택 합니다는 **외부 목록** 서식 파일을 선택한 후는 **만들기** 단추입니다.  
  
4.  사용자 지정 목록 이름을 **연락처**합니다.  
  
5.  찾아보기 단추 옆에 선택 된 **외부 콘텐츠 형식** 필드입니다.  
  
6.  에 **외부 콘텐츠 형식 선택** 대화 상자에서 선택 하는 **AdventureWorksContacts.BdcModel1.Contact** 항목을 선택한 다음 선택는 **만들기** 단추입니다.  
  
     SharePoint에서 AdventureWorks 샘플 데이터베이스의 연락처를 포함하는 외부 목록을 만듭니다.  
  
7.  SpecificFinder 메서드를 테스트하려면 목록에서 연락처를 선택합니다.  
  
8.  리본에서 선택 된 **항목** 탭을 선택 합니다는 **보기 항목** 명령입니다.  
  
     선택한 연락처의 세부 정보가 폼에 나타납니다.  
  
## <a name="next-steps"></a>다음 단계  
 다음이 항목에서는 sharepoint에서 BDC 서비스에 대 한 모델을 디자인 하는 방법에 대 한 자세히 알아볼 수 있습니다.  
  
-   [방법: Creator 메서드 추가](../sharepoint/how-to-add-a-creator-method.md)합니다.  
  
-   [방법: Updater 메서드 추가](../sharepoint/how-to-add-an-updater-method.md)합니다.  
  
-   [방법: Deleter 메서드 추가](../sharepoint/how-to-add-a-deleter-method.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [비즈니스 데이터 연결 모델 디자인](../sharepoint/designing-a-business-data-connectivity-model.md)   
 [비즈니스 데이터 연결 모델 만들기](../sharepoint/creating-a-business-data-connectivity-model.md)   
 [BDC 모델 디자인 도구 개요](../sharepoint/bdc-model-design-tools-overview.md)   
 [SharePoint에 비즈니스 데이터 통합](../sharepoint/integrating-business-data-into-sharepoint.md)  
  
  