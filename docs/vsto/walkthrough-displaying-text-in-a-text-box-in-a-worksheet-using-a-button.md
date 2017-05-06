---
title: "연습: 워크시트에서 단추를 사용하여 텍스트 상자에 텍스트 표시"
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
  - "텍스트[Visual Studio에서 Office 개발], 워크시트 표시"
  - "텍스트[Visual Studio에서 Office 개발], 텍스트 상자"
  - "텍스트 상자, 워크시트에 텍스트 표시"
  - "워크시트, 텍스트 표시"
ms.assetid: 59b73159-aab7-4f61-9ace-1723c18d78d6
caps.latest.revision: 56
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 55
---
# 연습: 워크시트에서 단추를 사용하여 텍스트 상자에 텍스트 표시
  이 연습에서는 Visual Studio의 Office 개발 도구를 사용하여 Excel 프로젝트를 만드는 방법과 Microsoft Office Excel 워크시트에서 단추와 텍스트 상자를 사용하는 기본적인 방법을 보여 줍니다.  결과를 완성된 샘플로 보려면 [Office 개발 샘플 및 연습](../vsto/office-development-samples-and-walkthroughs.md)의 Excel 컨트롤 샘플을 참조하십시오.  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
 이 연습을 통해 다음과 같은 작업 방법을 배웁니다.  
  
-   워크시트에 컨트롤 추가  
  
-   단추를 클릭할 때 텍스트 상자 채우기  
  
-   프로젝트 테스트  
  
> [!NOTE]  
>  일부 Visual Studio 사용자 인터페이스 요소의 경우 다음 지침에 설명된 것과 다른 이름 또는 위치가 시스템에 표시될 수 있습니다.  설치한 Visual Studio 버전과 사용하는 설정에 따라 이러한 요소가 결정됩니다.  자세한 내용은 [Customizing Development Settings in Visual Studio](http://msdn.microsoft.com/ko-kr/22c4debb-4e31-47a8-8f19-16f328d7dcd3)을 참조하십시오.  
  
## 사전 요구 사항  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Excel_15_short](../vsto/includes/excel-15-short-md.md)] 또는 [!INCLUDE[Excel_14_short](../vsto/includes/excel-14-short-md.md)]  
  
## 프로젝트 만들기  
 이 단계에서는 Visual Studio를 사용하여 Excel 통합 문서 프로젝트를 만듭니다.  
  
#### 새 프로젝트를 만들려면  
  
1.  My Excel Button이라는 Excel 통합 문서 프로젝트를 만듭니다.  **새 문서 만들기**가 선택되어 있는지 확인합니다.  자세한 내용은 [방법: Visual Studio에서 Office 프로젝트 만들기](../vsto/how-to-create-office-projects-in-visual-studio.md)을 참조하십시오.  
  
     Visual Studio의 디자이너에 새 Excel 통합 문서가 열리고 **My Excel Button** 프로젝트가 **솔루션 탐색기**에 추가됩니다.  
  
## 워크시트에 컨트롤 추가  
 이 연습에서는 첫 번째 워크시트에 단추와 텍스트 상자가 있어야 합니다.  
  
#### 단추 및 텍스트 상자를 추가하려면  
  
1.  확인은  **My Excel Button.xlsx** 통합 문서가 Visual Studio 디자이너에 열려 있는와 `Sheet1` 표시 합니다.  
  
2.  도구 상자의 **공용 컨트롤** 탭에서 <xref:Microsoft.Office.Tools.Excel.Controls.TextBox>를 `Sheet1`에 끌어 놓습니다.  
  
3.  **보기** 메뉴에서 **속성 창**을 선택합니다.  
  
4.  **속성** 창 드롭다운 상자에 **TextBox1**이 표시되어 있는지 확인하고 텍스트 상자의 **Name** 속성을 **displayText**로 변경합니다.  
  
5.  **Button** 컨트롤을 `Sheet1`에 끌어 놓고 다음 속성을 변경합니다.  
  
    |속성|값|  
    |--------|-------|  
    |**이름**|**insertText**|  
    |**텍스트**|텍스트 삽입|  
  
 이제 단추를 클릭할 때 실행할 코드를 작성합니다.  
  
## 단추를 클릭할 때 텍스트 상자 채우기  
 사용자가 단추를 클릭할 때마다  **Hello World\!** 텍스트 상자에 추가 됩니다.  
  
#### 단추를 클릭할 때 텍스트 상자에 내용을 표시하려면  
  
1.  **솔루션 탐색기**에서 마우스 오른쪽 단추로 **Sheet1**을 클릭한 다음 바로 가기 메뉴에서 **코드 보기**를 클릭합니다.  
  
2.  단추의 <xref:System.Windows.Forms.Control.Click> 이벤트 처리기에 다음 코드를 추가합니다.  
  
     [!code-csharp[Trin_VstcoreProgrammingControlsExcel#11](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreProgrammingControlsExcel/CS/Sheet1.cs#11)]
     [!code-vb[Trin_VstcoreProgrammingControlsExcel#11](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreProgrammingControlsExcel/VB/Sheet1.vb#11)]  
  
3.  C\#의 경우 아래와 같이 <xref:Microsoft.Office.Tools.Excel.Worksheet.Startup> 이벤트에 이벤트 처리기를 추가해야 합니다.  이벤트 처리기를 만드는 방법에 대한 자세한 내용은 [방법: Office 프로젝트에서 이벤트 처리기 만들기](../vsto/how-to-create-event-handlers-in-office-projects.md)를 참조하십시오.  
  
     [!code-csharp[Trin_VstcoreProgrammingControlsExcel#12](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreProgrammingControlsExcel/CS/Sheet1.cs#12)]  
  
## 응용 프로그램 테스트  
 이제 통합 문서 있는지를 테스트할 수 있습니다 메시지  **Hello World\!** 단추를 클릭 하면 텍스트 상자에 나타납니다.  
  
#### 통합 문서를 테스트하려면  
  
1.  F5 키를 눌러 프로젝트를 실행합니다.  
  
2.  단추를 클릭합니다.  
  
3.  확인  **Hello World\!** 텍스트 상자에 나타납니다.  
  
## 다음 단계  
 이 연습에서는 Excel 워크시트에서 단추와 텍스트 상자를 사용하는 기본적인 방법을 보여 줍니다.  다음에 수행할 수 있는 작업은 다음과 같습니다.  
  
-   프로젝트를 배포합니다.  자세한 내용은 [Office 솔루션 배포](../vsto/deploying-an-office-solution.md)을 참조하십시오.  
  
-   확인란을 사용하여 서식을 변경합니다.  자세한 내용은 [연습: CheckBox 컨트롤을 사용하여 워크시트 서식 변경](../vsto/walkthrough-changing-worksheet-formatting-using-checkbox-controls.md)을 참조하십시오.  
  
## 참고 항목  
 [방법: Office 문서에 Windows Forms 컨트롤 추가](../vsto/how-to-add-windows-forms-controls-to-office-documents.md)   
 [Excel을 사용한 연습](../vsto/walkthroughs-using-excel.md)   
 [Office 문서에서 Windows Forms 컨트롤에 대한 제한 사항](../vsto/limitations-of-windows-forms-controls-on-office-documents.md)  
  
  