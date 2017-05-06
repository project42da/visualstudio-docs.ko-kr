---
title: "연습: 워크플로에 응용 프로그램 페이지 추가"
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
  - "응용 프로그램 페이지[Visual Studio에서 SharePoint 개발]"
  - "Visual Studio에서 SharePoint 개발, 워크플로에 응용 프로그램 페이지 추가"
ms.assetid: e4845d07-917b-45cb-a569-4ecdd602fbd9
caps.latest.revision: 28
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 27
---
# 연습: 워크플로에 응용 프로그램 페이지 추가
  이 연습에서는 워크플로에서 파생된 데이터를 표시하는 응용 프로그램 페이지를 워크플로 프로젝트에 추가하는 방법을 보여 주며,  [연습: 연결 및 초기화 폼이 있는 워크플로 만들기](../sharepoint/walkthrough-creating-a-workflow-with-association-and-initiation-forms.md) 항목에 설명된 프로젝트를 사용합니다.  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   SharePoint 워크플로 프로젝트에 ASPX 응용 프로그램 페이지 추가  
  
-   워크플로 프로젝트에서 데이터 가져오기 및 조작  
  
-   응용 프로그램 페이지의 표에 데이터 표시  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## 사전 요구 사항  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   지원되는 [!INCLUDE[TLA#tla_win](../sharepoint/includes/tlasharptla-win-md.md)] 및 SharePoint 버전.  자세한 내용은 [SharePoint 솔루션 개발 요구 사항](../sharepoint/requirements-for-developing-sharepoint-solutions.md)을 참조하십시오.  
  
-   Visual Studio  
  
-   [연습: 연결 및 초기화 폼이 있는 워크플로 만들기](../sharepoint/walkthrough-creating-a-workflow-with-association-and-initiation-forms.md) 항목의 프로젝트도 완료해야 합니다.  
  
## 워크플로 코드 수정  
 먼저 워크플로에 한 줄의 코드를 추가하여 결과 열의 값을 비용 보고서의 금액으로 설정합니다.  이 값은 나중에 비용 보고서 요약을 계산할 때 사용됩니다.  
  
#### 워크플로에 있는 결과 열의 값을 설정하려면  
  
1.  [연습: 연결 및 초기화 폼이 있는 워크플로 만들기](../sharepoint/walkthrough-creating-a-workflow-with-association-and-initiation-forms.md) 항목에서 완료된 프로젝트를 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]에 로드합니다.  
  
2.  프로그래밍 언어에 따라 Workflow1.cs 또는 Workflow1.vb의 코드를 엽니다.  
  
3.  `createTask1_MethodInvoking` 메서드의 맨 아래에 다음 코드를 추가합니다.  
  
    ```vb  
    createTask1_TaskProperties1.ExtendedProperties("Outcome") =   
      workflowProperties.InitiationData  
    ```  
  
    ```csharp  
    createTask1_TaskProperties1.ExtendedProperties["Outcome"] =   
      workflowProperties.InitiationData;  
    ```  
  
## 응용 프로그램 페이지 만들기  
 다음으로, 프로젝트에 ASPX 폼을 추가합니다.  이 폼에는 비용 보고서 워크플로 프로젝트에서 가져온 데이터가 표시됩니다.  이렇게 하려면 응용 프로그램 페이지를 추가합니다.  응용 프로그램 페이지에서는 다른 SharePoint 페이지와 동일한 마스터 페이지를 사용하므로 SharePoint 사이트의 다른 페이지와 유사하게 나타납니다.  
  
#### 프로젝트에 응용 프로그램 페이지를 추가하려면  
  
1.  ExpenseReport 프로젝트를 선택한 다음, 메뉴 표시줄에서 **프로젝트**, **새 항목 추가**를 선택합니다.  
  
2.  **템플릿** 창에서 **응용 프로그램 페이지** 템플릿을 선택하고 프로젝트 항목에 대한 기본 이름\(**ApplicaitonPage1.aspx**\)을 사용한 다음, **추가** 버튼을 선택합니다.  
  
3.  ApplicationPage1.aspx의 [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)]에서 `PlaceHolderMain` 섹션을 다음 코드로 바꿉니다.  
  
    ```  
    <asp:Content ID="Main" ContentPlaceHolderID="PlaceHolderMain" runat="server">  
        <asp:Label ID="Label1" runat="server" Font-Bold="True"   
            Text="Expenses that exceeded allotted amount" Font-Size="Medium"></asp:Label>  
        <br />  
        <asp:Table ID="Table1" runat="server">  
        </asp:Table>  
    </asp:Content>  
    ```  
  
     이 코드는 제목과 함께 표를 페이지에 추가합니다.  
  
4.  `PlaceHolderPageTitleInTitleArea` 섹션을 다음 코드로 바꾸어 응용 프로그램에 제목을 추가합니다.  
  
    ```  
    <asp:Content ID="PageTitleInTitleArea" ContentPlaceHolderID="PlaceHolderPageTitleInTitleArea" runat="server" >  
        Expense Report Summary  
    </asp:Content>  
    ```  
  
## 응용 프로그램 페이지 코딩  
 다음으로, 비용 보고서 요약 응용 프로그램 페이지에 코드를 추가합니다.  페이지를 열면 코드에 따라 SharePoint 작업 목록에서 할당된 비용 한도를 초과하는 비용이 스캔됩니다.  보고서 목록에는 비용 합계와 함께 각 항목이 표시됩니다.  
  
#### 응용 프로그램 페이지를 코딩하려면  
  
1.  **ApplicationPage1.aspx** 노드를 선택한 다음, 메뉴 표시줄에서 **보기**, **코드** 를 선택하여 응용 프로그램 페이지에 숨은 코드를 표시합니다.  
  
2.  프로그래밍 언어에 따라 클래스의 맨 위에 있는 **using** 또는 **Import** 문을 다음 코드로 바꿉니다.  
  
    ```vb  
    Imports System  
    Imports Microsoft.SharePoint  
    Imports Microsoft.SharePoint.WebControls  
    Imports System.Collections  
    Imports System.Data  
    Imports System.Web.UI  
    Imports System.Web.UI.WebControls  
    Imports System.Web.UI.WebControls.WebParts  
    Imports System.Drawing  
    Imports Microsoft.SharePoint.Navigation  
    ```  
  
    ```csharp  
    using System;  
    using Microsoft.SharePoint;  
    using Microsoft.SharePoint.WebControls;  
    using System.Collections;  
    using System.Data;  
    using System.Web.UI;  
    using System.Web.UI.WebControls;  
    using System.Web.UI.WebControls.WebParts;  
    using System.Drawing;  
    using Microsoft.SharePoint.Navigation;  
    ```  
  
3.  `Page_Load` 메서드에 다음 코드를 추가합니다.  
  
    ```vb  
    Try  
        ' Reference the Tasks list on the SharePoint site.  
        ' Replace "TestServer" with a valid SharePoint server name.  
        Dim site As SPSite = New SPSite("http://TestServer")  
        Dim list As SPList = site.AllWebs(0).Lists("Tasks")  
        ' string text = "";  
        Dim sum As Integer = 0  
        Table1.Rows.Clear()  
        ' Add table headers.  
        Dim hr As TableHeaderRow = New TableHeaderRow  
        hr.BackColor = Color.LightBlue  
        Dim hc1 As TableHeaderCell = New TableHeaderCell  
        Dim hc2 As TableHeaderCell = New TableHeaderCell  
        hc1.Text = "Expense Report Name"  
        hc2.Text = "Amount Exceeded"  
        hr.Cells.Add(hc1)  
        hr.Cells.Add(hc2)  
        ' Add the TableHeaderRow as the first item   
        ' in the Rows collection of the table.  
        Table1.Rows.AddAt(0, hr)  
        ' Iterate through the tasks in the Task list and collect those    
        ' that have values in the "Related Content" and "Outcome" fields   
        ' - the fields written to when expense approval is required.  
        For Each item As SPListItem In list.Items  
            Dim s_relContent As String = ""  
            Dim s_outcome As String = ""  
            Try  
                ' Task has the fields - treat as expense report.  
                s_relContent = item.GetFormattedValue("Related Content")  
                s_outcome = item.GetFormattedValue("Outcome")  
            Catch erx As System.Exception  
                ' Task does not have fields - skip it.  
                Continue For  
            End Try  
            ' Convert amount to an int and keep a running total.  
            If (Not String.IsNullOrEmpty(s_relContent) And Not   
              String.IsNullOrEmpty(s_outcome)) Then  
                sum = (sum + Convert.ToInt32(s_outcome))  
                Dim relContent As TableCell = New TableCell  
                relContent.Text = s_relContent  
                Dim outcome As TableCell = New TableCell  
                outcome.Text = ("$" + s_outcome)  
                Dim dataRow2 As TableRow = New TableRow  
                dataRow2.Cells.Add(relContent)  
                dataRow2.Cells.Add(outcome)  
                Table1.Rows.Add(dataRow2)  
            End If  
        Next  
        ' Report the sum of the reports in the table footer.  
        Dim tfr As TableFooterRow = New TableFooterRow  
        tfr.BackColor = Color.LightGreen  
        ' Create a TableCell object to contain the   
        ' text for the footer.  
        Dim ftc1 As TableCell = New TableCell  
        Dim ftc2 As TableCell = New TableCell  
        ftc1.Text = "TOTAL: "  
        ftc2.Text = ("$" + Convert.ToString(sum))  
        ' Add the TableCell object to the Cells  
        ' collection of the TableFooterRow.  
        tfr.Cells.Add(ftc1)  
        tfr.Cells.Add(ftc2)  
        ' Add the TableFooterRow to the Rows  
        ' collection of the table.  
        Table1.Rows.Add(tfr)  
    Catch errx As Exception  
        System.Diagnostics.Debug.WriteLine(("Error: " + errx.ToString))  
    End Try  
    ```  
  
    ```csharp  
    try  
    {  
        // Reference the Tasks list on the SharePoint site.  
        // Replace "TestServer" with a valid SharePoint server name.  
        SPSite site = new SPSite("http://TestServer");  
        SPList list = site.AllWebs[0].Lists["Tasks"];  
  
        // string text = "";  
        int sum = 0;  
  
        Table1.Rows.Clear();  
  
        // Add table headers.  
        TableHeaderRow hr = new TableHeaderRow();  
        hr.BackColor = Color.LightBlue;  
        TableHeaderCell hc1 = new TableHeaderCell();  
        TableHeaderCell hc2 = new TableHeaderCell();  
        hc1.Text = "Expense Report Name";  
        hc2.Text = "Amount Exceeded";  
        hr.Cells.Add(hc1);  
        hr.Cells.Add(hc2);  
        // Add the TableHeaderRow as the first item   
        // in the Rows collection of the table.  
        Table1.Rows.AddAt(0, hr);  
  
        // Iterate through the tasks in the Task list and collect those   
        // that have values in the "Related Content" and "Outcome"   
        // fields - the fields written to when expense approval is   
        // required.  
        foreach (SPListItem item in list.Items)  
        {  
            string s_relContent = "";  
            string s_outcome = "";  
  
            try  
            {  
                // Task has the fields - treat as expense report.  
                s_relContent = item.GetFormattedValue("Related   
                  Content");  
                s_outcome = item.GetFormattedValue("Outcome");  
            }  
            catch  
            {  
                // Task does not have fields - skip it.  
                continue;  
            }  
  
            if (!String.IsNullOrEmpty(s_relContent) &&   
              !String.IsNullOrEmpty(s_outcome))  
            {  
                // Convert amount to an int and keep a running total.  
                sum += Convert.ToInt32(s_outcome);  
                TableCell relContent = new TableCell();  
                relContent.Text = s_relContent;  
                TableCell outcome = new TableCell();  
                outcome.Text = "$" + s_outcome;  
                TableRow dataRow2 = new TableRow();  
                dataRow2.Cells.Add(relContent);  
                dataRow2.Cells.Add(outcome);  
                Table1.Rows.Add(dataRow2);  
            }  
        }  
  
        // Report the sum of the reports in the table footer.  
           TableFooterRow tfr = new TableFooterRow();  
        tfr.BackColor = Color.LightGreen;  
  
        // Create a TableCell object to contain the   
        // text for the footer.  
        TableCell ftc1 = new TableCell();  
        TableCell ftc2 = new TableCell();  
        ftc1.Text = "TOTAL: ";  
        ftc2.Text = "$" + Convert.ToString(sum);  
  
        // Add the TableCell object to the Cells  
        // collection of the TableFooterRow.  
        tfr.Cells.Add(ftc1);  
        tfr.Cells.Add(ftc2);  
  
        // Add the TableFooterRow to the Rows  
        // collection of the table.  
        Table1.Rows.Add(tfr);  
    }  
  
    catch (Exception errx)  
    {  
        System.Diagnostics.Debug.WriteLine("Error: " + errx.ToString());  
    }  
    ```  
  
    > [!WARNING]  
    >  코드에서 "TestServer" 를 SharePoint를 실행 하는 올바른 서버 이름으로 대체 해야 합니다.  
  
## 응용 프로그램 페이지 테스트  
 다음으로, 응용 프로그램 페이지에 비용 데이터가 제대로 표시되는지 여부를 확인합니다.  
  
#### 응용 프로그램 페이지를 테스트하려면  
  
1.  F5 키를 눌러 프로젝트를 실행하고 SharePoint에 배포합니다.  
  
2.  **홈** 버튼을 선택한 다음, 빠른 실행 모음에서 **공유 문서** 링크를 선택하여 SharePoint 사이트의 공유 문서 목록을 표시합니다.  
  
3.  이 예제의 비용 보고서를 표시하려면, 페이지 맨 위에 있는 **라이브러리 도구** 탭에서 **문서** 링크를 선택한 다음 도구 리본 메뉴에서 **문서 업로드** 단추를 선택하여 문서 목록에 새 문서를 업로드합니다.  
  
4.  일부 문서를 업로드 한 후, 페이지 맨 위에 있는 **라이브러리** 탭에서 **라이브러리** 링크를 선택한 다음 도구 리본 메뉴에서 **라이브러리 설정** 버튼을 선택하여 워크플로를 인스턴스화합니다.  
  
5.  **문서 라이브러리 설정** 페이지의 **사용 권한 및 관리** 섹션에서 **워크플로 설정** 링크를 선택합니다.  
  
6.  **워크플로 설정** 페이지에서 **워크플로 추가** 링크를 선택합니다.  
  
7.  **워크플로 추가** 페이지에서 **ExpenseReport \- Workflow1** 워크플로를 선택하고 워크플로의 이름\(예: ExpenseTest\)을 입력한 후 **다음** 버튼을 선택합니다.  
  
     워크플로 연결 폼이 나타납니다.  이 폼은 비용 한도 금액을 보고하는 데 사용합니다.  
  
8.  연결 폼에서 **자동 승인 한도** 란에 **1000** 을 입력 한 다음 **워크플로 연결** 버튼을 선택합니다.  
  
9. **홈** 버튼을 선택하여 SharePoint 홈 페이지로 돌아갑니다.  
  
10. 빠른 실행 모음에서 **공유 문서** 링크를 선택합니다.  
  
11. 업로드 된 문서 중 하나를 선택하여 드롭다운 화살표 표시를 선택하고, 선택한 다음 **워크플로** 항목을 선택합니다.  
  
12. ExpenseTest 옆에 있는 이미지를 선택하여 워크플로 초기화 폼을 표시합니다.  
  
13. **비용 합계** 텍스트 상자에 1000보다 큰 값을 입력하고 **워크플로 시작** 버튼을 선택합니다.  
  
     보고된 비용이 할당된 비용 금액을 초과하는 경우 작업 목록에 작업이 추가됩니다.  또한 값이 **완료됨**인 **ExpenseTest**라는 열이 공유 문서 목록의 비용 보고서 항목에 추가됩니다.  
  
14. 공유 문서 목록의 다른 문서에 대해 11 \- 13단계를 반복합니다. 정확한 문서 수는 중요하지 않습니다.  
  
15. 웹 브라우저에서 이 URL \(**http:\/\/***SystemName***\/\_layouts\/ExpenseReport\/ApplicationPage1.aspx**\) 을 열어 비용 보고서 요약 응용 프로그램 페이지를 표시합니다.  
  
     비용 보고서 요약 페이지에 할당된 금액, 초과 금액 및 모든 보고서의 합계 금액을 초과하는 모든 비용 보고서가 표시됩니다.  
  
## 다음 단계  
 SharePoint 응용 프로그램 페이지에 대한 자세한 내용은 [SharePoint를 위한 응용 프로그램 페이지 만들기](../sharepoint/creating-application-pages-for-sharepoint.md)를 참조하십시오.  
  
 다음 항목에서 Visual Studio의 Visual Web Designer를 사용하여 SharePoint 페이지 내용을 디자인하는 방법에 대해 더 자세히 알아볼 수 있습니다.  
  
-   [SharePoint를 위한 웹 파트 만들기](../sharepoint/creating-web-parts-for-sharepoint.md).  
  
-   [웹 파트 또는 응용 프로그램 페이지를 위해 재사용 가능한 컨트롤 만들기](../sharepoint/creating-reusable-controls-for-web-parts-or-application-pages.md).  
  
## 참고 항목  
 [연습: 연결 및 초기화 폼이 있는 워크플로 만들기](../sharepoint/walkthrough-creating-a-workflow-with-association-and-initiation-forms.md)   
 [방법: 응용 프로그램 페이지 만들기](../sharepoint/how-to-create-an-application-page.md)   
 [SharePoint를 위한 응용 프로그램 페이지 만들기](../sharepoint/creating-application-pages-for-sharepoint.md)   
 [Developing SharePoint Solutions](../sharepoint/developing-sharepoint-solutions.md)  
  
  