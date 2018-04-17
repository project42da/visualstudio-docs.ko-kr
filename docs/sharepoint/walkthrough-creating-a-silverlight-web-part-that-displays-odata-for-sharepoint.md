---
title: '연습: SharePoint 용 OData를 표시 하는 Silverlight 웹 파트 만들기 | Microsoft Docs'
ms.custom: ''
ms.date: 02/22/2017
ms.technology:
- office-development
ms.topic: conceptual
f1_keywords:
- VS.SharePointTools.SPE.SilverlightWebPart
dev_langs:
- VB
- CSharp
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 019c1d4b20f1d7a53fc68ef561d45989e93eee28
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="walkthrough-creating-a-silverlight-web-part-that-displays-odata-for-sharepoint"></a>연습: SharePoint용 OData를 표시하는 Silverlight 웹 파트 만들기
  SharePoint 2010 OData를 사용 하 여 해당 목록 데이터를 제공합니다. SharePoint, OData 서비스 ListData.svc RESTful 서비스에 의해 구현 됩니다. 이 연습에서는 Silverlight 응용 프로그램을 호스팅하는 SharePoint 웹 파트를 만드는 방법을 보여 줍니다. Silverlight 응용 프로그램 ListData.svc를 사용 하 여 SharePoint 알림 목록 정보를 표시 합니다. 자세한 내용은 참조 [SharePoint Foundation REST 인터페이스](http://go.microsoft.com/fwlink/?LinkId=225999) 및 [개방형 데이터 프로토콜](http://go.microsoft.com/fwlink/?LinkId=226000)합니다.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>전제 조건  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   지원되는 Microsoft Windows 및 SharePoint 버전. [!INCLUDE[crdefault](../sharepoint/includes/crdefault-md.md)] [SharePoint 솔루션 개발을 위한 요구 사항](../sharepoint/requirements-for-developing-sharepoint-solutions.md)합니다.  
  
-   [!INCLUDE[vs_dev11_long](../sharepoint/includes/vs-dev11-long-md.md)].  
  
##  <a name="creating-a-silverlight-application-and-silverlight-web-part"></a>Silverlight 응용 프로그램과 Silverlight 웹 파트 만들기  
 먼저 Visual Studio에서 Silverlight 응용 프로그램을 만듭니다. Silverlight 응용 프로그램 ListData.svc 서비스를 사용 하 여 SharePoint 알림 목록에서 데이터를 검색 합니다.  
  
> [!NOTE]  
>  버전의 Silverlight 4.0 하기 전에 SharePoint 목록 데이터를 참조 하기 위해 필요한 인터페이스를 지원 합니다.  
  
#### <a name="to-create-a-silverlight-application-and-silverlight-web-part"></a>Silverlight 응용 프로그램 및 Silverlight 웹 파트를 만들려면  
  
1.  메뉴 모음에서 **파일**, **새로**, **프로젝트** 표시 하는 **새 프로젝트** 대화 상자.  
  
2.  확장 하 고는 **SharePoint** 노드 아래의 **Visual C#** 또는 **Visual Basic**를 선택한 후는 **2010** 노드.  
  
3.  템플릿 창에서 선택 된 **SharePoint 2010 Silverlight 웹 파트** 템플릿.  
  
4.  에 **이름** 상자에 입력 **SLWebPartTest** 선택한 후는 **확인** 단추입니다.  
  
     **SharePoint 사용자 지정 마법사** 대화 상자가 나타납니다.  
  
5.  에 **디버깅에 대 한 사이트 및 보안 수준을 지정** 페이지, 사이트 정의 디버깅 하려는 SharePoint 서버 사이트에 대 한 URL을 입력 하거나 기본 위치를 사용 하 여 (http://*시스템 이름*/) .  
  
6.  에 **이 SharePoint 솔루션에 대 한 신뢰 수준을?** 섹션에서 선택 된 **팜 솔루션으로 배포** 옵션 단추입니다.  
  
     이 예제에서는 팜 솔루션을 사용 하지만 Silverlight 웹 파트 프로젝트 팜 또는 샌드박스 솔루션으로 배포할 수 있습니다. 샌드박스 솔루션과 팜 솔루션에 대 한 자세한 내용은 참조 [샌드박스 솔루션 고려 사항](../sharepoint/sandboxed-solution-considerations.md)합니다.  
  
7.  에 **Silverlight 웹 파트를 연결 하 시겠습니까** 의 섹션은 **Silverlight 구성 정보를 지정** 페이지를 선택 합니다는 **새 Silverlight 프로젝트 만들기 및 웹 파트와 연결** 옵션 단추입니다.  
  
8.  변경의 **이름** 를 **SLApplication**설정, **언어** 을 **Visual Basic** 또는 **Visual C#**, 다음 설정 **Silverlight 버전** 를 **Silverlight 4.0**합니다.  
  
9. 선택 된 **마침** 단추입니다. 프로젝트에 표시 **솔루션 탐색기**합니다.  
  
     솔루션에 두 개의 프로젝트가 포함 된: Silverlight 응용 프로그램과 Silverlight 웹 파트입니다. Silverlight 응용 프로그램 검색 하 고 SharePoint에서 목록 데이터를 표시 하 고 Silverlight 웹 파트를 SharePoint에서 볼 수 있게 해 주는 Silverlight 응용 프로그램을 호스트 합니다.  
  
##  <a name="customizing-the-silverlight-application"></a>Silverlight 응용 프로그램을 사용자 지정  
 Silverlight 응용 프로그램에 코드와 디자인 요소를 추가 합니다.  
  
#### <a name="to-customize-the-silverlight-application"></a>Silverlight 응용 프로그램을 사용자 지정 하려면  
  
1.  Silverlight 응용 프로그램에서 System.Windows.Data에 대 한 어셈블리 참조를 추가 합니다. 자세한 내용은 참조 [하는 방법: 참조 추가 또는 제거 참조 추가 대화 상자를 사용 하 여](http://msdn.microsoft.com/en-us/3bd75d61-f00c-47c0-86a2-dd1f20e231c9)합니다.  
  
2.  **솔루션 탐색기**, 바로 가기 메뉴를 열고 **참조**를 선택한 후 **서비스 참조 추가**합니다.  
  
    > [!NOTE]  
    >  Visual Basic을 사용 하는 경우 선택 해야는 **모든 파일 표시** 맨 위에 있는 아이콘 **솔루션 탐색기** 표시 하는 **참조** 노드.  
  
3.  주소 상자에는 **서비스 참조 추가** 대화 상자와 같은 SharePoint 사이트의 URL을 입력 합니다 **http://MySPSite**를 선택한 후는 **이동** 단추입니다.  
  
     Silverlight ListData.svc SharePoint OData 서비스를 찾으면 주소를 전체 서비스 URL로 바꿉니다. 예를 들어 http://myserver 되 http://myserver/_vti_bin/ListData.svc합니다.  
  
4.  선택 된 **확인** 을 프로젝트에 서비스 참조 추가 단추 및 ServiceReference1 기본 서비스 이름을 사용 합니다.  
  
5.  메뉴 모음에서 **빌드**, **솔루션 빌드**를 선택합니다.  
  
6.  SharePoint 서비스를 기반으로 프로젝트에 새 데이터 원본을 추가 합니다. 메뉴 모음에서이 작업을 수행 하려면 선택 **보기**, **다른 창**, **데이터 소스**합니다.  
  
     **데이터 소스** 창의 모든 작업, 알림, 일정 등 사용 가능한 SharePoint 목록 데이터를 표시 합니다.  
  
7.  Silverlight 응용 프로그램에 공지 사항 목록 데이터를 추가 합니다. "공지 사항"을 끌어 놓을 수는 **데이터 소스** Silverlight 디자이너 창.  
  
     SharePoint 사이트의 알림 목록에 바인딩된 그리드 컨트롤을 만듭니다.  
  
8.  Silverlight 페이지에 맞게 그리드 컨트롤의 크기를 조정 합니다.  
  
9. MainPage.xaml의 코드 파일 (MainPage.xaml.cs에 대 한 Visual C#) 또는 MainPage.xaml.vb Visual basic의 경우 다음 네임 스페이스 참조를 추가 합니다.  
  
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
  
10. 클래스의 맨 위에 다음 변수 선언을 추가 합니다.  
  
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
   
11. 대체는 `UserControl_Loaded` 다음으로는 프로시저입니다.  
  
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
     바꿔야는 *ServerName* SharePoint를 실행 하는 서버의 이름으로 자리 표시자입니다.  
  
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
       
## <a name="modifying-the-silverlight-web-part"></a>Silverlight 웹 파트를 수정합니다.  
 Silverlight 디버깅을 사용 하려면 Silverlight 웹 파트 프로젝트에서 속성을 변경 합니다.  
  
#### <a name="to-modify-the-silverlight-web-part"></a>Silverlight 웹 파트를 수정 하려면  
  
1.  Silverlight 웹 파트 프로젝트에 대 한 바로 가기 메뉴를 열고 (**SLWebPartTest**)를 선택한 후 **속성**합니다.  
  
2.  에 **속성** 창, 선택는 **SharePoint** 탭 합니다.  
  
3.  선택 되어 있지 않은 경우 선택 된 **스크립트 디버깅 대신 Silverlight 사용 디버깅** 확인란 합니다.  
  
4.  프로젝트를 저장합니다.  
  
##  <a name="testing-the-silverlight-web-part"></a>Silverlight 웹 파트를 테스트합니다.  
 SharePoint 목록 데이터 제대로 표시 되는지 확인 하려면 SharePoint에서 새 Silverlight 웹 파트를 테스트 합니다.  
  
#### <a name="to-test-the-silverlight-web-part"></a>Silverlight 웹 파트를 테스트 하려면  
  
1.  빌드하고 SharePoint 솔루션을 실행 하려면 F5 키를 선택 합니다.  
  
2.  Sharepoint에서에 **사이트 작업** 메뉴 선택 **새 페이지**합니다.  
  
3.  에 **새 페이지** 대화 상자에서와 같은 제목을 입력 **SL 웹 파트 테스트**를 선택한 후는 **만들기** 단추입니다.  
  
4.  페이지 디자이너에서에 **편집 도구** 탭에서 선택 **삽입**합니다.  
  
5.  탭 스트립에서 선택 **웹 파트**합니다.  
  
6.  에 **범주** 상자는 **사용자 지정** 폴더입니다.  
  
7.  에 **웹 파트** 목록, Silverlight 웹 파트를 선택 하 고, 선택는 **추가** 디자이너에 웹 파트를 추가 하는 단추입니다.  
  
8.  만든 후 추가 된 항목의 모든 원하는 웹 페이지에, 선택는 **페이지** 탭을 선택한 후는 **저장 후 닫기** 도구 모음에서 단추입니다.  
  
     Silverlight 웹 파트는 SharePoint 사이트에서 알림 데이터 이제 표시 해야 합니다. 기본적으로 페이지는 sharepoint에서 사이트 페이지 목록에 저장 됩니다.  
  
    > [!NOTE]  
    >  도메인 간 Silverlight에 대 한 데이터를 액세스할 때 Silverlight 웹 응용 프로그램을 악용 하는 데 사용할 수 있는 보안 취약점 으로부터 보호 합니다. Silverlight에 대 한 원격 데이터에 액세스할 때 문제가 발생 하면 참조 [하는 서비스 사용 가능한 도메인 경계를 넘어](http://go.microsoft.com/fwlink/?LinkId=223276)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [SharePoint를 위한 웹 파트 만들기](../sharepoint/creating-web-parts-for-sharepoint.md)   
 [SharePoint 솔루션 패키지 배포, 게시 및 업그레이드](../sharepoint/deploying-publishing-and-upgrading-sharepoint-solution-packages.md)  
  
  
