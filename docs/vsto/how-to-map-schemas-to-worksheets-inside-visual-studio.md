---
title: "방법: Visual Studio 내에서 워크시트에 스키마 매핑 | Microsoft Docs"
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
- XML schemas [Office development in Visual Studio], mapping
- mappings [Office development in Visual Studio], XML schemas to Excel worksheets
- Excel [Office development in Visual Studio], XML schemas
- worksheets [Office development in Visual Studio], XML schemas
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: ed0da1c2ac181db93105a93dd2269be55f0379a2
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="how-to-map-schemas-to-worksheets-inside-visual-studio"></a>방법: Visual Studio 내에서 워크시트에 스키마 매핑
  Visual Studio에서 열려 있는 워크시트 동안 워크시트에 XML 스키마를 매핑할 수 있습니다. 통합 문서 Visual Studio 외부에서 열릴 때 사용 하는 동일한 Microsoft Office Excel 도구를 사용 합니다. Office 프로젝트 이전 워크시트에 스키마 매핑 여부 Excel 솔루션을 만든 후 동일한 개체를 만듭니다.  
  
 [!INCLUDE[appliesto_xlalldoc](../vsto/includes/appliesto-xlalldoc-md.md)]  
  
> [!NOTE]  
>  Excel 솔루션에서 다중 파트 XML 스키마를 사용할 수 없습니다.  
  
### <a name="to-map-an-xml-schema-to-an-excel-worksheet-in-visual-studio"></a>Visual Studio에서 Excel 워크시트에 XML 스키마를 매핑할  
  
1.  Visual Studio 내의 Excel 통합 문서 또는 서식 파일 프로젝트를 엽니다.  
  
2.  디자이너에 포커스를 이동 하기 위해 워크시트에서 여기를 클릭 합니다.  
  
3.  리본에서 **개발자** 탭을 클릭합니다.  
  
    > [!NOTE]  
    >  **개발자** 탭이 표시되지 않는 경우 먼저 개발자 탭을 표시해야 합니다. 자세한 내용은 [How to: Show the Developer Tab on the Ribbon](../vsto/how-to-show-the-developer-tab-on-the-ribbon.md)을 참조하세요.  
  
4.  에 **XML** 그룹에서 클릭 **소스**합니다.  
  
     **XML 원본은** 창이 열립니다.  
  
5.  에 **XML 원본은** 창 클릭 **XML 맵**합니다.  
  
     **XML 맵** 대화 상자가 열립니다.  
  
6.  에 **XML 맵** 대화 상자를 클릭 **추가**합니다.  
  
7.  스키마 파일을 찾아를 선택한 다음 클릭 **열려**합니다.  
  
8.  **확인**을 클릭합니다.  
  
     에 스키마가 표시 된 **XML 원본** 창. 형식화 된 프로젝트에서 <xref:System.Data.DataSet> 스키마를 기반으로 생성 되는 및 <xref:System.Windows.Forms.BindingSource> 만들어집니다.  
  
9. 요소를 끌어는 **XML 원본은** 워크시트에 해당 컨트롤을 만들 위치를 창.  
  
     Office 프로젝트는 생성-반복 되지 않는 스키마 요소를 끌어 오면는 <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> 에 자동으로 바인딩되는 컨트롤의 <xref:System.Windows.Forms.BindingSource>합니다.  
  
     Office 프로젝트는 생성 반복 스키마 요소를 끌어 오면는 <xref:Microsoft.Office.Tools.Excel.ListObject> 데이터 원본에 자동으로 바인딩되지 않은 컨트롤입니다. 자세한 내용은 참조 [XML 스키마 및 문서 수준 사용자 지정에서 데이터](../vsto/xml-schemas-and-data-in-document-level-customizations.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [방법: Visual Studio 내부의 Word 문서에 스키마 매핑](../vsto/how-to-map-schemas-to-word-documents-inside-visual-studio.md)   
 [문서 수준 사용자 지정의 XML 스키마 및 데이터](../vsto/xml-schemas-and-data-in-document-level-customizations.md)  
  
  