---
title: "연습: 워크플로에 응용 프로그램 페이지 추가 | Microsoft Docs"
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
- SharePoint development in Visual Studio, adding applications page to workflow
- application page [SharePoint development in Visual Studio]
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: 86b402e1f8b8be3adf477d67eb11387fa3091afd
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="walkthrough-add-an-application-page-to-a-workflow"></a>연습: 워크플로에 응용 프로그램 페이지 추가
  이 연습에는 워크플로 프로젝트에는 워크플로에서 파생 된 데이터를 표시 하는 응용 프로그램 페이지를 추가 하는 방법을 보여 줍니다. 이 항목에서 설명 하는 프로젝트에 기반 [연습: 연결 및 초기화 폼이 있는 워크플로 만들기](../sharepoint/walkthrough-creating-a-workflow-with-association-and-initiation-forms.md)합니다.  
  
 이 연습에서는 다음 작업을 수행합니다.  
  
-   ASPX 응용 프로그램 페이지를 SharePoint 워크플로 프로젝트에 추가 합니다.  
  
-   워크플로 프로젝트에서 데이터를 가져오기 및 조작 합니다.  
  
-   응용 프로그램 페이지에서 테이블에 데이터를 표시 합니다.  
  
 [!INCLUDE[note_settings_general](../sharepoint/includes/note-settings-general-md.md)]  
  
## <a name="prerequisites"></a>필수 구성 요소  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   지원 되는 버전 [!INCLUDE[TLA#tla_win](../sharepoint/includes/tlasharptla-win-md.md)] 및 SharePoint 합니다. 자세한 내용은 참조 [SharePoint 솔루션 개발 요구 사항](../sharepoint/requirements-for-developing-sharepoint-solutions.md)합니다.  
  
-   Visual Studio.  
  
-   항목의 프로젝트를 완료 해야 [연습: 연결 및 초기화 폼이 있는 워크플로 만들기](../sharepoint/walkthrough-creating-a-workflow-with-association-and-initiation-forms.md)합니다.  
  
## <a name="amending-the-workflow-code"></a>워크플로 코드 수정  
 먼저, 경비 보고서에는 결과 열 값을 설정 하는 워크플로를 코드의 줄을 추가 합니다. 이 값은 경비 보고서 요약 계산의 뒷부분에 나오는 사용 됩니다.  
  
#### <a name="to-set-the-value-of-the-outcome-column-in-the-workflow"></a>워크플로에서 결과 열 값을 설정 하려면  
  
1.  이 항목에서 완료 된 프로젝트를 로드할 [연습: 연결 및 초기화 폼이 있는 워크플로 만들기](../sharepoint/walkthrough-creating-a-workflow-with-association-and-initiation-forms.md) 에 [!INCLUDE[vsprvs](../sharepoint/includes/vsprvs-md.md)]합니다.  
  
2.  (선택한 프로그래밍 언어)에 따라 다름 Workflow1.cs 또는 Workflow1.vb에 대 한 코드를 엽니다.  
  
3.  맨 아래에 `createTask1_MethodInvoking` 메서드를 다음 코드를 추가 합니다.  
  
    ```vb  
    createTask1_TaskProperties1.ExtendedProperties("Outcome") =   
      workflowProperties.InitiationData  
    ```  
  
    ```csharp  
    createTask1_TaskProperties1.ExtendedProperties["Outcome"] =   
      workflowProperties.InitiationData;  
    ```  
  
## <a name="creating-an-application-page"></a>응용 프로그램 페이지 만들기  
 다음으로 프로젝트에 ASPX 폼을 추가 합니다. 이 양식은 경비 보고서 워크플로 프로젝트에서 가져온 데이터가 표시 됩니다. 이 위해 응용 프로그램 페이지를 추가 합니다. 응용 프로그램 페이지는 다른 SharePoint 페이지가 만들어지고 SharePoint 사이트에서 다른 페이지와 유사 합니다 즉으로 동일한 마스터 페이지를 사용 합니다.  
  
#### <a name="to-add-an-application-page-to-the-project"></a>프로젝트에 응용 프로그램 페이지를 추가 하려면  
  
1.  경비 보고서 프로젝트를 선택한 다음 메뉴 모음에서 메뉴 **프로젝트**, **새 항목 추가**합니다.  
  
2.  에 **템플릿** 창, 선택는 **응용 프로그램 페이지** 서식 파일을 프로젝트 항목에 대 한 기본 이름을 사용 (**ApplicaitonPage1.aspx**)는 선택**추가** 단추입니다.  
  
3.  에 [!INCLUDE[TLA2#tla_xml](../sharepoint/includes/tla2sharptla-xml-md.md)] 의 ApplicationPage1.aspx, 대체 된 `PlaceHolderMain` 섹션을 다음:  
  
    ```  
    <asp:Content ID="Main" ContentPlaceHolderID="PlaceHolderMain" runat="server">  
        <asp:Label ID="Label1" runat="server" Font-Bold="True"   
            Text="Expenses that exceeded allotted amount" Font-Size="Medium"></asp:Label>  
        <br />  
        <asp:Table ID="Table1" runat="server">  
        </asp:Table>  
    </asp:Content>  
    ```  
  
     이 코드는 제목과 함께 페이지에 테이블을 추가합니다.  
  
4.  대체 하 여 응용 프로그램 페이지에 제목 추가 `PlaceHolderPageTitleInTitleArea` 섹션을 다음:  
  
    ```  
    <asp:Content ID="PageTitleInTitleArea" ContentPlaceHolderID="PlaceHolderPageTitleInTitleArea" runat="server" >  
        Expense Report Summary  
    </asp:Content>  
    ```  
  
## <a name="coding-the-application-page"></a>응용 프로그램 페이지를 코딩합니다.  
 다음으로 경비 보고서 요약 응용 프로그램 페이지에 코드를 추가 합니다. 페이지를 열 때 코드는 SharePoint 작업 목록에에서 할당 된 지출 한도 초과 하는 비용이 대 한를 검색 합니다. 보고서는 비용 합계와 함께 각 항목을 나열합니다.  
  
#### <a name="to-code-the-application-page"></a>응용 프로그램 페이지의 코드를 작성 하려면  
  
1.  선택 된 **ApplicationPage1.aspx** 노드를 선택한 다음 메뉴 모음에서 메뉴 **보기**, **코드** 코드 숨김 응용 프로그램 페이지를 표시 합니다.  
  
2.  대체는 **를 사용 하 여** 또는 **가져오기** 다음을 사용 하 여 클래스의 맨 (에 따라 선택한 프로그래밍 언어) 문:  
  
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
    >  SharePoint를 실행 하는 유효한 서버 이름으로 코드에서 "TestServer"를 대체 해야 합니다.  
  
## <a name="testing-the-application-page"></a>응용 프로그램 페이지를 테스트합니다.  
 다음으로 응용 프로그램 페이지 비용 데이터를 올바르게 표시 여부를 확인 합니다.  
  
#### <a name="to-test-the-application-page"></a>응용 프로그램 페이지를 테스트 하려면  
  
1.  F5 키를 실행 하 고 프로젝트를 SharePoint 배포를 선택 합니다.  
  
2.  선택 된 **홈** 단추를 선택한 후는 **공유 문서** SharePoint 사이트에서 공유 문서 목록을 표시 하려면 빠른 실행 모음에서 링크 합니다.  
  
3.  이 예제에 대 한 경비 보고서를 표시 하려면 몇 가지 새 문서 문서 목록에 선택 하 여 업로드는 **문서** 에서 링크는 **라이브러리** 는 선택페이지의맨위탭 **문서 업로드** 도구 리본의 단추입니다.  
  
4.  일부 문서를 업로드 한 후을 선택 하 여 워크플로 인스턴스화하는 **라이브러리** 링크를 **라이브러리** 페이지 및 다음의 맨 위 탭은 **라이브러리 설정**도구 리본의 단추입니다.  
  
5.  에 **문서 라이브러리 설정** 페이지를 선택 합니다는 **워크플로 설정** 연결에 **사용 권한 및 관리** 섹션.  
  
6.  **워크플로 설정** 페이지에서 선택 된 **워크플로 추가** 링크 합니다.  
  
7.  **워크플로 추가** 페이지를 선택 합니다는 **경비 보고서-Workflow1** 워크플로 같은 워크플로의 이름을 입력 **ExpenseTest**는 선택**다음** 단추입니다.  
  
     워크플로 연결 폼이 나타납니다. 지출 한도 금액을 보고 하기 위해 사용 합니다.  
  
8.  연결 폼에 입력 **1000** 에 **자동 승인 제한** 상자를 선택한 후는 **워크플로 연결** 단추입니다.  
  
9. 선택 된 **홈** 단추 SharePoint 홈 페이지로 돌아갑니다.  
  
10. 선택 된 **공유 문서** 빠른 실행 모음에서 링크 합니다.  
  
11. 드롭다운 화살표를 표시을 선택한 다음를 선택 하려면 업로드 된 문서 중 하나를 선택 하 고 **워크플로** 항목입니다.  
  
12. 워크플로 초기화 폼을 표시 하려면 ExpenseTest 옆에 있는 이미지를 선택 합니다.  
  
13. 에 **비용 합계** 입력란을 1000 보다 큰 값을 입력 한 다음 선택는 **워크플로 시작** 단추입니다.  
  
     보고 된 비용이 할당된 된 비용 금액을 초과 하면 작업이 작업 목록에 추가 됩니다. 라는 열 **ExpenseTest** 값과 **Completed** 공유 문서 목록에 경비 보고서 항목에도 추가 됩니다.  
  
14. 공유 문서 목록에 다른 문서와 함께 11-13 단계를 반복 합니다. (문서의 정확한 수 중요 하지 않습니다.)  
  
15. 웹 브라우저에서 다음 URL을 열어 경비 보고서 요약 응용 프로그램 페이지를 표시: **http://***SystemName***/_layouts/ExpenseReport/ApplicationPage1.aspx**.  
  
     경비 보고서 요약 페이지에 할당 된 금액을 초과 하는 경비 보고서, by, 초과 금액 및 모든 보고서에 대 한 총 금액 모두 나열 합니다.  
  
## <a name="next-steps"></a>다음 단계  
 SharePoint 응용 프로그램 페이지에 대 한 자세한 내용은 참조 [SharePoint 용 응용 프로그램 페이지 만들기](../sharepoint/creating-application-pages-for-sharepoint.md)합니다.  
  
 다음이 항목에서는 Visual Studio에서 비주얼 웹 디자이너를 사용 하 여 SharePoint 페이지 콘텐츠를 디자인 하는 방법에 대 한 더 알아볼 수 있습니다.  
  
-   [SharePoint를 위한 웹 파트 만들기](../sharepoint/creating-web-parts-for-sharepoint.md)합니다.  
  
-   [웹 파트 또는 응용 프로그램 페이지에 대 한 재사용 가능한 컨트롤 만들기](../sharepoint/creating-reusable-controls-for-web-parts-or-application-pages.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [연습: 연결 및 초기화 폼이 있는 워크플로 만들기](../sharepoint/walkthrough-creating-a-workflow-with-association-and-initiation-forms.md)   
 [방법: 응용 프로그램 페이지 만들기](../sharepoint/how-to-create-an-application-page.md)   
 [SharePoint 용 응용 프로그램 페이지 만들기](../sharepoint/creating-application-pages-for-sharepoint.md)   
 [SharePoint 솔루션 개발](../sharepoint/developing-sharepoint-solutions.md)  
  
  