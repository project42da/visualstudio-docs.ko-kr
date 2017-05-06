---
title: "Walkthrough: Profiling a SharePoint Application"
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
helpviewer_keywords: 
  - "SharePoint development in Visual Studio, profiling"
  - "performance testing [SharePoint development in Visual Studio]"
  - "SharePoint development in Visual Studio, performance testing"
  - "profiling [SharePoint development in Visual Studio]"
ms.assetid: 0b19d4b7-5fcc-42a2-b411-96eccd00137f
caps.latest.revision: 16
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 15
---
# Walkthrough: Profiling a SharePoint Application
  이 연습에서는 Visual Studio에서 프로파일링 도구를 사용하여 SharePoint 응용 프로그램의 성능을 최적화하는 방법을 보여 줍니다.  예제 응용 프로그램은 기능 이벤트 수신기의 성능을 저하시키는 유휴 루프가 포함된 SharePoint 기능 이벤트 수신기입니다.  Visual Studio 프로파일러를 사용하면 프로젝트의 가장 비용이 많이 드는\(성능이 가장 낮은\) 부분\(*과다 경로*라고도 함\)을 찾고 제거할 수 있습니다.  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   [기능 및 기능 이벤트 수신기 추가](#BKMK_AddFtrandFtrEvntReceiver)  
  
-   [SharePoint 응용 프로그램 구성 및 배포](#BKMK_ConfigSharePointApp)  
  
-   [SharePoint 응용 프로그램 실행](#BKMK_RunSPApp)  
  
-   [프로파일링 결과 확인 및 해석](#BKMK_ViewResults)  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## 사전 요구 사항  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   지원되는 Microsoft Windows 및 SharePoint 버전.  [!INCLUDE[crdefault](../sharepoint/includes/crdefault-md.md)] [SharePoint 솔루션 개발 요구 사항](../sharepoint/requirements-for-developing-sharepoint-solutions.md).  
  
-   [!INCLUDE[vs_dev11_long](../sharepoint/includes/vs-dev11-long-md.md)].  
  
## SharePoint 프로젝트 만들기  
 먼저 SharePoint 프로젝트를 만듭니다.  
  
#### SharePoint 프로젝트를 만들려면  
  
1.  메뉴 모음에서 **파일**, **새로 만들기**, **프로젝트**를 선택하여 **새 프로젝트** 대화 상자를 표시합니다.  
  
2.  **Visual C\#** 또는 **Visual Basic** 아래의 **SharePoint** 노드를 확장한 다음 **2010** 노드를 선택합니다.  
  
3.  템플릿 창에서 **SharePoint 2010 프로젝트** 템플릿을 선택합니다.  
  
4.  **이름** 상자에 ProfileTest를 입력한 다음 **확인** 단추를 선택합니다.  
  
     **SharePoint 사용자 지정 마법사**가 나타납니다.  
  
5.  **디버깅에 사용할 사이트 및 보안 수준 지정** 페이지에서 사이트 정의를 디버깅할 SharePoint 서버 사이트의 URL을 입력하거나 기본 위치\(http:\/\/*system name*\/\)를 사용합니다.  
  
6.  **이 SharePoint 솔루션의 신뢰 수준을 선택하십시오.** 섹션에서 **팜 솔루션으로 배포** 옵션 단추를 선택합니다.  
  
     현재 팜 솔루션만 프로파일링할 수 있습니다.  샌드박스 솔루션과 팜 솔루션 비교에 대한 자세한 내용은 [샌드박스가 적용된 솔루션 고려 사항](../sharepoint/sandboxed-solution-considerations.md)을 참조하세요.  
  
7.  **마침** 단추를 선택합니다.  프로젝트가 **솔루션 탐색기**에 표시됩니다.  
  
##  <a name="BKMK_AddFtrandFtrEvntReceiver"></a> 기능 및 기능 이벤트 수신기 추가  
 다음 작업으로, 기능의 이벤트 수신기와 함께 프로젝트에 기능을 추가합니다.  이 이벤트 수신기에는 프로파일링할 코드가 포함됩니다.  
  
#### 기능 및 기능 이벤트 수신기를 추가하려면  
  
1.  **솔루션 탐색기**에서 **기능** 노드의 바로 가기 메뉴를 열고 **기능 추가**를 선택한 다음 이름을 기본값 **Feature1**로 둡니다.  
  
2.  **솔루션 탐색기**에서 **Feature1**의 바로 가기 메뉴를 열고 **이벤트 수신기 추가**를 선택합니다.  
  
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
  
5.  `FeatureActivated` 프로시저 아래에 다음 프로시저를 추가합니다.  
  
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
  
6.  **솔루션 탐색기**에서 프로젝트\(**ProfileTest**\)의 바로 가기 메뉴를 열고 **속성**을 선택합니다.  
  
7.  **속성** 대화 상자에서 **SharePoint** 탭을 선택합니다.  
  
8.  **활성 배포 구성** 목록에서 **활성화 없음**을 선택합니다.  
  
     이 배포 구성을 선택하면 SharePoint에서 나중에 기능을 수동으로 활성화할 수 있습니다.  
  
9. 프로젝트를 저장합니다.  
  
##  <a name="BKMK_ConfigSharePointApp"></a> SharePoint 응용 프로그램 구성 및 배포  
 SharePoint 프로젝트가 준비되었으므로 이 프로젝트를 구성하고 SharePoint 서버에 배포합니다.  
  
#### SharePoint 응용 프로그램을 구성하고 배포하려면  
  
1.  **분석** 메뉴에서 **성능 마법사 시작**을 선택합니다.  
  
2.  **성능 마법사**의 첫 번째 페이지에서 프로파일링 방법을 **CPU 샘플링**으로 두고 **다음** 단추를 선택합니다.  
  
     다른 프로파일링 방법은 고급 프로파일링 상황에서 사용할 수 있습니다.  자세한 내용은 [프로파일링 방법 이해](../profiling/understanding-performance-collection-methods.md)를 참조하세요.  
  
3.  **성능 마법사**의 두 번째 페이지에서 프로필 대상을 **ProfileTest**로 두고 **다음** 단추를 선택합니다.  
  
     솔루션에 여러 프로젝트가 있는 경우 해당 프로젝트가 이 목록에 나타납니다.  
  
4.  **성능 마법사**의 세 번째 페이지에서 **계층 상호 작용 프로파일링 사용** 확인란을 선택 취소하고 **다음** 단추를 선택합니다.  
  
     TIP\(계층 상호 작용 프로파일링\) 기능은 데이터베이스를 쿼리하는 응용 프로그램의 성능을 측정하고 웹 페이지가 요청된 횟수를 표시하는 데 유용합니다.  해당 데이터가 이 예제에 필요하지 않기 때문에 이 기능을 사용하도록 설정하지 않을 것입니다.  
  
5.  **성능 마법사**의 네 번째 페이지에서 **마법사를 완료한 후 프로파일링을 시작합니다.** 확인란을 선택된 상태로 두고 **마침** 단추를 선택합니다.  
  
     마법사는 서버에서 응용 프로그램 프로파일링을 사용하도록 설정하고 **성능 탐색기** 창을 표시한 다음 SharePoint 응용 프로그램을 빌드, 배포 및 실행합니다.  
  
##  <a name="BKMK_RunSPApp"></a> SharePoint 응용 프로그램 실행  
 SharePoint에서 기능을 활성화하여 `FeatureActivation` 이벤트 코드가 실행되도록 합니다.  
  
#### SharePoint 응용 프로그램을 실행하려면  
  
1.  SharePoint에서 **사이트 작업** 메뉴를 연 다음 **사이트 설정**을 선택합니다.  
  
2.  **사이트 작업** 목록에서 **사이트 기능 관리** 링크를 선택합니다.  
  
3.  **기능** 목록에서 **ProfileTest Feature1** 옆에 있는 **활성화** 단추를 선택합니다.  
  
     유휴 루프가 `FeatureActivated` 함수에서 호출되기 때문에 이 작업을 수행할 때 일시 중지됩니다.  
  
4.  **빠른 실행** 모음에서 **목록**을 선택한 다음 **목록** 목록에서 **알림**을 선택합니다.  
  
     기능이 활성화되었다는 새 알림이 목록에 추가되었음을 확인합니다.  
  
5.  SharePoint 사이트를 닫습니다.  
  
     SharePoint를 닫은 후 프로파일러는 샘플 프로파일링 보고서를 만들고 표시한 다음 **ProfileTest** 프로젝트의 폴더에 .vsp 파일로 저장합니다.  
  
##  <a name="BKMK_ViewResults"></a> 프로파일링 결과 확인 및 해석  
 SharePoint 응용 프로그램을 실행하고 프로파일링했으므로 테스트 결과를 확인합니다.  
  
#### 프로파일링 결과를 확인하고 해석하려면  
  
1.  샘플 프로파일링 보고서의 **개별 작업이 가장 많은 함수** 섹션에서 `TimeCounter`가 목록 위쪽에 있음을 확인합니다.  
  
     이 위치는 `TimeCounter`가 샘플이 가장 많은 함수 중 하나이므로 응용 프로그램에서 가장 큰 성능 병목 지점 중 하나임을 나타냅니다.  그러나 이 상황은 예시 목적으로 그렇게 의도적으로 설계되었기 때문에 놀라운 것은 아닙니다.  
  
2.  **개별 작업이 가장 많은 함수** 섹션에서 `ProcessRequest` 링크를 선택하여 `ProcessRequest` 함수의 비용 분포를 표시합니다.  
  
     **함수**의 `ProcessRequest`호출된 섹션에서 **FeatureActiviated** 함수가 가장 비용이 많이 드는 호출된 함수로 나열됩니다.  
  
3.  **호출된 함수** 섹션에서 **FeatureActivated** 단추를 선택합니다.  
  
     **FeatureActivated**의 **호출된 함수** 섹션에서 `TimeCounter` 함수는 가장 비용이 많이 드는 호출된 함수로 나열됩니다.  **함수 코드 뷰** 창에서 강조 표시된 코드\(`TimeCounter`\)는 핫 스폿이며 수정이 필요한 위치를 나타냅니다.  
  
4.  샘플 프로파일링 보고서를 닫습니다.  
  
     보고서를 언제든지 다시 보려면 **성능 탐색기** 창에서 .vsp 파일을 엽니다.  
  
## 코드 수정 및 응용 프로그램 다시 프로파일링  
 SharePoint 응용 프로그램의 핫 스폿 함수가 식별되었으므로 해당 함수를 수정합니다.  
  
#### 코드를 수정하고 응용 프로그램을 다시 프로파일링하려면  
  
1.  기능 이벤트 수신기 코드의 `TimeCounter`에서 `FeatureActivated` 메서드 호출을 주석으로 처리하여 호출되지 않도록 합니다.  
  
2.  프로젝트를 저장합니다.  
  
3.  **성능 탐색기**에서 대상 폴더를 연 다음 **ProfileTest** 노드를 선택합니다.  
  
4.  **성능 탐색기** 도구 모음의 **작업** 탭에서 **프로파일링 시작** 단추를 선택합니다.  
  
     응용 프로그램을 다시 프로파일링하기 전에 프로파일링 속성을 변경하려면 **성능 마법사 시작** 단추를 대신 선택합니다.  
  
5.  이 항목의 앞부분에 있는 **SharePoint 응용 프로그램 실행** 단원의 지침을 따릅니다.  
  
     유휴 루프 호출이 제거되었으므로 기능이 훨씬 빠르게 활성화됩니다.  샘플 프로파일링 보고서는 이를 반영합니다.  
  
## 참고 항목  
 [프로파일링 도구 사용](../profiling/performance-explorer.md)   
 [프로파일링 도구 성능 세션 개요](../profiling/performance-session-overview.md)   
 [초보자를 위한 성능 프로파일링 지침](../profiling/beginners-guide-to-performance-profiling.md)   
 [Visual Studio 프로파일러를 사용한 응용 프로그램 병목 지점 찾기](http://go.microsoft.com/fwlink/?LinkID=137266)  
  
  