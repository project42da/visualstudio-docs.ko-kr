---
title: "연습: 비즈니스 데이터를 사용하여 SharePoint에 외부 목록 만들기 | Microsoft Docs"
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
  - "Business Data Connectivity 서비스[Visual Studio에서 SharePoint 개발], 웹 파트의 비즈니스 데이터"
  - "BDC[Visual Studio에서 SharePoint 개발], 외부 목록"
  - "Business Data Connectivity 서비스[Visual Studio에서 SharePoint 개발], SharePoint 목록의 비즈니스 데이터"
  - "BDC[Visual Studio에서 SharePoint 개발], SharePoint 목록의 비즈니스 데이터"
  - "BDC[Visual Studio에서 SharePoint 개발], 웹 파트의 비즈니스 데이터"
  - "BDC[Visual Studio에서 SharePoint 개발], 엔터티 지원 목록"
  - "Business Data Connectivity 서비스[Visual Studio에서 SharePoint 개발], 엔터티 백업 목록"
  - "Business Data Connectivity 서비스[Visual Studio에서 SharePoint 개발], 외부 목록"
ms.assetid: 046cf234-705a-4a6f-91f8-c5c569ae0dd0
caps.latest.revision: 38
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 37
---
# 연습: 비즈니스 데이터를 사용하여 SharePoint에 외부 목록 만들기
  BDC\(비즈니스 데이터 연결\) 서비스는 SharePoint에서 백 엔드 서버 응용 프로그램, 웹 서비스 및 데이터베이스의 비즈니스 데이터를 표시할 수 있게 해 줍니다.  
  
 이 연습에서는 샘플 데이터베이스의 연락처 정보를 반환하는 BDC 서비스 모델을 만드는 방법을 보여 줍니다.  그 다음에는 이 모델을 사용하여 SharePoint에 외부 목록을 만듭니다.  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   프로젝트 만들기  
  
-   모델에 엔터티 추가  
  
-   Finder 메서드 추가  
  
-   SpecificFinder 메서드 추가  
  
-   프로젝트 테스트  
  
## 사전 요구 사항  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   지원되는 Windows 및 SharePoint 버전.  자세한 내용은 [SharePoint 솔루션 개발 요구 사항](../sharepoint/requirements-for-developing-sharepoint-solutions.md)을 참조하십시오.  
  
-   [!INCLUDE[vsPro](../sharepoint/includes/vspro-md.md)], [!INCLUDE[vsUltLong](../sharepoint/includes/vsultlong-md.md)] 또는 [!INCLUDE[vsPreLong](../sharepoint/includes/vsprelong-md.md)].  
  
-   AdventureWorks 샘플 데이터베이스에 액세스할 수 있는 권한.  AdventureWorks 데이터베이스를 설치하는 방법에 대한 자세한 내용은 [SQL Server 샘플 데이터베이스](http://go.microsoft.com/fwlink/?LinkID=117483) 를 참조하십시오.  
  
## BDC 모델이 포함된 프로젝트 만들기  
  
#### BDC 모델이 포함된 프로젝트를 만들려면  
  
1.  Visual Studio 메뉴 모음을 열고, **파일**에서 **새로 만들기**로 들어가서 **프로젝트**를 선택해 줍니다.  
  
     **새 프로젝트** 대화 상자가 열립니다.  
  
2.  **Visual C\#** 또는 **Visual Basic** 에서 **SharePoint** 노드를 확장한 다음 **2010** 항목을 선택합니다.  
  
3.  **템플릿** 창에서 **SharePoint 2010 프로젝트** 를 선택하고, 프로젝트 이름을 AdventureWorksTest로 입력한 다음, **OK** 버튼을 선택합니다.  
  
     **SharePoint 사용자 지정 마법사**가 나타납니다.  이 마법사를 사용하면 프로젝트를 디버깅하는 데 사용할 사이트와 솔루션의 신뢰 수준을 지정할 수 있습니다.  
  
4.  **팜 솔루션으로 배포** 옵션 버튼을 선택하여 신뢰 수준을 설정합니다.  
  
5.  **마침** 단추를 선택하여 기본 로컬 SharePoint 사이트를 수락합니다.  
  
6.  **솔루션 탐색기**에서 SharePoint 프로젝트 노드를 선택합니다.  
  
7.  메뉴 모음에서 **프로젝트**, **새 항목 추가**를 선택합니다.  
  
     **새 항목 추가** 대화 상자가 열립니다.  
  
8.  **템플릿** 창에서 **비즈니스 데이터 연결 모델 \(팜 솔루션만\)** 을 선택하고, 프로젝트 이름을 AdventureWorksContacts 로 입력한 다음, **추가** 버튼을 선택합니다.  
  
## 프로젝트에 데이터 액세스 클래스 추가  
  
#### 프로젝트에 데이터 액세스 클래스를 추가하려면  
  
1.  메뉴 모음에서 **도구**, **데이터베이스에 연결** 을 선택합니다.  
  
     **연결 추가** 대화 상자가 열립니다.  
  
2.  SQL Server AdventureWorks 샘플 데이터베이스에 대한 연결을 추가합니다.  
  
     자세한 내용은 [Add\/Modify Connection \(Microsoft SQL Server\)](http://msdn.microsoft.com/ko-kr/fa400910-26c3-4df7-b9d1-115e688b4ea3)을 참조하십시오.  
  
3.  **솔루션 탐색기**에서 프로젝트 노드를 선택합니다.  
  
4.  메뉴 모음에서 **프로젝트**, **새 항목 추가**를 선택합니다.  
  
5.  **설치된 템플릿** 창에서 **데이터** 노드를 선택합니다.  
  
6.  **템플릿** 창에서 **LINQ to SQL 클래스**를 선택합니다.  
  
7.  **이름** 상자에서, AdventureWorks를 명시한 다음, **추가** 버튼을 선택합니다.  
  
     .dbml 파일이 프로젝트에 추가되고 O\/R 디자이너\(개체 관계형 디자이너\)가 열립니다.  
  
8.  메뉴 모음에서 **보기**, **서버 탐색기**를 선택합니다.  
  
9. **서버 탐색기**에서 AdventureWorks 샘플 데이터베이스를 나타내는 노드를 확장한 다음 **테이블** 노드를 확장합니다.  
  
10. **Contact \(Person\)** 테이블을 O\/R 디자이너에 추가합니다.  
  
     엔터티 클래스가 만들어져 디자인 화면에 표시됩니다.  이 엔터티 클래스에는 Contact \(Person\) 테이블의 열에 매핑되는 속성이 있습니다.  
  
## BDC 모델에서 기본 엔터티 제거  
 **비즈니스 데이터 연결 모델** 프로젝트는 모델에 Entity1이라는 기본 엔터티를 추가합니다.  이 엔터티를 제거합니다.  나중에 새 엔터티를 추가합니다.  비어 있는 모델로 시작하면 연습을 완료하는 데 필요한 단계가 줄어듭니다.  
  
#### 모델에서 기본 엔터티를 제거하려면  
  
1.  **솔루션 탐색기**에서 **BdcModel1** 노드를 확장한 다음 BdcModel1.bdcm 파일을 엽니다.  
  
2.  비즈니스 데이터 연결 모델 파일이 BDC 디자이너에서 열립니다.  
  
3.  디자이너에서 **Entity1** 의 바로 가기 메뉴를 연 다음 **삭제**를 선택합니다.  
  
4.  **솔루션 탐색기** 에서, Entity1.vb \(Visual Basic\) 또는 Entity1.cs \(C\#\) 의 바로가기 메뉴를 연 다음, **삭제** 를 선택합니다.  
  
5.  Entity1Service.vb \(Visual Basic\) 또는 Entity1Service.cs \(C\#\) 에 대한 바로 가기 메뉴를 열고 **삭제** 를 선택합니다.  
  
## 모델에 엔터티 추가  
 모델에 엔터티를 추가합니다.  Visual Studio **도구 상자**의 엔터티를 BDC 디자이너에 추가할 수 있습니다.  
  
#### 모델에 엔터티를 추가하려면  
  
1.  메뉴 모음에서 **보기**, **도구 상자**를 선택합니다.  
  
2.  **도구 상자** 의 **BusinessDataConnectivity** 탭에서 **엔터티** 를 BDC 디자이너에 추가합니다.  
  
     디자이너에 새 엔터티가 표시됩니다.  Visual Studio에서 EntityService.vb\(Visual Basic\) 또는 EntityService.cs\(C\#\) 파일을 프로젝트에 추가합니다.  
  
3.  메뉴 모음에서 **보기**, **속성**, **창** 을 선택합니다.  
  
4.  **속성** 창에서 **이름** 속성 값을 Contact로 설정합니다.  
  
5.  디자이너에서, 엔터티의 바로 가기 메뉴를 열고 **추가** 를 선택한 다음 **식별자** 를 선택합니다.  
  
     새 식별자가 엔터티에 나타납니다.  
  
6.  **속성** 창에서 식별자 이름을 ContactID로 변경합니다.  
  
7.  **형식 이름** 목록에서 **System.Int32** 을 선택합니다.  
  
## SpecificFinder 메서드 추가  
 BDC 서비스에서 특정 연락처를 표시할 수 있도록 하려면 SpecificFinder 메서드를 추가해야 합니다.  사용자가 목록에서 항목을 선택하고 리본 메뉴에서 **항목 보기** 단추를 선택하면 BDC 서비스에서 SpecificFinder 메서드를 호출합니다.  
  
 **BDC 메서드 세부 정보** 창을 사용하여 Contact 엔터티에 SpecificFinder 메서드를 추가합니다.  특정 엔터티를 반환하려면 메서드에 코드를 추가합니다.  
  
#### SpecificFinder 메서드를 추가하려면  
  
1.  BDC 디자이너에서 **Contact** 엔터티를 선택합니다.  
  
2.  선택 메뉴 모음에서 **보기**, **기타 창**, **BDC 메서드 세부 정보** 을 선택합니다.  
  
     BDC 메서드 세부 정보 창이 열립니다.  
  
3.  **메서드 추가** 목록에서 **Specific Finder 메서드 만들기** 를 선택합니다.  
  
     모델에 다음 요소가 추가됩니다.  이러한 요소는 **BDC 메서드 세부 정보** 창에 표시됩니다.  
  
    -   ReadItem 메서드  
  
    -   메서드의 입력 매개 변수  
  
    -   메서드의 반환 매개 변수  
  
    -   각 매개 변수에 대한 형식 설명자  
  
    -   메서드의 메서드 인스턴스  
  
4.  **BDC 메서드 세부 정보** 창에서, **Contact** 형식 설명자에 대해 표시되는 드롭다운 목록을 연 다음 **편집** 을 선택합니다.  
  
     **BDC 탐색기** 가 열리고 모델의 계층적 뷰를 제공합니다.  
  
5.  **속성** 창에서 **TypeName** 속성 옆에 있는 목록을 열고 **현재 프로젝트** 탭을 선택한 다음 **연락처** 속성을 선택합니다.  
  
6.  **BDC 탐색기** 에서, **Contact** 형식 설명자의 바로 가기 메뉴를 연 다음, **형식 설명자 추가** 를 선택합니다.  
  
     **TypeDescriptor1**이라는 새 형식 설명자가 **BDC 탐색기**에 표시됩니다.  
  
7.  **속성** 창에서 **이름** 속성값을 **ContactID**로 설정합니다.  
  
8.  **TypeName** 속성 옆에 있는 목록을 연 다음 **Int32** 를 선택합니다.  
  
9. **식별자** 속성 옆에 있는 목록을 연 다음 **ContactID** 을 선택합니다.  
  
10. 6단계를 반복하여 다음 각 필드에 대한 형식 설명자를 만듭니다.  
  
    |Name|형식 이름|  
    |----------|-----------|  
    |FirstName|System.String|  
    |LastName|System.String|  
    |Phone|System.String|  
    |EmailAddress|System.String|  
    |EmailPromotion|System.Int32|  
    |NameStyle|System.Boolean|  
    |PasswordHash|System.String|  
    |PasswordSalt|System.String|  
  
11. BDC 디자이너의 **Contact** 엔터티에서 **ReadItem** 메서드를 엽니다.  
  
     코드 편집기에서 Contact 서비스 코드 파일이 열립니다.  
  
12. `ContactService` 클래스에서 `ReadItem` 메서드를 다음 코드로 바꿉니다.  이 코드는 다음 작업을 수행합니다.  
  
    -   AdventureWorks 데이터베이스의 Contact 테이블에서 데이터를 검색합니다.  
  
    -   BDC 서비스에 Contact 엔터티를 반환합니다.  
  
    > [!NOTE]  
    >  `ServerName` 필드의 값을 서버 이름으로 바꿉니다.  
  
     [!code-csharp[SP_BDC#3](../snippets/csharp/VS_Snippets_OfficeSP/sp_bdc/CS/bdcmodel1/contactservice.cs#3)]
     [!code-vb[SP_BDC#3](../snippets/visualbasic/VS_Snippets_OfficeSP/sp_bdc/VB/bdcmodel1/contactservice.vb#3)]  
  
## Finder 메서드 추가  
 BDC 서비스에서 목록에 연락처를 표시할 수 있도록 하려면 Finder 메서드를 추가해야 합니다.  **BDC 메서드 세부 정보** 창에서 Contact 엔터티에 Finder 메서드를 추가합니다.  BDC 서비스에 엔터티 컬렉션을 반환하려면 메서드에 코드를 추가합니다.  
  
#### Finder 메서드를 추가하려면  
  
1.  BDC 디자이너에서 **Contact** 엔터티를 선택합니다.  
  
2.  **BDC 메서드 세부 정보** 창에서 **ReadItem** 노드를 축소합니다.  
  
3.  **ReadList** 메서드 아래의 **메서드 추가** 목록에서 **Finder 메서드 만들기** 를 선택합니다.  
  
     메서드, 반환 매개 변수 및 형식 설명자가 추가됩니다.  
  
4.  BDC 디자이너의 **Contact** 엔터티에서 **ReadList** 메서드를 엽니다.  
  
     코드 편집기에서 Contact 서비스 코드 파일이 열립니다.  
  
5.  `ContactService` 클래스에서 `ReadList` 메서드를 다음 코드로 바꿉니다.  이 코드는 다음 작업을 수행합니다.  
  
    -   AdventureWorks 데이터베이스의 Contacts 테이블에서 데이터를 검색합니다.  
  
    -   Contact 엔터티 목록을 BDC 서비스에 반환합니다.  
  
    > [!NOTE]  
    >  `ServerName` 필드의 값을 서버 이름으로 바꿉니다.  
  
     [!code-csharp[SP_BDC#2](../snippets/csharp/VS_Snippets_OfficeSP/sp_bdc/CS/bdcmodel1/contactservice.cs#2)]
     [!code-vb[SP_BDC#2](../snippets/visualbasic/VS_Snippets_OfficeSP/sp_bdc/VB/bdcmodel1/contactservice.vb#2)]  
  
## 프로젝트 테스트  
 프로젝트를 실행하면 SharePoint 사이트가 열리고 비즈니스 데이터 연결 서비스에 모델이 추가됩니다.  SharePoint에 Contact 엔터티를 참조하는 외부 목록을 만듭니다.  AdventureWorks 데이터베이스의 연락처 데이터가 목록에 표시됩니다.  
  
> [!NOTE]  
>  솔루션을 디버깅하려면 먼저 SharePoint에서 보안 설정을 수정해야 할 수도 있습니다.  자세한 내용은 [비즈니스 데이터 연결 모델 디자인](../sharepoint/designing-a-business-data-connectivity-model.md)을 참조하십시오.  
  
#### 프로젝트를 테스트하려면  
  
1.  **F5** 키를 선택합니다.  
  
     SharePoint 사이트가 열립니다.  
  
2.  **사이트 작업** 메뉴에서 **기타 옵션** 명령을 선택합니다.  
  
3.  **만들기** 페이지에서 **외부 목록** 템플릿을 선택한 다음 **만들기** 버튼을 선택합니다.  
  
4.  사용자 지정 목록의 이름으로 Contacts를 지정합니다.  
  
5.  **외부 콘텐츠 형식** 필드 옆에 있는 찾아보기 단추를 선택합니다.  
  
6.  **외부 콘텐츠 형식 선택** 대화 상자에서 **AdventureWorksContacts.BdcModel1.Contact** 를 선택한 다음 **만들기** 버튼을 선택합니다.  
  
     SharePoint에서 AdventureWorks 샘플 데이터베이스의 연락처를 포함하는 외부 목록을 만듭니다.  
  
7.  SpecificFinder 메서드를 테스트하려면, 목록의 연락처를 선택합니다.  
  
8.  리본에서 **항목** 탭을 선택한 다음 **항목 보기** 명령을 선택합니다.  
  
     선택한 연락처의 세부 정보가 폼에 나타납니다.  
  
## 다음 단계  
 다음 항목에서는 SharePoint에서 BDC 서비스 모델을 디자인하는 방법에 대해 더 자세히 설명합니다.  
  
-   [방법: Creator 메서드 추가](../sharepoint/how-to-add-a-creator-method.md).  
  
-   [방법: Updater 메서드 추가](../sharepoint/how-to-add-an-updater-method.md).  
  
-   [방법: Deleter 메서드 추가](../sharepoint/how-to-add-a-deleter-method.md).  
  
## 참고 항목  
 [비즈니스 데이터 연결 모델 디자인](../sharepoint/designing-a-business-data-connectivity-model.md)   
 [비즈니스 데이터 연결 모델 만들기](../sharepoint/creating-a-business-data-connectivity-model.md)   
 [BDC 모델 디자인 도구 개요](../sharepoint/bdc-model-design-tools-overview.md)   
 [SharePoint에 비즈니스 데이터 통합](../sharepoint/integrating-business-data-into-sharepoint.md)  
  
  