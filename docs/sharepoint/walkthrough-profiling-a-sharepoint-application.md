---
title: "연습: SharePoint 응용 프로그램 프로 파일링 | Microsoft Docs"
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
helpviewer_keywords:
- SharePoint development in Visual Studio, profiling
- performance testing [SharePoint development in Visual Studio]
- SharePoint development in Visual Studio, performance testing
- profiling [SharePoint development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 91952e2f10f025568d356149f63bff63e0c0b1fc
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="walkthrough-profiling-a-sharepoint-application"></a>연습: SharePoint 응용 프로그램 프로파일링
  이 연습에서는 Visual Studio에서 프로파일링 도구를 사용하여 SharePoint 응용 프로그램의 성능을 최적화하는 방법을 보여 줍니다. 예제 응용 프로그램은 기능 이벤트 수신기의 성능을 저하시키는 유휴 루프가 포함된 SharePoint 기능 이벤트 수신기입니다. Visual Studio 프로파일러를 사용 하면을 찾고, 프로젝트의 가장 비용이 많이 드는 (성능이 가장 낮은) 부분을 라고도 제거할는 *실행 부하 과다 경로*합니다.  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   [기능 및 기능 이벤트 수신기 추가](#BKMK_AddFtrandFtrEvntReceiver)합니다.  
  
-   [구성 및 SharePoint 응용 프로그램 배포](#BKMK_ConfigSharePointApp)합니다.  
  
-   [SharePoint 응용 프로그램을 실행](#BKMK_RunSPApp)합니다.  
  
-   [확인 및 프로 파일링 결과 해석](#BKMK_ViewResults)합니다.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>필수 구성 요소  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   지원되는 Microsoft Windows 및 SharePoint 버전. [!INCLUDE[crdefault](../sharepoint/includes/crdefault-md.md)][SharePoint 솔루션 개발을 위한 요구 사항](../sharepoint/requirements-for-developing-sharepoint-solutions.md)합니다.  
  
-   [!INCLUDE[vs_dev11_long](../sharepoint/includes/vs-dev11-long-md.md)].  
  
## <a name="creating-a-sharepoint-project"></a>SharePoint 프로젝트 만들기  
 먼저 SharePoint 프로젝트를 만듭니다.  
  
#### <a name="to-create-a-sharepoint-project"></a>SharePoint 프로젝트를 만들려면  
  
1.  메뉴 모음에서 **파일**, **새로**, **프로젝트** 표시 하는 **새 프로젝트** 대화 상자.  
  
2.  확장 하 고는 **SharePoint** 노드 아래의 **Visual C#** 또는 **Visual Basic**를 선택한 후는 **2010** 노드.  
  
3.  템플릿 창에서 선택 된 **SharePoint 2010 프로젝트** 템플릿.  
  
4.  에 **이름** 상자에 입력 **ProfileTest**, 선택한 후는 **확인** 단추입니다.  
  
     **SharePoint 사용자 지정 마법사** 나타납니다.  
  
5.  에 **디버깅에 대 한 사이트 및 보안 수준을 지정** 페이지, 사이트 정의 디버깅 하려는 SharePoint 서버 사이트에 대 한 URL을 입력 하거나 기본 위치를 사용 하 여 (http://*시스템 이름*/) .  
  
6.  에 **이 SharePoint 솔루션에 대 한 신뢰 수준을?** 섹션에서 선택 된 **팜 솔루션으로 배포** 옵션 단추입니다.  
  
     현재 팜 솔루션만 프로파일링할 수 있습니다. 샌드박스 솔루션과 팜 솔루션 비교에 대 한 자세한 내용은 참조 [샌드박스 솔루션 고려 사항](../sharepoint/sandboxed-solution-considerations.md)합니다.  
  
7.  선택 된 **마침** 단추입니다. 에 프로젝트가 표시 **솔루션 탐색기**합니다.  
  
##  <a name="BKMK_AddFtrandFtrEvntReceiver"></a>기능 및 기능 이벤트 수신기 추가  
 다음 작업으로, 기능의 이벤트 수신기와 함께 프로젝트에 기능을 추가합니다. 이 이벤트 수신기에는 프로파일링할 코드가 포함됩니다.  
  
#### <a name="to-add-a-feature-and-feature-event-receiver"></a>기능 및 기능 이벤트 수신기를 추가하려면  
  
1.  **솔루션 탐색기**에 대 한 바로 가기 메뉴를 열고는 **기능** 노드를 선택 **기능 추가**, 이름 값을 기본값으로 유지 하 고 **Feature1**.  
  
2.  **솔루션 탐색기**, 바로 가기 메뉴를 열고 **Feature1**를 선택한 후 **이벤트 수신기 추가**합니다.  
  
     주석 처리된 몇 가지 이벤트 처리기가 포함된 코드 파일이 기능에 추가되고 편집할 수 있도록 열립니다.  
  
3.  이벤트 수신기 클래스에서 다음 변수 선언을 추가합니다.  
  
    ```vb  
    ' SharePoint site/subsite.  
    Private siteUrl As String = "http://localhost"  
    Private webUrl As String = "/"  
    ```  
  
    ```csharp  
    // SharePoint site/subsite.  
    private string siteUrl = "http://localhost";  
    private string webUrl = "/";  
    ```  
  
4.  `FeatureActivated` 프로시저를 다음 코드로 바꿉니다.  
  
    ```vb  
    Public Overrides Sub FeatureActivated(properties As SPFeatureReceiverProperties)  
        Try  
            Using site As New SPSite(siteUrl)  
                Using web As SPWeb = site.OpenWeb(webUrl)  
                    ' Reference the lists.  
                    Dim announcementsList As SPList = web.Lists("Announcements")  
  
                    ' Add a new announcement to the Announcements list.  
                    Dim listItem As SPListItem = announcementsList.Items.Add()  
                    listItem("Title") = "Activated Feature: " & Convert.ToString(properties.Definition.DisplayName)  
                    listItem("Body") = Convert.ToString(properties.Definition.DisplayName) & " was activated on: " & DateTime.Now.ToString()  
                    ' Waste some time.  
                    TimeCounter()  
                    ' Update the list.  
                    listItem.Update()  
                End Using  
            End Using  
  
        Catch e As Exception  
            Console.WriteLine("Error: " & e.ToString())  
        End Try  
    End Sub  
    ```  
  
    ```csharp  
    public override void FeatureActivated(SPFeatureReceiverProperties properties)  
    {  
        try  
        {  
            using (SPSite site = new SPSite(siteUrl))  
            {  
                using (SPWeb web = site.OpenWeb(webUrl))  
                {  
                    // Reference the lists.  
                    SPList announcementsList = web.Lists["Announcements"];  
  
                    // Add a new announcement to the Announcements list.  
                    SPListItem listItem = announcementsList.Items.Add();  
                    listItem["Title"] = "Activated Feature: " + properties.Definition.DisplayName;  
                    listItem["Body"] = properties.Definition.DisplayName + " was activated on: " +   
    DateTime.Now.ToString();  
                    // Waste some time.  
                    TimeCounter();  
                    // Update the list.  
                    listItem.Update();                          
                }  
            }  
        }  
  
        catch (Exception e)  
        {  
            Console.WriteLine("Error: " + e.ToString());  
        }  
    }  
    ```  
  
5.  다음 절차 아래 추가 `FeatureActivated`프로시저입니다.  
  
    ```vb  
  
    Public Sub TimeCounter()  
        Dim result As Integer  
        For i As Integer = 0 To 99999  
            For j As Integer = 0 To 9999  
                result = i * j  
            Next j  
        Next i  
    End Sub  
    ```  
  
    ```csharp  
    public void TimeCounter()  
    {  
        for (int i = 0; i < 100000; i++)  
        {  
            for (int j = 0; j < 10000; j++)  
            {  
                int result = i * j;  
            }  
        }  
    }  
    ```  
  
6.  **솔루션 탐색기**, 프로젝트에 대 한 바로 가기 메뉴를 열고 (**ProfileTest**)를 선택한 후 **속성**합니다.  
  
7.  에 **속성** 대화 상자에서 선택 하는 **SharePoint** 탭 합니다.  
  
8.  에 **활성 배포 구성** 목록에서 선택 **활성화 없음**합니다.  
  
     이 배포 구성을 선택하면 SharePoint에서 나중에 기능을 수동으로 활성화할 수 있습니다.  
  
9. 프로젝트를 저장합니다.  
  
##  <a name="BKMK_ConfigSharePointApp"></a>구성 및 SharePoint 응용 프로그램 배포  
 SharePoint 프로젝트가 준비되었으므로 이 프로젝트를 구성하고 SharePoint 서버에 배포합니다.  
  
#### <a name="to-configure-and-deploy-the-sharepoint-application"></a>SharePoint 응용 프로그램을 구성하고 배포하려면  
  
1.  에 **분석** 메뉴 선택 **성능 마법사 시작**합니다.  
  
2.  첫 번째 페이지는 **성능 마법사**,으로 프로 파일링 방법을 둡니다 **CPU 샘플링** 선택 하 고는 **다음** 단추입니다.  
  
     다른 프로파일링 방법은 고급 프로파일링 상황에서 사용할 수 있습니다. 자세한 내용은 [성능 컬렉션 메서드 이해](/visualstudio/profiling/understanding-performance-collection-methods)를 참조하세요.  
  
3.  두 개의 페이지는 **성능 마법사**, 프로필 대상으로 유지 **ProfileTest** 선택 하 고는 **다음** 단추입니다.  
  
     솔루션에 여러 프로젝트가 있는 경우 해당 프로젝트가 이 목록에 나타납니다.  
  
4.  세 번째 페이지는 **성능 마법사**선택을 취소는 **계층 상호 작용 프로 파일링** 확인란을 선택한 후는 **다음** 단추입니다.  
  
     TIP(계층 상호 작용 프로파일링) 기능은 데이터베이스를 쿼리하는 응용 프로그램의 성능을 측정하고 웹 페이지가 요청된 횟수를 표시하는 데 유용합니다. 해당 데이터가 이 예제에 필요하지 않기 때문에 이 기능을 사용하도록 설정하지 않을 것입니다.  
  
5.  네 번째 페이지는 **성능 마법사**, 둡니다는 **마법사를 완료 한 후 프로 파일링 시작** 확인란을 선택 하 고 선택 합니다는 **마침** 단추입니다.  
  
     마법사 응용 프로그램 서버에 프로 파일링, 표시 된 **성능 탐색기** 창을 닫은 후 빌드, 배포 및 SharePoint 응용 프로그램을 실행 합니다.  
  
##  <a name="BKMK_RunSPApp"></a>SharePoint 응용 프로그램 실행  
 SharePoint에서 기능을 활성화하여 `FeatureActivation` 이벤트 코드가 실행되도록 합니다.  
  
#### <a name="to-run-the-sharepoint-application"></a>SharePoint 응용 프로그램을 실행하려면  
  
1.  Sharepoint에서 열고는 **사이트 작업** 메뉴를 선택한 후 **사이트 설정**합니다.  
  
2.  에 **사이트 작업** 목록에서 선택 된 **사이트 기능 관리** 링크 합니다.  
  
3.  에 **기능** 목록에서 선택 된 **Activate** 단추 옆에 **ProfileTest Feature1**합니다.  
  
     유휴 루프가 `FeatureActivated` 함수에서 호출되기 때문에 이 작업을 수행할 때 일시 중지됩니다.  
  
4.  에 **빠른 실행** 막대에서 **나열** 한 다음는 **나열** 목록에서 선택 **공지**합니다.  
  
     기능이 활성화되었다는 새 알림이 목록에 추가되었음을 확인합니다.  
  
5.  SharePoint 사이트를 닫습니다.  
  
     SharePoint를 닫은 후 프로파일러 및 샘플 프로 파일링 보고서를 표시 만들고에.vsp 파일로 저장 된 **ProfileTest** 프로젝트의 폴더입니다.  
  
##  <a name="BKMK_ViewResults"></a>확인 및 프로 파일링 결과 해석  
 SharePoint 응용 프로그램을 실행하고 프로파일링했으므로 테스트 결과를 확인합니다.  
  
#### <a name="to-view-and-interpret-the-profiling-results"></a>프로파일링 결과를 확인하고 해석하려면  
  
1.  에 **함수 목록의 개별 작업이 가장 많은** 섹션 샘플 프로 파일링 보고서의 알 수 있듯이 `TimeCounter` 목록의 위쪽에 있습니다.  
  
     이 위치는 `TimeCounter`가 샘플이 가장 많은 함수 중 하나이므로 응용 프로그램에서 가장 큰 성능 병목 지점 중 하나임을 나타냅니다. 그러나 이 상황은 예시 목적으로 그렇게 의도적으로 설계되었기 때문에 놀라운 것은 아닙니다.  
  
2.  에 **함수 목록의 개별 작업이 가장 많은** 섹션에서 `ProcessRequest` 링크에 대 한 비용 분포를 표시 하는 `ProcessRequest` 함수입니다.  
  
     에 **함수 라고** 섹션 `ProcessRequest`, 다음에 유의 **FeatureActiviated** 함수가 나열 되어 가장 비용이 많이 드는 함수를 호출 합니다.  
  
3.  에 **함수 라고** 섹션에서 선택 된 **FeatureActivated** 단추 합니다.  
  
     에 **함수 라고** 섹션 **FeatureActivated**, `TimeCounter` 함수가 나열 되어 가장 비용이 많이 드는 함수를 호출 합니다. 에 **함수 코드 뷰** 창, 강조 표시 된 코드 (`TimeCounter`) 핫 스폿 이며 수정이 필요한 위치를 나타냅니다.  
  
4.  샘플 프로파일링 보고서를 닫습니다.  
  
     언제 든 지 다시 보려면 보고서를 열고.vsp 파일에는 **성능 탐색기** 창.  
  
## <a name="fixing-the-code-and-reprofiling-the-application"></a>코드 수정 및 응용 프로그램 다시 프로파일링  
 SharePoint 응용 프로그램의 핫 스폿 함수가 식별되었으므로 해당 함수를 수정합니다.  
  
#### <a name="to-fix-the-code-and-reprofile-the-application"></a>코드를 수정하고 응용 프로그램을 다시 프로파일링하려면  
  
1.  기능 이벤트 수신기 코드의 `TimeCounter`에서 `FeatureActivated` 메서드 호출을 주석으로 처리하여 호출되지 않도록 합니다.  
  
2.  프로젝트를 저장합니다.  
  
3.  **성능 탐색기**대상 폴더를 연 다음 선택에서 **ProfileTest** 노드.  
  
4.  에 **성능 탐색기** 도구 모음에는 **동작** 탭을 선택는 **프로 파일링 시작** 단추입니다.  
  
     응용 프로그램을 다시 프로 파일링 하기 전에 프로 파일링 속성 변경, 선택 하려는 경우는 **성능 마법사 시작** 단추를 대신 합니다.  
  
5.  지침에 따라는 **SharePoint 응용 프로그램을 실행** 이전에이 항목의 섹션입니다.  
  
     유휴 루프 호출이 제거되었으므로 기능이 훨씬 빠르게 활성화됩니다. 샘플 프로파일링 보고서는 이를 반영합니다.  
  
## <a name="see-also"></a>참고 항목  
 [성능 탐색기](/visualstudio/profiling/performance-explorer)   
 [성능 세션 개요](/visualstudio/profiling/performance-session-overview)   
 [초보자를 위한 성능 프로파일링 지침](/visualstudio/profiling/beginners-guide-to-performance-profiling)   
 [Visual Studio 프로파일러를 사용한 응용 프로그램 병목 지점 찾기](http://go.microsoft.com/fwlink/?LinkID=137266)  
  
  