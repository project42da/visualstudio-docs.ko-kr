---
title: "연습: 단추를 사용 하 여 워크시트에 텍스트 상자에 텍스트를 표시 하 | Microsoft Docs"
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
- text [Office development in Visual Studio], displaying worksheets
- worksheets, displaying text
- text boxes, displaying text in worksheets
- text [Office development in Visual Studio], text boxes
ms.assetid: 59b73159-aab7-4f61-9ace-1723c18d78d6
caps.latest.revision: "56"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.workload: office
ms.openlocfilehash: 7743a3d1c0548b444343b3dc96b25eabac4ac951
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="walkthrough-displaying-text-in-a-text-box-in-a-worksheet-using-a-button"></a>연습: 워크시트에서 단추를 사용하여 텍스트 상자에 텍스트 표시
  이 연습에서는 Visual Studio에서 Office 개발 도구를 사용 하 여 Excel 프로젝트를 만드는 방법 및 Microsoft Office Excel 워크시트에서 단추 및 텍스트 상자를 사용 하는 기본적인 보여 줍니다. 결과 전체 샘플을 보려면 Excel 컨트롤 샘플을 참조 [Office 개발 샘플 및 연습](../vsto/office-development-samples-and-walkthroughs.md)합니다.  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
 이 연습에서는 다음 작업을 수행하는 방법을 배웁니다.  
  
-   워크시트에 컨트롤을 추가 합니다.  
  
-   단추를 클릭할 때 텍스트 상자를 채웁니다.  
  
-   프로젝트를 테스트 합니다.  
  
> [!NOTE]  
>  일부 Visual Studio 사용자 인터페이스 요소의 경우 다음 지침에 설명된 것과 다른 이름 또는 위치가 시스템에 표시될 수 있습니다. 이러한 요소는 사용하는 Visual Studio 버전 및 설정에 따라 결정됩니다. 자세한 내용은 [Visual Studio IDE 개인 설정](../ide/personalizing-the-visual-studio-ide.md)을 참조하세요.  
  
## <a name="prerequisites"></a>필수 구성 요소  
 이 연습을 완료하려면 다음 구성 요소가 필요합니다.  
  
-   [!INCLUDE[vsto_vsprereq](../vsto/includes/vsto-vsprereq-md.md)]  
  
-   [!INCLUDE[Excel_15_short](../vsto/includes/excel-15-short-md.md)] 또는 [!INCLUDE[Excel_14_short](../vsto/includes/excel-14-short-md.md)]  
  
## <a name="creating-the-project"></a>프로젝트 만들기  
 이 단계에서는 Visual Studio를 사용 하 여 Excel 통합 문서 프로젝트를 만듭니다.  
  
#### <a name="to-create-a-new-project"></a>새 프로젝트를 만들려면  
  
1.  이름의 Excel 통합 문서 프로젝트를 만들 **내 Excel 단추**합니다. 다음 사항을 확인 **새 문서** 을 선택 합니다. 자세한 내용은 [How to: Create Office Projects in Visual Studio](../vsto/how-to-create-office-projects-in-visual-studio.md)을 참조하세요.  
  
     Visual Studio 디자이너에서 새 Excel 통합 문서를 열고 추가 된 **내 Excel 단추** 프로젝트를 **솔루션 탐색기**합니다.  
  
## <a name="adding-controls-to-the-worksheet"></a>워크시트에 컨트롤 추가  
 이 연습에서는 단추와 입력란 첫 번째 워크시트에 필요 합니다.  
  
#### <a name="to-add-a-button-and-a-text-box"></a>단추 및 텍스트 상자를 추가하려면  
  
1.  되어 있는지 확인는 **내 Excel Button.xlsx** Visual Studio 디자이너에 통합 문서가 열려 있는 `Sheet1` 표시 합니다.  
  
2.  **공용 컨트롤** 끌어서 도구 상자 탭은 <xref:Microsoft.Office.Tools.Excel.Controls.TextBox> 를 `Sheet1`합니다.  
  
3.  **보기** 메뉴 선택 **속성 창**합니다.  
  
4.  수 있도록 **TextBox1** 에 표시 되는 **속성** 창 드롭다운 상자 및 변경의 **이름** 를 입력란의 속성 **displayText**.  
  
5.  끌어서는 **단추** 컨트롤을 끌어와 `Sheet1` 다음 속성을 변경 합니다.  
  
    |속성|값|  
    |--------------|-----------|  
    |**이름**|**insertText**|  
    |**텍스트**|**텍스트 삽입**|  
  
 이제 단추를 클릭할 때 실행 되도록 코드를 작성 합니다.  
  
## <a name="populating-the-text-box-when-the-button-is-clicked"></a>단추를 클릭할 때 텍스트 상자 채우기  
 사용자가 단추를 클릭할 때마다 **Hello World!** 텍스트 상자에 추가 됩니다.  
  
#### <a name="to-write-to-the-text-box-when-the-button-is-clicked"></a>단추를 클릭할 때 텍스트 상자에 쓰려면  
  
1.  **솔루션 탐색기**를 마우스 오른쪽 단추로 클릭 **Sheet1**, 클릭 하 고 **코드 보기** 바로 가기 메뉴.  
  
2.  다음 코드를 추가 하는 <xref:System.Windows.Forms.Control.Click> 단추의 이벤트 처리기.  
  
     [!code-vb[Trin_VstcoreProgrammingControlsExcel#11](../vsto/codesnippet/VisualBasic/my excel chart/Sheet1.vb#11)]
     [!code-csharp[Trin_VstcoreProgrammingControlsExcel#11](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsExcelCS/Sheet1.cs#11)]  
  
3.  C#에서 이벤트 처리기를 추가 해야는 <xref:Microsoft.Office.Tools.Excel.Worksheet.Startup> 아래와 같이 이벤트입니다. 이벤트 처리기를 만드는 방법에 대 한 정보를 참조 하십시오. [하는 방법: Office 프로젝트의 이벤트 처리기 만들기](../vsto/how-to-create-event-handlers-in-office-projects.md)합니다.  
  
     [!code-csharp[Trin_VstcoreProgrammingControlsExcel#12](../vsto/codesnippet/CSharp/Trin_VstcoreProgrammingControlsExcelCS/Sheet1.cs#12)]  
  
## <a name="testing-the-application"></a>응용 프로그램 테스트  
 이제 다음 사항을 확인 하려면 통합 문서를 테스트할 수 있습니다 메시지 **Hello World!** 단추를 클릭할 때 텍스트 상자에 나타납니다.  
  
#### <a name="to-test-your-workbook"></a>통합 문서를 테스트하려면  
  
1.  F5 키를 눌러 프로젝트를 실행합니다.  
  
2.  단추를 클릭합니다.  
  
3.  확인 **Hello World!** 텍스트 상자에 나타납니다.  
  
## <a name="next-steps"></a>다음 단계  
 이 연습에서는 Excel 워크시트에서 단추 및 텍스트 상자를 사용 하는 기본적인 보여 줍니다. 다음으로 수행할 수 있는 몇 가지 작업은 다음과 같습니다.  
  
-   프로젝트를 배포 합니다. 자세한 내용은 참조 [Office 솔루션 배포](../vsto/deploying-an-office-solution.md)합니다.  
  
-   확인란을 사용 하 여 서식을 변경 하 합니다. 자세한 내용은 참조 [연습: 변경 워크시트 서식을 사용 하 여 CheckBox 컨트롤](../vsto/walkthrough-changing-worksheet-formatting-using-checkbox-controls.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: Office 문서에 Windows Forms 컨트롤 추가](../vsto/how-to-add-windows-forms-controls-to-office-documents.md)   
 [Excel을 사용한 연습](../vsto/walkthroughs-using-excel.md)   
 [Office 문서에서 Windows Forms 컨트롤에 대한 제한 사항](../vsto/limitations-of-windows-forms-controls-on-office-documents.md)  
  
  