---
title: "연습: SharePoint용 OData를 표시하는 Silverlight 웹 파트 만들기 | Microsoft Docs"
ms.custom: ""
ms.date: "02/22/2017"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "office-development"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "VS.SharePointTools.SPE.SilverlightWebPart"
dev_langs: 
  - "VB"
  - "CSharp"
ms.assetid: 92d55e68-8f3f-4bf7-a21b-801c298b04c4
caps.latest.revision: 21
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 20
---
# 연습: SharePoint용 OData를 표시하는 Silverlight 웹 파트 만들기
  SharePoint 2010 은 OData를 사용하여 목록 데이터를 노출합니다.  Sharepoint에서 OData 서비스는 RESTful 서비스 ListData.svc에 의해 구현 됩니다.  이 연습에서는 Silverlight 응용 프로그램을 호스팅하는 SharePoint 웹 파트를 만드는 방법을 보여 줍니다.  Silverlight 응용 프로그램은 ListData.svc를 사용하여 SharePoint 공지 사항 목록 정보를 표시 합니다.  자세한 내용은 [SharePoint Foundation REST 인터페이스](http://go.microsoft.com/fwlink/?LinkId=225999) 및 [Open Data Protocol](http://go.microsoft.com/fwlink/?LinkId=226000) 을 참조하십시오.  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   [Silverlight 응용 프로그램 및 Silverlight 웹 파트 만들기](#BKMK_creatingSLApp).  
  
-   [Silverlight 응용 프로그램 사용자 지정](#BKMK_customizeSLApp)  
  
-   [Silverlight 응용 프로그램 사용자 지정](#BKMK_customizeSLApp).  
  
-   [Silverlight 응용 프로그램 사용자 지정](#BKMK_customizeSLApp).  
  
-   [Silverlight 웹 파트 테스트](#BKMK_testSLApp).  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## 사전 요구 사항  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   지원되는 Microsoft Windows 및 SharePoint 버전.  [!INCLUDE[crdefault](../sharepoint/includes/crdefault-md.md)] [SharePoint 솔루션 개발 요구 사항](../sharepoint/requirements-for-developing-sharepoint-solutions.md).  
  
-   [!INCLUDE[vs_dev11_long](../sharepoint/includes/vs-dev11-long-md.md)].  
  
##  <a name="BKMK_creatingSLApp"></a> Silverlight 응용 프로그램 및 Silverlight 웹 파트 만들기  
 먼저, Visual Studio에서 Silverlight 응용 프로그램을 만듭니다.  Silverlight 응용 프로그램은 ListData.svc 서비스를 사용하여 SharePoint 공지 사항 목록에서 데이터를 검색 합니다.  
  
> [!NOTE]  
>  Silverlight 4.0 이전 버전에서는 SharePoint 목록의 데이터를 참조 하기 위해 필요한 인터페이스를 지원하지 않습니다.  
  
#### Silverlight 응용 프로그램 및 Silverlight 웹 파트를 만드려면  
  
1.  메뉴 모음에서 **파일**, **새로 만들기**, **프로젝트**를 선택하여 **새 프로젝트** 대화 상자를 엽니다.  
  
2.  **Visual C\#** 또는 **Visual Basic** 아래의 **SharePoint** 노드를 확장한 다음 **2010** 을 선택합니다.  
  
3.  템플릿 창에서, **SharePoint 2010 Silverlight 웹 파트** 템플릿을 선택합니다.  
  
4.  **이름** 상자에서 SLWebPartTest를 입력한 후 **OK** 버튼을 선택합니다.  
  
     **SharePoint 사용자 지정 마법사** 대화 상자가 나타납니다.  
  
5.  **디버깅에 사용할 사이트 및 보안 수준 지정** 페이지에서, 사이트 정의를 디버깅할 SharePoint 서버 사이트의 URL을 입력하거나 기본 위치\(http:\/\/*system name*\/\)를 사용합니다.  
  
6.  **이 SharePoint 솔루션의 신뢰 수준을 선택하십시오.** 섹션에서 **팜 솔루션으로 배포** 옵션 단추를 선택합니다.  
  
     이 예제에서는 팜 솔루션을 사용하지만, Silverlight 웹 파트 프로젝트는 팜 또는 샌드박스가 적용 된 솔루션으로 배포될 수 있습니다.  샌드박스가 적용된 솔루션과 팜 솔루션 비교에 대한 자세한 내용은 [샌드박스가 적용된 솔루션 고려 사항](../sharepoint/sandboxed-solution-considerations.md)을 참조하십시오.  
  
7.  **Silverlight 구성 정보를 지정** 페이지의 **Silverlight 웹 파트를 어떻게 연결 하시겠습니까?** 섹션에서 **새 Silverlight 프로젝트 만들기 및 웹 파트에 연결** 옵션 버튼을 선택합니다.  
  
8.  **이름** 을 SLApplication 으로 변경하고 **언어** 를 **Visual Basic** 또는 **Visual C\#** 으로 설정한 다음 **Silverlight 버전** 을 **Silverlight 4.0** 으로 설정합니다.  
  
9. **마침** 단추를 선택합니다.  프로젝트가 **솔루션 탐색기**에 나타납니다.  
  
     솔루션은 두 개의 프로젝트, Silverlight 응용 프로그램 및 Silverlight 웹 파트를 포함합니다.  Silverlight 응용 프로그램은 SharePoint에서 목록 데이터의 검색 및 표시를 하고, Silverlight 웹 파트는 이것을 SharePoint에서 볼 수 있도록 Silverlight 응용 프로그램을 호스트 합니다.  
  
##  <a name="BKMK_customizeSLApp"></a> Silverlight 응용 프로그램 사용자 지정  
 Silverlight 응용 프로그램에 코드 및 디자인 요소를 추가 합니다.  
  
#### Silverlight 응용 프로그램을 사용자 지정 하려면  
  
1.  Silverlight 응용 프로그램에서 System.Windows.Data에 대한 어셈블리 참조를 추가 합니다.  자세한 내용은 [방법: 참조 추가 대화 상자를 사용하여 참조 추가 또는 제거](http://msdn.microsoft.com/ko-kr/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)을 참조하십시오.  
  
2.  **솔루션 탐색기**에서 **참조**의 바로 가기 메뉴를 열고 **서비스 참조 추가**를 선택합니다.  
  
    > [!NOTE]  
    >  Visual Basic 사용 하는 경우, **참조** 노드를 표시하려면 **솔루션 탐색기** 맨 위에 있는 **모든 파일 표시** 아이콘을 사용해야 합니다.  
  
3.  **서비스 참조 추가** 대화 상자의 주소 상자에서, **http:\/\/MySPSite** 와 같은 SharePoint 사이트의 URL을 입력 한 다음 **이동** 버튼을 선택합니다.  
  
     Silverlight 가 SharePoint OData 서비스 ListData.svc를 찾으면, 주소를 전체 서비스 URL 주소로 바꿉니다.  이 예제에서는 http:\/\/myserver 가 http:\/\/myserver\/\_vti\_bin\/ListData.svc 로 바뀝니다.  
  
4.  **확인** 버튼을 선택하여 프로젝트에 서비스 참조를 추가하고, 기본 서비스 이름인 ServiceReference1을 사용 합니다.  
  
5.  메뉴 모음에서 **빌드**, **솔루션 빌드**를 선택합니다.  
  
6.  새 데이터 원본을 SharePoint 서비스를 기반의 프로젝트에 추가 합니다.  이것을 하려면, 선택 메뉴 모음에서 **보기**, **기타 Windows**, **데이터 소스**를 선택합니다.  
  
     **데이터 소스** 창에 작업, 공지 사항, 일정과 같은 사용할 수 있는 모든 SharePoint 목록 데이터가 표시됩니다.  
  
7.  공지 사항 목록 데이터를 Silverlight 응용 프로그램에 추가 합니다.  **데이터 소스** 창에서 "공지"를 Silverlight 디자이너 창에 추가합니다.  
  
     이것은 SharePoint 사이트의 공지 사항 목록에 바인딩된 눈금 컨트롤을 만듭니다.  
  
8.  Silverlight 페이지에 맞게 표 컨트롤의 크기를 조정 합니다.  
  
9. MainPage.xaml 코드 파일 \(Visual C\#의 MainPage.xaml.cs 또는 Visual Basic의 MainPage.xaml.vb\) 에 다음 네임 스페이스 참조를 추가 합니다.  
  
    ```vb  
    ' Add the following three Imports statements.  
    Imports SLApplication.ServiceReference1  
    Imports System.Windows.Data  
    Imports System.Data.Services.Client  
    ```  
  
    ```csharp  
    // Add the following three using statements.  
    using SLApplication.ServiceReference1;  
    using System.Windows.Data;  
    using System.Data.Services.Client;  
    ```  
  
<!-- TODO: review snippet reference      [!CODE [SP_SLWebPart#1](SP_SLWebPart#1)]  -->  
  
10. 다음 변수 선언을 클래스의 맨 위에 추가합니다.  
  
    ```vb  
    Private context As TeamSiteDataContext  
    Private myCollectionViewSource As CollectionViewSource  
    Private announcements As New DataServiceCollection(Of AnnouncementsItem)()  
    ```  
  
    ```csharp  
    private TeamSiteDataContext context;  
    private CollectionViewSource myCollectionViewSource;  
    DataServiceCollection<AnnouncementsItem> announcements = new DataServiceCollection<AnnouncementsItem>();  
    ```  
  
<!-- TODO: review snippet reference      [!CODE [SP_SLWebPart#2](SP_SLWebPart#2)]  -->  
  
11. `UserControl_Loaded` 프로시저를 다음 코드로 바꿉니다.  
  
    ```vb  
    Private Sub UserControl_Loaded_1(sender As Object, e As RoutedEventArgs)  
        ' The URL for the OData service.  
        ' Replace <server name> in the next line with the name of your SharePoint server.  
        context = New TeamSiteDataContext(New Uri("http://<server name>/_vti_bin/ListData.svc"))  
  
        ' Do not load your data at design time.  
        If Not System.ComponentModel.DesignerProperties.GetIsInDesignMode(Me) Then  
            'Load your data here and assign the results to the CollectionViewSource.  
            myCollectionViewSource =   DirectCast(Me.Resources("announcementsViewSource"), System.Windows.Data.CollectionViewSource)  
            announcements.LoadCompleted += New EventHandler(Of LoadCompletedEventArgs)(AddressOf announcements_LoadCompleted)  
            announcements.LoadAsync(context.Announcements)  
        End If  
    End Sub  
    ```  
  
    ```csharp  
    private void UserControl_Loaded_1(object sender, RoutedEventArgs e)  
    {  
        // The URL for the OData service.  
        // Replace <server name> in the next line with the name of your   
        // SharePoint server.  
        context = new TeamSiteDataContext(new Uri("http://ServerName>/_vti_bin/ListData.svc"));  
  
        // Do not load your data at design time.  
        if (!System.ComponentModel.DesignerProperties.GetIsInDesignMode(this))  
        {  
            //Load your data here and assign the results to the CollectionViewSource.  
            myCollectionViewSource = (System.Windows.Data.CollectionViewSource)this.Resources["announcementsViewSource"];  
            announcements.LoadCompleted += new EventHandler<LoadCompletedEventArgs>(announcements_LoadCompleted);  
            announcements.LoadAsync(context.Announcements);  
        }  
    }  
    ```  
  
<!-- TODO: review snippet reference      [!CODE [SP_SLWebPart#3](SP_SLWebPart#3)]  -->  
  
     *ServerName* 자리 표시자를 SharePoint를 실행 하는 서버 이름으로 대체합니다.  
  
12. 다음 오류 처리 프로시저를 추가 합니다.  
  
    ```vb  
    Private Sub announcements_LoadCompleted(sender As Object, e As LoadCompletedEventArgs)  
        ' Handle any errors.  
        If e.[Error] Is Nothing Then  
            myCollectionViewSource.Source = announcements  
        Else  
            MessageBox.Show(String.Format("ERROR: {0}", e.[Error].Message))  
        End If  
    End Sub  
  
    ```  
  
    ```csharp  
    void announcements_LoadCompleted(object sender, LoadCompletedEventArgs e)  
    {  
        // Handle any errors.  
        if (e.Error == null)  
        {  
            myCollectionViewSource.Source = announcements;  
        }  
        else  
        {  
            MessageBox.Show(string.Format("ERROR: {0}", e.Error.Message));  
        }  
    }  
    ```  
  
<!-- TODO: review snippet reference      [!CODE [SP_SLWebPart#4](SP_SLWebPart#4)]  -->  
  
## Silverlight 웹 파트 수정  
 Silverlight 디버깅을 활성화 하려면 Silverlight 웹 파트 프로젝트에 속성을 변경 합니다.  
  
#### Silverlight 웹 파트를 수정하려면  
  
1.  Silverlight 웹 파트 프로젝트 \(**SLWebPartTest**\) 의 바로 가기 메뉴를 열고 **속성**을 선택합니다.  
  
2.  **속성** 창에서 **SharePoint** 탭을 선택합니다.  
  
3.  선택 되어 있지 않은 경우, **\(스크립트 디버깅 대신\) Silverlight 디버깅 사용** 확인란을 선택합니다.  
  
4.  프로젝트를 저장합니다.  
  
##  <a name="BKMK_testSLApp"></a> Silverlight 웹 파트 테스트  
 SharePoint 목록 데이터가 올바르게 표시 되도록 하려면 SharePoint에서 새 Silverlight 웹 파트를 테스트 합니다.  
  
#### Silverlight 웹 파트를 테스트하려면  
  
1.  F5 키를 눌러 SharePoint 솔루션을 빌드하고 실행합니다.  
  
2.  Sharepoint의 **사이트 작업** 메뉴에서 **새 페이지** 를 선택합니다.  
  
3.  **새 페이지** 다이얼로그에서, SL 웹 파트 테스트와 같은 제목을 입력한 다음 **만들기** 버튼을 선택합니다.  
  
4.  페이지 디자이너의 **편집 도구** 탭에서 **삽입** 을 선택합니다.  
  
5.  탭 스트립에서 **웹 파트** 를 선택합니다.  
  
6.  **범주** 상자에서 **사용자 지정** 폴더를 선택합니다.  
  
7.  **웹 파트** 목록에서, Silverlight 웹 파트를 선택한 다음 **추가** 버튼을 선태갛여 디자이너에 웹 파트를 추가합니다.  
  
8.  웹 페이지에 추가할 것을 다 추가하고 난 후, **페이지** 탭을 선택하고, 도구 모음에서 **저장 & 닫기** 버튼을 선택합니다.  
  
     이제 Silverlight 웹 파트는 SharePoint 사이트의 알림 데이터를 표시합니다.  기본적으로 페이지는 SharePoint에서 사이트 페이지 목록에 저장 됩니다.  
  
    > [!NOTE]  
    >  Silverlight에서 도메인 간 데이터를 액세스할 때, Silverlight 는 웹 응용 프로그램을 악용하는데 사용될 수 있는 보안 취약점으로부터 보호 합니다.  Silverlight에서 원격 데이터에 액세스 할 때 문제가 발생 하면 [도메인 경계간 사용할 수 있는 서비스 만들기](http://go.microsoft.com/fwlink/?LinkId=223276) 을 참조하십시오.  
  
## 참고 항목  
 [SharePoint를 위한 웹 파트 만들기](../sharepoint/creating-web-parts-for-sharepoint.md)   
 [SharePoint 솔루션 패키지 배포, 게시 및 업그레이드](../sharepoint/deploying-publishing-and-upgrading-sharepoint-solution-packages.md)  
  
  