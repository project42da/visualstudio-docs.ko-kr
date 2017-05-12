---
title: "연습: SharePoint를 위한 웹 파트 만들기"
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
  - "웹 파트[Visual Studio에서 SharePoint 개발], 만들기"
  - "웹 파트[Visual Studio에서 SharePoint 개발], 디자인"
  - "웹 파트[Visual Studio에서 SharePoint 개발], 개발"
ms.assetid: 51fb5bdd-b99c-4716-83bc-e66a5da15169
caps.latest.revision: 34
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 33
---
# 연습: SharePoint를 위한 웹 파트 만들기
  웹 파트를 추가하면 사용자가 SharePoint 사이트 페이지의 콘텐츠, 모양 및 동작을 브라우저에서 직접 수정할 수 있습니다.  이 연습에서는 Visual Studio 2010에서 **웹 파트** 항목 템플릿을 사용하여 웹 파트를 만드는 방법을 보여 줍니다.  
  
 이 웹 파트는 직원을 데이터 표에 표시합니다.  사용자는 직원 데이터가 들어 있는 파일의 위치를 지정할 수 있으며  직원 중 관리자만 목록에 나타나도록 데이터 표를 필터링할 수도 있습니다.  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   Visual Studio **웹 파트** 항목 템플릿을 사용하여 웹 파트 만들기  
  
-   웹 파트 사용자가 설정할 수 있는 속성 만들기.  이 속성은 직원 데이터 파일의 위치를 지정합니다.  
  
-   웹 파트 컨트롤 컬렉션에 컨트롤을 추가하여 웹 파트에서 콘텐츠 렌더링  
  
-   렌더링된 웹 파트의 동사 메뉴에 나타나는 새 *동사* 메뉴 항목 만들기.  사용자는 동사를 사용하여 웹 파트에 나타나는 데이터를 수정할 수 있습니다.  
  
-   SharePoint에서 웹 파트 테스트  
  
    > [!NOTE]  
    >  일부 Visual Studio 사용자 인터페이스 요소의 경우 다음 지침에 설명된 것과 다른 이름 또는 위치가 시스템에 표시될 수 있습니다.  설치한 Visual Studio 버전과 사용하는 설정에 따라 이러한 요소가 결정됩니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
## 사전 요구 사항  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   지원되는 Microsoft Windows 및 SharePoint 버전.  자세한 내용은 [SharePoint 솔루션 개발 요구 사항](../sharepoint/requirements-for-developing-sharepoint-solutions.md)을 참조하십시오.  
  
-   [!INCLUDE[vs_pro_current_short](../sharepoint/includes/vs-pro-current-short-md.md)] 또는 Visual Studio ALM\(Application Lifecycle Management\)의 버전  
  
## 빈 SharePoint 프로젝트 만들기  
 먼저 빈 SharePoint 프로젝트를 만듭니다.  나중에 **웹 파트** 항목 템플릿을 사용하여 이 프로젝트에 웹 파트를 추가합니다.  
  
#### 빈 SharePoint 프로젝트를 만들려면  
  
1.  **관리자 권한으로 실행** 옵션을 사용하여 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]를 시작합니다.  
  
2.  메뉴 모음에서 **파일**, **New**, **프로젝트** 선택합니다.  
  
3.  **새 프로젝트** 대화 상자에서 사용할 언어 아래의 **SharePoint** 노드를 확장한 다음 **2010** 노드를 선택합니다.  
  
4.  **템플릿** 창에서 **SharePoint 2010 프로젝트** 항목을 선택한 다음 **확인** 단추를 클릭합니다.  
  
     **SharePoint 사용자 지정 마법사**가 나타납니다.  이 마법사를 사용하면 프로젝트를 디버깅하는 데 사용할 사이트와 솔루션의 신뢰 수준을 선택할 수 있습니다.  
  
5.  **팜 솔루션으로 배포** 옵션 단추를 선택한 다음 **마침** 단추를 선택하여 기본 로컬 SharePoint 사이트를 사용합니다.  
  
## 프로젝트에 웹 파트 추가  
 프로젝트에 **웹 파트** 항목을 추가합니다.  **웹 파트** 항목을 추가하면 웹 파트 코드 파일도 추가됩니다.  나중에 웹 파트의 콘텐츠를 렌더링하는 코드를 이 웹 파트 코드 파일에 추가합니다.  
  
#### 프로젝트에 웹 파트를 추가하려면  
  
1.  메뉴 모음에서 **프로젝트**, **새 항목 추가**를 선택합니다.  
  
2.  **새 항목 추가** 대화 상자의 **설치된 템플릿** 창에서 **SharePoint** 노드를 확장한 다음 **2010** 을 클릭합니다.  
  
3.  SharePoint 템플릿 목록에서, **웹 파트** 템플릿을 선택한 다음 **확인** 단추를 클릭합니다.  
  
     **솔루션 탐색기**에 해당 **웹 파트** 항목이 표시됩니다.  
  
## 웹 파트에서 콘텐츠 렌더링  
 웹 파트에 표시할 컨트롤을 웹 파트 클래스의 컨트롤 컬렉션에 추가하는 방법으로 컨트롤을 지정할 수 있습니다.  
  
#### 웹 파트에서 콘텐츠를 렌더링하려면  
  
1.  **솔루션 탐색기**에서 WebPart1.vb\(Visual Basic\) 또는 WebPart1.cs\(C\#\)를 엽니다.  
  
     코드 편집기에서 웹 파트 코드 파일이 열립니다.  
  
2.  웹 파트 코드 파일의 맨 위에 다음 문을 추가합니다.  
  
     [!code-csharp[SP_WebPart#1](../snippets/csharp/VS_Snippets_OfficeSP/sp_webpart/cs/webpart1/webpart1.cs#1)]
     [!code-vb[SP_WebPart#1](../snippets/visualbasic/VS_Snippets_OfficeSP/sp_webpart/vb/webpart1/webpart1.vb#1)]  
  
3.  `WebPart1` 클래스에 다음 코드를 추가합니다.  이 코드는 다음 필드를 선언합니다.  
  
    -   웹 파트에서 직원을 표시하기 위한 데이터 표  
  
    -   데이터 표를 필터링하는 데 사용되는 컨트롤에 표시되는 텍스트  
  
    -   데이터 표에 데이터를 표시할 수 없는 경우 오류를 보여 주는 레이블  
  
    -   직원 데이터 파일의 경로가 들어 있는 문자열  
  
     [!code-csharp[SP_WebPart#2](../snippets/csharp/VS_Snippets_OfficeSP/sp_webpart/cs/webpart1/webpart1.cs#2)]
     [!code-vb[SP_WebPart#2](../snippets/visualbasic/VS_Snippets_OfficeSP/sp_webpart/vb/webpart1/webpart1.vb#2)]  
  
4.  `WebPart1` 클래스에 다음 코드를 추가합니다.  이 코드는 웹 파트에 `DataFilePath`라는 사용자 지정 속성을 추가합니다.  사용자 지정 속성은 사용자가 SharePoint에서 설정할 수 있는 속성입니다.  이 속성은 데이터 표를 채우는 데 사용되는 XML 데이터 파일의 위치를 가져오거나 설정합니다.  
  
     [!code-csharp[SP_WebPart#3](../snippets/csharp/VS_Snippets_OfficeSP/sp_webpart/cs/webpart1/webpart1.cs#3)]
     [!code-vb[SP_WebPart#3](../snippets/visualbasic/VS_Snippets_OfficeSP/sp_webpart/vb/webpart1/webpart1.vb#3)]  
  
5.  `CreateChildControls` 메서드를 다음 코드로 바꿉니다.  이 코드는 다음 작업을 수행합니다.  
  
    -   이전 단계에서 선언한 데이터 표와 레이블을 추가합니다.  
  
    -   데이터 표를 직원 데이터가 들어 있는 XML 파일에 바인딩합니다.  
  
     [!code-csharp[SP_WebPart#4](../snippets/csharp/VS_Snippets_OfficeSP/sp_webpart/cs/webpart1/webpart1.cs#4)]
     [!code-vb[SP_WebPart#4](../snippets/visualbasic/VS_Snippets_OfficeSP/sp_webpart/vb/webpart1/webpart1.vb#4)]  
  
6.  `WebPart1` 클래스에 다음 메서드를 추가합니다.  이 코드는 다음 작업을 수행합니다.  
  
    -   렌더링된 웹 파트의 웹 파트 동사 메뉴에 표시되는 동사를 만듭니다.  
  
    -   사용자가 동사 메뉴의 동사를 선택할 때 발생하는 이벤트를 처리합니다.  이 코드는 데이터 표에 표시되는 직원 목록을 필터링합니다.  
  
     [!code-csharp[SP_WebPart#5](../snippets/csharp/VS_Snippets_OfficeSP/sp_webpart/cs/webpart1/webpart1.cs#5)]
     [!code-vb[SP_WebPart#5](../snippets/visualbasic/VS_Snippets_OfficeSP/sp_webpart/vb/webpart1/webpart1.vb#5)]  
  
## 웹 파트 테스트  
 프로젝트를 실행하면 SharePoint 사이트가 열립니다.  웹 파트는 SharePoint의 웹 파트 갤러리에 자동으로 추가됩니다.  모든 웹 파트 페이지에 웹 파트를 추가할 수 있습니다.  
  
#### 웹 파트를 테스트하려면  
  
1.  다음 XML을 메모장 파일에 붙여넣습니다.  이 XML 파일에는 웹 파트에 표시되는 샘플 데이터가 들어 있습니다.  
  
    ```  
  
    <employees xmlns="http://schemas.microsoft.com/vsto/samples">  
       <employee>  
           <name>David Hamilton</name>  
           <hireDate>2001-05-11</hireDate>  
           <title>Sales Associate</title>  
       </employee>  
       <employee>  
           <name>Karina Leal</name>  
           <hireDate>1999-04-01</hireDate>  
           <title>Manager</title>  
       </employee>  
       <employee>  
           <name>Nancy Davolio</name>  
           <hireDate>1992-05-01</hireDate>  
           <title>Sales Associate</title>  
       </employee>  
       <employee>  
           <name>Steven Buchanan</name>  
           <hireDate>1955-03-04</hireDate>  
           <title>Manager</title>  
       </employee>  
       <employee>  
           <name>Suyama Michael</name>  
           <hireDate>1963-07-02</hireDate>  
           <title>Sales Associate</title>  
       </employee>  
    </employees>  
    ```  
  
2.  메모장의 메뉴 모음에서 **파일**, **저장**을 차례로 선택합니다.  
  
3.  **다른 이름으로 저장** 대화 상자의 **파일 형식** 목록에서 **모든 파일**을 선택합니다.  
  
4.  **파일 이름** 상자에 data.xml을 입력합니다.  
  
5.  **폴더 찾아보기** 단추를 사용하여 폴더를 선택한 다음 **저장** 버튼을 클릭합니다.  
  
6.  Visual Studio에서 **F5** 키를 누릅니다.  
  
     SharePoint 사이트가 열립니다.  
  
7.  **사이트 작업** 메뉴에서 **기타 옵션**을 선택합니다.  
  
8.  **만들기** 페이지에서 **웹 파트 페이지** 형식을 선택한 다음 **만들기** 단추를 클릭합니다.  
  
9. **새 웹 파트 페이지** 페이지에서 페이지 이름으로 **SampleWebPartPage.aspx**를 지정한 다음 **만들기** 버튼을 클릭합니다.  
  
     웹 파트 페이지가 표시됩니다.  
  
10. 웹 파트 페이지의 아무 영역이나 선택합니다.  
  
11. 페이지 위쪽에서 **삽입** 탭을 선택한 다음 **웹 파트** 버튼을 클릭합니다.  
  
12. **범주** 창에서 **사용자 지정** 폴더를 선택하고 **WebPart1** 웹 파트를 선택한 다음 **추가** 버튼을 클릭합니다.  
  
     페이지에 웹 파트 페이지가 표시됩니다.  
  
## 사용자 지정 속성 테스트  
 웹 파트에 표시되는 데이터 표를 채우려면 각 직원에 대한 정보가 들어 있는 XML 파일의 경로를 지정합니다.  
  
#### 사용자 지정 속성을 테스트하려면  
  
1.  웹 파트의 오른쪽에 나타나는 화살표를 누른 다음 표시된 메뉴에서 **웹 파트 편집** 을 선택합니다.  
  
     웹 파트의 속성이 포함된 창이 페이지 오른쪽에 표시됩니다.  
  
2.  창에서 **기타** 노드를 확장하고 이전에 만든 XML 파일의 경로를 입력한 다음 **적용**, **확인** 버튼을 차례로 클릭합니다.  
  
     직원 목록이 웹 파트에 표시되는지 확인합니다.  
  
## 웹 파트 동사 테스트  
 웹 파트 동사 메뉴에 표시되는 항목을 클릭하여 관리자가 아닌 직원을 표시하고 숨깁니다.  
  
#### 웹 파트 동사를 테스트하려면  
  
1.  웹 파트의 오른쪽에 나타나는 화살표를 누른 다음 표시된 메뉴에서 **관리자에게만 보여주기** 을 선택합니다.  
  
     관리자에 해당하는 직원만 웹 파트에 표시됩니다.  
  
2.  화살표를 다시 선택한 다음 표시된 메뉴에서 **모든 직원 표시** 를 선택합니다.  
  
     모든 직원이 웹 파트에 표시됩니다.  
  
## 참고 항목  
 [SharePoint를 위한 웹 파트 만들기](../sharepoint/creating-web-parts-for-sharepoint.md)   
 [방법: SharePoint 웹 파트 만들기](../sharepoint/how-to-create-a-sharepoint-web-part.md)   
 [방법: 디자이너를 사용하여 SharePoint 웹 파트 만들기](../sharepoint/how-to-create-a-sharepoint-web-part-by-using-a-designer.md)   
 [연습: 디자이너를 사용하여 SharePoint를 위한 웹 파트 만들기](../sharepoint/walkthrough-creating-a-web-part-for-sharepoint-by-using-a-designer.md)  
  
  