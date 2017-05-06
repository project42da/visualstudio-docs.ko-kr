---
title: "연습: IntelliTrace를 사용하여 SharePoint 응용 프로그램 디버깅"
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
  - "IntelliTrace[Visual Studio에서 SharePoint 개발]"
  - "독립 실행형 데이터 수집기"
  - "Visual Studio에서 SharePoint 개발, IntelliTrace"
  - "데이터 수집기"
  - "IntelliTrace"
ms.assetid: 4bd80d2f-f680-4bf4-81c3-f14e8185f6a4
caps.latest.revision: 27
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 26
---
# 연습: IntelliTrace를 사용하여 SharePoint 응용 프로그램 디버깅
  IntelliTrace를 사용하여 SharePoint 솔루션을 더 쉽게 디버깅할 수 있습니다.  일반적인 디버거에서는 현재 시점에서의 솔루션에 대한 스냅숏만 제공합니다.  그러나, IntelliTrace를 사용하여 솔루션에서 발생한 과거 이벤트와 해당 발생한 컨텍스트를 검토할 수 있으며 코드로 이동할 수 있습니다.  
  
 이 연습에서는 배포된 응용 프로그램에서 IntelliTrace 데이터를 수집하기 위해 Microsoft 모니터링 에이전트를 사용하여 Visual Studio Ultimate에서 SharePoint 2010 또는 SharePoint 2013 프로젝트를 디버깅하는 방법을 보여 줍니다.  데이터를 분석 하려면, Visual Studio Ultimate을 사용해야 합니다.  이 프로젝트는 기능이 활성화될 때 작업을 작업 목록에 추가하고 알림을 알림 목록에 추가하는 기능 수신기를 통합합니다.  기능이 비활성화되면 작업이 완료된 것으로 표시되고 두 번째 알림이 알림 목록에 추가됩니다.  그러나 이 절차에는 프로젝트가 올바르게 실행되지 못하게 하는 논리 오류가 포함되어 있습니다.  IntelliTrace를 사용하여 이 오류를 찾고 해결할 수 있습니다.  
  
 **적용:** 이 항목의 정보를 Visual Studio에서 만든 SharePoint 2010 및 SharePoint 2013에 적용합니다.  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   [기능 수신기 만들기](#BKMK_CreateReceiver)  
  
-   [기능 수신기에 코드 추가](#BKMK_AddCode)  
  
-   [프로젝트 테스트](#BKMK_Test1)  
  
-   [Microsoft 모니터링 에이전트를 사용하여 IntelliTrace 데이터 수집합니다.](#BKMK_CollectDiagnosticData)  
  
-   [SharePoint 솔루션 디버그 및 수정](#BKMK_DebugSolution)  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## 사전 요구 사항  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   지원되는 Windows 및 SharePoint 버전.  [SharePoint 솔루션 개발 요구 사항](../sharepoint/requirements-for-developing-sharepoint-solutions.md)를 참조하십시오.  
  
-   Visual Studio Ultimate  
  
##  <a name="BKMK_CreateReceiver"></a> 기능 수신기 만들기  
 먼저, 기능 수신기가 포함된 빈 SharePoint 프로젝트를 만듭니다.  
  
#### 기능 수신기를 만들려면  
  
1.  SharePoint 2010 또는 SharePoint 2013 솔루션 프로젝트를 만들고 이름을 IntelliTraceTest로 합니다.  
  
     프로젝트의 SharePoint 사이트와 솔루션의 신뢰 수준을 지정할 수 있는 **SharePoint 사용자 지정 마법사**가 나타납니다.  
  
2.  **팜 솔루션으로 배포** 옵션 단추를 선택한 다음 **완료** 단추를 선택합니다.  
  
     IntelliTrace는 팜 솔루션에서만 작동합니다.  
  
3.  **솔루션 탐색기**에서 **기능** 노드의 바로 가기 메뉴를 열고 **기능 추가**를 선택합니다.  
  
     Feature1.feature가 나타납니다.  
  
4.  Feature1.feature를 위한 바로 가기 메뉴를 열고 **이벤트 수신자 추가** 를 선택하여 기능에 코드 모듈을 추가 합니다.  
  
##  <a name="BKMK_AddCode"></a> 기능 수신기에 코드 추가  
 다음으로, 기능 수신기의 `FeatureActivated` 및 `FeatureDeactivating` 메서드에 코드를 추가합니다.  이러한 메서드는 기능이 SharePoint에서 활성화되거나 비활성화될 때마다 각각 트리거됩니다.  
  
#### 기능 수신기에 코드를 추가하려면  
  
1.  `Feature1EventReceiver` 클래스의 맨 위에서, 다음 코드를 추가하여 SharePoint 사이트 및 하위 사이트를 지정하는 변수를 선언합니다.  
  
    ```vb  
    ' SharePoint site and subsite.  
    Private siteUrl As String = "http://localhost"  
    Private webUrl As String = "/"  
    ```  
  
    ```csharp  
    // SharePoint site and subsite.  
    private string siteUrl = "http://localhost";  
    private string webUrl = "/";  
    ```  
  
2.  `FeatureActivated` 메서드를 다음 코드로 바꿉니다.  
  
    ```vb  
    Public Overrides Sub FeatureActivated(ByVal properties As SPFeatureReceiverProperties)  
        Try  
            Using site As New SPSite(siteUrl)  
                Using web As SPWeb = site.OpenWeb(webUrl)  
                    ' Reference the lists.  
                    Dim announcementsList As SPList = web.Lists("Announcements")  
                    Dim taskList As SPList = web.Lists("Tasks")  
  
                    ' Add an announcement to the Announcements list.  
                    Dim listItem As SPListItem = announcementsList.Items.Add()  
                    listItem("Title") = "Activated Feature: " & Convert.ToString(properties.Definition.DisplayName)  
                    listItem("Body") = Convert.ToString(properties.Definition.DisplayName) & " was activated on: " & DateTime.Now.ToString()  
                    listItem.Update()  
  
                    ' Add a task to the Task list.  
                    Dim newTask As SPListItem = taskList.Items.Add()  
                    newTask("Title") = "Deactivate feature: " & Convert.ToString(properties.Definition.DisplayName)  
                    newTask.Update()  
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
                    SPList taskList = web.Lists["Tasks"];  
  
                    // Add an announcement to the Announcements list.  
                    SPListItem listItem = announcementsList.Items.Add();  
                    listItem["Title"] = "Activated Feature: " + properties.Definition.DisplayName;  
                    listItem["Body"] = properties.Definition.DisplayName + " was activated on: " + DateTime.Now.ToString();  
                    listItem.Update();  
  
                    // Add a task to the Task list.  
                    SPListItem newTask = taskList.Items.Add();  
                    newTask["Title"] = "Deactivate feature: " + properties.Definition.DisplayName;  
                    newTask.Update();  
                }  
            }  
        }  
  
        catch (Exception e)  
        {  
            Console.WriteLine("Error: " + e.ToString());  
        }  
  
    }  
    ```  
  
3.  `FeatureDeactivating` 메서드를 다음 코드로 바꿉니다.  
  
    ```vb  
    Public Overrides Sub FeatureDeactivating(ByVal properties As SPFeatureReceiverProperties)  
        ' The following line induces an error to demonstrate debugging.  
        ' Remove this line later for proper operation.  
        Throw New System.InvalidOperationException("Serious error occurred!")  
        Try  
            Using site As New SPSite(siteUrl)  
                Using web As SPWeb = site.OpenWeb(webUrl)  
                    ' Reference the lists.  
                    Dim taskList As SPList = web.Lists("Tasks")  
                    Dim announcementsList As SPList = web.Lists("Announcements")  
  
                    ' Add an announcement that the feature was deactivated.  
                    Dim listItem As SPListItem = announcementsList.Items.Add()  
                    listItem("Title") = "Deactivated Feature: " & Convert.ToString(properties.Definition.DisplayName)  
                    listItem("Body") = Convert.ToString(properties.Definition.DisplayName) & " was deactivated on: " & DateTime.Now.ToString()  
                    listItem.Update()  
  
                    ' Find the task that the feature receiver added to the Task list when the  
                    ' feature was activated.  
                    Dim qry As New SPQuery()  
                    qry.Query = "<Where><Contains><FieldRef Name='Title' /><Value Type='Text'>Deactivate</Value></Contains></Where>"  
                    Dim taskItems As SPListItemCollection = taskList.GetItems(qry)  
  
                    For Each taskItem As SPListItem In taskItems  
                        ' Mark the task as complete.  
                        taskItem("PercentComplete") = 1  
                        taskItem("Status") = "Completed"  
                        taskItem.Update()  
                    Next  
                End Using  
  
            End Using  
  
        Catch e As Exception  
            Console.WriteLine("Error: " & e.ToString())  
        End Try  
  
    End Sub  
    ```  
  
    ```csharp  
    public override void FeatureDeactivating(SPFeatureReceiverProperties properties)  
    {  
        // The following line induces an error to demonstrate debugging.  
        // Remove this line later for proper operation.  
        throw new System.InvalidOperationException("A serious error occurred!");   
        try  
        {  
            using (SPSite site = new SPSite(siteUrl))  
            {  
                using (SPWeb web = site.OpenWeb(webUrl))  
                {  
                    // Reference the lists.  
                    SPList taskList = web.Lists["Tasks"];  
                    SPList announcementsList = web.Lists["Announcements"];  
  
                    // Add an announcement that the feature was deactivated.  
                    SPListItem listItem = announcementsList.Items.Add();  
                    listItem["Title"] = "Deactivated Feature: " + properties.Definition.DisplayName;  
                    listItem["Body"] = properties.Definition.DisplayName + " was deactivated on: " + DateTime.Now.ToString();  
                    listItem.Update();  
  
                    // Find the task that the feature receiver added to the Task list when the  
                    // feature was activated.  
                    SPQuery qry = new SPQuery();  
                    qry.Query = "<Where><Contains><FieldRef Name='Title' /><Value Type='Text'>Deactivate</Value></Contains></Where>";  
                    SPListItemCollection taskItems = taskList.GetItems(qry);  
  
                    foreach (SPListItem taskItem in taskItems)  
                    {  
                        // Mark the task as complete.  
                        taskItem["PercentComplete"] = 1;  
                        taskItem["Status"] = "Completed";  
                        taskItem.Update();  
                    }  
                }  
            }  
  
        }  
  
        catch (Exception e)  
        {  
            Console.WriteLine("Error: " + e.ToString());  
        }  
    }  
    ```  
  
##  <a name="BKMK_Test1"></a> 프로젝트 테스트  
 기능 수신기에 코드를 추가하고 데이터 수집기를 실행했으므로 SharePoint 솔루션이 제대로 작동 하는지 테스트하기 위해 표시하고 실행 합니다.  
  
> [!IMPORTANT]  
>  이 예제에서는 FeatureDeactivating 이벤트 처리기에서 오류가 throw 됩니다.  이 연습의 뒷부분에서 데이터 수집기가 생성한 .iTrace 파일을 사용하여 이 오류를 찾습니다.  
  
#### 프로젝트를 테스트하려면  
  
1.  SharePoint에 솔루션을 배포하고 브라우저에서 SharePoint 사이트를 엽니다.  
  
     배포 시 기능이 자동으로 활성화되어 기능 수신기가 알림과 작업을 추가합니다.  
  
2.  공지 사항 및 작업 목록의 내용을 표시합니다.  
  
     알림 목록은 **활성화된 기능: IntelliTraceTest\_Feature1**이라는 새 알림을 추가해야 하고 **기능 비활성화: IntelliTraceTest\_Feature1**이라는 이름의 새 작업을 작업 목록에 추가합니다.  이들 항목 중 하나가 없는 경우, 기능이 활성화되어 있는지 여부를 확인합니다.  정품 인증이 되지 않으면, 활성화 합니다.  
  
3.  다음 단계를 수행하여 기능을 비활성화 합니다.  
  
    1.  SharePoint의 **사이트 활성화** 메뉴에서, **사이트 설정**을 선택합니다.  
  
    2.  **사이트 작업**에서, **사이트 기능 관리** 링크를 선택합니다.  
  
    3.  **IntelliTraceTest Feature1**옆에, **비활성화** 단추를 선택합니다.  
  
    4.  경고 페이지에서 **이 기능 비활성화** 링크를 선택합니다.  
  
     FeatureDeactivating\(\) 이벤트 처리기는 오류를 throw 합니다.  
  
##  <a name="BKMK_CollectDiagnosticData"></a> Microsoft 모니터링 에이전트를 사용하여 IntelliTrace 데이터 수집합니다.  
 SharePoint를 실행하는 시스템에 Microsoft 모니터링 에이전트를 설치 하는 경우, IntelliTrace를 반환하는 일반 정보를 보다 구체적인 데이터를 사용하여 SharePoint 솔루션을 디버깅할 수 있습니다.  SharePoint 솔루션이 실행되는 동안 에이전트는 디버그 정보를 확인하기 위한 PowerShell cmdlet을 사용하여 Visual Studio 외부에서 작동합니다.  
  
> [!NOTE]  
>  이 섹션의 구성 정보는이 예제입니다.  다른 구성 옵션에 대한 자세한 내용은 [IntelliTrace 독립 실행형 수집기 사용](../debugger/using-the-intellitrace-stand-alone-collector.md)을 참조하십시오.  
  
1.  SharePoint에서 실행 되는 컴퓨터에서, [Microsoft 모니터링 에이전트를 설정하고 솔루션을 모니터링 시작](../debugger/using-the-intellitrace-stand-alone-collector.md)을 합니다.  
  
2.  기능을 비활성화 합니다.  
  
    1.  SharePoint의 **사이트 활성화** 메뉴에서, **사이트 설정**을 선택합니다.  
  
    2.  **사이트 작업**에서, **사이트 기능 관리** 링크를 선택합니다.  
  
    3.  **IntelliTraceTest Feature1**옆에, **비활성화** 단추를 선택합니다.  
  
    4.  경고 페이지에서 **이 기능 비활성화** 링크를 선택합니다.  
  
     \(이 경우, FeatureDeactivating\(\) 이벤트 처리기에서 throw 되는 오류\)으로 인해 오류가 발생합니다.  
  
3.  PowerShell 창에서, [Stop WebApplicationMonitoring](http://go.microsoft.com/fwlink/?LinkID=313687) 명령을 실행하여 .iTrace 파일을 생성, 모니터링 중지, SharePoint 솔루션을 다시 시작합니다.  
  
     **Stop\-WebApplicationMonitoring**  *"\<SharePointSite\>\\\<SharePointAppName\>"*  
  
##  <a name="BKMK_DebugSolution"></a> SharePoint 솔루션 디버그 및 수정  
 이제 Visual Studio에서 IntelliTrace 로그 파일 을 보고 SharePoint 솔루션에서이 오류를 찾고 수정할 수 있습니다.  
  
#### SharePoint 솔루션을 디버그 및 수정하려면  
  
1.  \\IntelliTraceLogs 폴더에서 Visual Studio의 .iTrace 파일을 엽니다.  
  
     **IntelliTrace 요약** 페이지가 나타납니다.  오류가 처리되지 않았기 때문에, **분석** 섹션의 처리되지 않은 예외 영역에서 SharePoint 상관 관계 ID \(GUID\)가 나타납니다.  오류가 발생한 곳에 호출 스택을 표시하려면 **호출 스택** 단추를 선택합니다.  
  
2.  **디버그 예외** 단추를 선택합니다.  
  
     메시지가 표시되면 기호 파일을 로드합니다.  **IntelliTrace** 창에서, 예외 표시 창에 "throw 됨: 심각한 오류가 발생 했습니다\!"가 강조됩니다.  
  
     IntelliTrace 창에서, 실패 한 코드를 표시하려면 예외를 선택합니다.  
  
3.  SharePoint 솔루션 열기 및 다음 주석 처리를 하거나 FeatureDeactivating\(\) 프로시저의 맨 위 에서 **throw** 명령문을 제거하여 오류를 수정합니다.  
  
4.  Visual Studio 솔루션을 다시 빌드하고 다음 SharePoint에 다시 배포합니다.  
  
5.  다음 단계를 수행하여 기능을 비활성화 합니다.  
  
    1.  SharePoint의 **사이트 활성화** 메뉴에서, **사이트 설정**을 선택합니다.  
  
    2.  **사이트 작업**에서, **사이트 기능 관리** 링크를 선택합니다.  
  
    3.  **IntelliTraceTest Feature1**옆에, **비활성화** 단추를 선택합니다.  
  
    4.  경고 페이지에서 **이 기능 비활성화** 링크를 선택합니다.  
  
6.  작업 목록을 열고 Deactivate 작업의 **상태** 값이 이제 "완료"로 올바르게 설정되어 있고 이 작업의 **완료율** 값이 100%인 것을 확인합니다.  
  
     코드는 이제 제대로 실행됩니다.  
  
## 참고 항목  
 [SharePoint 코드 확인 및 디버깅](../sharepoint/verifying-and-debugging-sharepoint-code.md)   
 [IntelliTrace 사용](../debugger/intellitrace.md)   
 [연습: 단위 테스트를 사용하여 SharePoint 코드 확인](http://msdn.microsoft.com/ko-kr/3d2c4aaf-3cb5-4825-b21b-f10222abe818)  
  
  