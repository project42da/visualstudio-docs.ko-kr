---
title: "연습: IntelliTrace를 사용 하 여 SharePoint 응용 프로그램을 디버깅 | Microsoft Docs"
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
- IntelliTrace [SharePoint development in Visual Studio]
- standalone data collector
- SharePoint development in Visual Studio, IntelliTrace
- data collector
- IntelliTrace
ms.assetid: 4bd80d2f-f680-4bf4-81c3-f14e8185f6a4
caps.latest.revision: "27"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 34ee1ca7d62a661f915edba1adc22c18f90256b6
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-debugging-a-sharepoint-application-by-using-intellitrace"></a>연습: IntelliTrace를 사용하여 SharePoint 응용 프로그램 디버깅
  IntelliTrace를 사용 하 여 SharePoint 솔루션을 보다 쉽게 디버깅할 수 있습니다. 기존 디버거는 현재 시점에서 스냅숏을 솔루션을 제공합니다. 그러나 솔루션에서 발생 한 이전 이벤트와 발생 했으며 코드를 탐색 하는 컨텍스트를 검토 하려면 IntelliTrace를 사용할 수 있습니다.  
  
 이 연습에는 Microsoft Monitoring Agent를 사용 하 여 배포 된 응용 프로그램에서 IntelliTrace 데이터를 수집 하 여 Visual Studio Ultimate에서 SharePoint 2010 또는 SharePoint 2013 프로젝트를 디버깅 하는 방법을 보여 줍니다. 해당 데이터를 분석 하기 위해 Visual Studio Ultimate 사용 해야 합니다. 이 프로젝트는 기능이 활성화 된 경우 작업 목록 및 알림 목록에 대 한 공지에 작업을 추가 하는 기능 수신기를 통합 합니다. 이 기능이 비활성화 되 면 task는 완료 됨으로 표시 되 고 두 번째 알림이 알림 목록에 추가 됩니다. 그러나 프로시저 프로젝트 올바르게 실행 되지 않는 논리적 오류를 포함 합니다. IntelliTrace를 사용 하 여 찾은 하 고 오류를 수정 합니다.  
  
 **적용 대상:** 이 항목의 정보는 Visual Studio에서 생성 된 SharePoint 2010 및 SharePoint 2013 솔루션에 적용 됩니다.  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   [기능 수신기 만들기](#BKMK_CreateReceiver)  
  
-   [기능 수신기에 코드 추가](#BKMK_AddCode)  
  
-   [프로젝트 테스트](#BKMK_Test1)  
  
-   [Microsoft Monitoring Agent를 사용 하 여 IntelliTrace 데이터 수집](#BKMK_CollectDiagnosticData)  
  
-   [디버깅 하 고 SharePoint 솔루션을 수정 합니다.](#BKMK_DebugSolution)  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>필수 구성 요소  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   Windows 및 SharePoint 버전의 지원. 참조 [SharePoint 솔루션 개발을 위한 요구 사항](../sharepoint/requirements-for-developing-sharepoint-solutions.md)합니다.  
  
-   Visual Studio Ultimate 합니다.  
  
##  <a name="BKMK_CreateReceiver"></a>기능 수신기 만들기  
 첫째, 기능 수신기가 빈 SharePoint 프로젝트를 만듭니다.  
  
#### <a name="to-create-a-feature-receiver"></a>기능 수신기를 만들려면  
  
1.  SharePoint 2010 또는 SharePoint 2013 솔루션 프로젝트를 만들고 이름을 **IntelliTraceTest**합니다.  
  
     **SharePoint 사용자 지정 마법사** 프로젝트 및 솔루션의 신뢰 수준에 대 한 SharePoint 사이트를 지정할 수 있는 나타납니다.  
  
2.  선택 된 **팜 솔루션으로 배포** 옵션 단추를 선택한 후는 **마침** 단추입니다.  
  
     IntelliTrace는 팜 솔루션 에서만 작동 합니다.  
  
3.  **솔루션 탐색기**에 대 한 바로 가기 메뉴를 열고는 **기능** 노드를 선택한 후 **기능 추가**합니다.  
  
     Feature1.feature 나타납니다.  
  
4.  Feature1.feature를에 대 한 바로 가기 메뉴를 연 다음 선택 **이벤트 수신기 추가** 기능에 코드 모듈을 추가 합니다.  
  
##  <a name="BKMK_AddCode"></a>기능 수신기에 코드 추가  
 기능 수신기에서 두 개의 메서드를 다음으로 코드를 추가: `FeatureActivated` 및 `FeatureDeactivating`합니다. 이러한 메서드는 기능을 활성화 또는 비활성화 되어 있는 SharePoint 각각 때마다 트리거됩니다.  
  
#### <a name="to-add-code-to-the-feature-receiver"></a>기능 수신기에 코드를 추가 하려면  
  
1.  맨 위에 있는 `Feature1EventReceiver` 클래스, SharePoint 사이트와 하위 사이트를 지정 하는 변수를 선언 하는 다음 코드를 추가 합니다.  
  
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
  
##  <a name="BKMK_Test1"></a>프로젝트 테스트  
 기능 수신기에는 코드가 추가 하 고 데이터 수집기가 실행 되 고, 배포 하 고 올바르게 작동 하는지 여부를 테스트 하려면 SharePoint 솔루션을 실행 합니다.  
  
> [!IMPORTANT]  
>  예를 들어 FeatureDeactivating 이벤트 처리기에서 오류가 throw 됩니다. 이 연습의 뒷부분에서 생성 하는 데이터 수집기는.iTrace 파일을 사용 하 여이 오류를 찾습니다.  
  
#### <a name="to-test-the-project"></a>프로젝트를 테스트하려면  
  
1.  SharePoint에 솔루션을 배포 하 고 브라우저에서 SharePoint 사이트를 엽니다.  
  
     기능이 자동으로 활성화 되어 알림 및 작업을 추가 하려면 기능 수신기입니다.  
  
2.  공지 사항 및 작업 목록의 내용을 표시 합니다.  
  
     알림 목록을 라는 새 알림이 있어야 **Activated 기능: IntelliTraceTest_Feature1**, 하며, 작업 목록 이라고 하는 새 작업 **Deactivate 기능: IntelliTraceTest_ Feature1**합니다. 이들이 항목 중 하나가 없거나 기능이 활성화 되어 있는지 여부를 확인 합니다. 를 활성화 하지 활성화 수 있습니다.  
  
3.  다음 단계를 수행 하 여 기능을 비활성화 합니다.  
  
    1.  에 **사이트 작업** sharepoint에서 메뉴 선택 **사이트 설정**합니다.  
  
    2.  아래 **사이트 작업**, 선택는 **사이트 기능 관리** 링크 합니다.  
  
    3.  옆에 **IntelliTraceTest Feature1**, 선택는 **비활성화** 단추입니다.  
  
    4.  경고 페이지에서 선택 된 **이 기능을 비활성화** 링크 합니다.  
  
     FeatureDeactivating() 이벤트 처리기에서 오류가 발생 합니다.  
  
##  <a name="BKMK_CollectDiagnosticData"></a>Microsoft Monitoring Agent를 사용 하 여 IntelliTrace 데이터 수집  
 SharePoint를 실행 하는 시스템에서 Microsoft Monitoring Agent를 설치 하는 경우에 IntelliTrace 반환 하는 일반 정보는 보다 구체적인 데이터를 사용 하 여 SharePoint 솔루션을 디버깅할 수 있습니다. 에이전트는 프로그램 SharePoint 솔루션을 실행 하는 동안 디버그 정보를 캡처하려면 PowerShell cmdlet을 사용 하 여 Visual Studio 외부에서 작동 합니다.  
  
> [!NOTE]  
>  이 섹션의 구성 정보는이 예제에서는 관련이 있습니다. 다른 구성 옵션에 대 한 자세한 내용은 참조 [IntelliTrace 독립 실행형 수집기를 사용 하 여](/visualstudio/debugger/using-the-intellitrace-stand-alone-collector)합니다.  
  
1.  SharePoint를 실행 하는 컴퓨터에서 [Microsoft 모니터링 에이전트를 설정 하 고 솔루션을 모니터링 하려면 시작](/visualstudio/debugger/using-the-intellitrace-stand-alone-collector)합니다.  
  
2.  기능을 비활성화 합니다.  
  
    1.  에 **사이트 작업** sharepoint에서 메뉴 선택 **사이트 설정**합니다.  
  
    2.  아래 **사이트 작업**, 선택는 **사이트 기능 관리** 링크 합니다.  
  
    3.  옆에 **IntelliTraceTest Feature1**, 선택는 **비활성화** 단추입니다.  
  
    4.  경고 페이지에서 선택 된 **이 기능을 비활성화** 링크 합니다.  
  
     (이 경우 인해 FeatureDeactivating() 이벤트 처리기에서 throw 되는 오류) 오류가 발생 합니다.  
  
3.  PowerShell 창에서 실행 된 [Stop-webapplicationmonitoring](http://go.microsoft.com/fwlink/?LinkID=313687) 명령.iTrace 파일을 만들고, 모니터링을 중지, SharePoint 솔루션을 다시 시작 합니다.  
  
     **Stop-webapplicationmonitoring***"\<SharePointSite >\\< SharePointAppName\>"*   
  
##  <a name="BKMK_DebugSolution"></a>디버깅 하 고 SharePoint 솔루션을 수정 합니다.  
 이제를 찾아 SharePoint 솔루션의 오류를 해결 하는 Visual Studio에서 IntelliTrace 로그 파일을 볼 수 있습니다.  
  
#### <a name="to-debug-and-fix-the-sharepoint-solution"></a>SharePoint 솔루션을 디버그 및 수정하려면  
  
1.  \IntelliTraceLogs 폴더에서 Visual Studio에서.iTrace 파일을 엽니다.  
  
     **IntelliTrace 요약** 페이지가 나타납니다. SharePoint 상관 관계 ID (GUID)의 처리 되지 않은 예외 영역에 나타나는 오류 처리 되지 않았습니다. 때문에 **분석** 섹션. 선택 된 **호출 스택** 오류가 발생 한 호출 스택을 보려면 하려면 단추입니다.  
  
2.  선택 된 **예외 디버그** 단추입니다.  
  
     메시지가 표시 되 면 기호 파일을 로드 합니다. 에 **IntelliTrace** 창 예외가 강조 표시로 "throw 됨: 심각한 오류가 발생 했습니다!".  
  
     IntelliTrace 창에서 실패 한 코드를 표시 하는 예외를 선택 합니다.  
  
3.  SharePoint 솔루션을 열고 다음 중 하나를 주석으로 처리 하거나 제거 하 여 오류를 해결는 **throw** FeatureDeactivating() 프로시저 맨 위에 있는 문.  
  
4.  Visual Studio에서 솔루션을 다시 작성 한 다음 SharePoint에 다시 배포 합니다.  
  
5.  다음 단계를 수행 하 여 기능을 비활성화 합니다.  
  
    1.  에 **사이트 작업** sharepoint에서 메뉴 선택 **사이트 설정**합니다.  
  
    2.  아래 **사이트 작업**, 선택는 **사이트 기능 관리** 링크 합니다.  
  
    3.  옆에 **IntelliTraceTest Feature1**, 선택는 **비활성화** 단추입니다.  
  
    4.  경고 페이지에서 선택 된 **이 기능을 비활성화** 링크 합니다.  
  
6.  작업 목록 상자를 열고 되어 있는지 확인은 **상태** 비활성화 작업의 값은 "완료 됨" 및 해당 **% 완료** 값은 100%입니다.  
  
     이제 코드가 제대로 실행 됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [SharePoint 코드 확인 및 디버그](../sharepoint/verifying-and-debugging-sharepoint-code.md)   
 [IntelliTrace](/visualstudio/debugger/intellitrace)   
 [연습: 단위 테스트를 사용 하 여 SharePoint 코드 확인](https://msdn.microsoft.com/en-us/library/gg599006(v=vs.100).aspx)  
  
  