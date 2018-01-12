---
title: "문서 수준 사용자 지정에서 데이터 및 XML 스키마 | Microsoft Docs"
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
- XML schemas [Office development in Visual Studio]
- schemas [Office development in Visual Studio]
- XML [Office development in Visual Studio], XML schemas
- XML schemas [Office development in Visual Studio], about XML schemas and data
- Office development in Visual Studio, XML
author: TerryGLee
ms.author: tglee
manager: ghogen
ms.workload: office
ms.openlocfilehash: b3f55c8c6b2975e8dbaa85177fddcadaf62e000e
ms.sourcegitcommit: f9fbf1f55f9ac14e4e5c6ae58c30dc1800ca6cda
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/10/2018
---
# <a name="xml-schemas-and-data-in-document-level-customizations"></a>문서 수준 사용자 지정의 XML 스키마 및 데이터
  **중요 한** Microsoft Word에 대 한이 항목에 정보는 이점과 개인 및 United States 및 해당 지역 외부에 있는 사용자 또는 사용자를 사용 하는 조직의 사용에 대해 독점적으로 발표 된 또는 개발 실행 되는 프로그램, Microsoft Word 2010 년 1 월, Microsoft 구현의 특정 기능을 제거 하는 경우 하기 전에 Microsoft에서 사용이 허가 된 제품에서에서와 관련 된 사용자 지정 XML Microsoft Word입니다. Microsoft Word에 대 한이 정보를 읽거나 개인 이나 조직에는 미국이 나 Microsoft Word 2010 년 1 월 10 일 이후에 Microsoft에서 사용이 허가 된 제품에서 실행 되는 프로그램을 개발 하거나를 사용 하는 사용자의 지역에서 사용 될 수 있습니다. ; 이러한 제품 해당 날짜 이전에 사용이 허가 또는 구입 해야 하 고 미국 이외의 용도로 사용이 허가 된 제품와 동일 하 게 작동 하지 않습니다.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
 Microsoft Office Excel 및 Microsoft Office Word 문서에 스키마 매핑 수 있는 기능을 제공 합니다. 이 기능은 가져오거나는 문서에서 XML 데이터 가져오기 및 내보내기 단순화할 수 있습니다.  
  
 프로그래밍 모델에서 컨트롤로 매핑된 문서 수준 사용자 지정에서 스키마 요소를 visual Studio 노출 합니다. Excel의 경우 Visual Studio에서는 데이터베이스, 웹 서비스 및 개체의 데이터에 컨트롤 바인딩을 지원을 합니다. Word 및 Excel에 대 한 Visual Studio 솔루션에는 향상 된 최종 사용자 환경을 제공 하는 스키마로 매핑된 문서와 함께 사용할 수 있는 작업 창에 대 한 지원을 추가 합니다. 자세한 내용은 [Actions Pane Overview](../vsto/actions-pane-overview.md)을 참조하십시오.  
  
> [!NOTE]  
>  Excel 솔루션에서 다중 파트 XML 스키마를 사용할 수 없습니다.  
  
## <a name="objects-created-when-schemas-are-attached-to-excel-workbooks"></a>스키마를 Excel 통합 문서에 첨부할 때 작성 개체  
 통합 문서에 스키마를 연결 하면 Visual Studio가 자동으로 여러 개체를 만든 고 프로젝트에 추가 합니다. 이러한 개체 삭제 해서는 Visual Studio 도구를 사용 하 여 Excel에서 관리 됩니다. 를 삭제 하려면 워크시트에서 매핑된 요소를 제거 하거나 Excel 도구를 사용 하 여 스키마를 분리 합니다.  
  
 두 가지 주요 개체:  
  
-   XML 스키마 (XSD 파일)입니다. 통합 문서에서 모든 스키마에 대해 Visual Studio 프로젝트에 스키마를 추가합니다. XSD 확장명을 가진 프로젝트 항목으로 표시 됨 **솔루션 탐색기**합니다.  
  
-   형식화된 <xref:System.Data.DataSet> 클래스. 이 클래스는 스키마에 따라 생성 됩니다. 이 데이터 집합 클래스에 표시 됩니다. **클래스 뷰**합니다.  
  
## <a name="objects-created-when-schema-elements-are-mapped-to-excel-worksheets"></a>스키마 요소는 Excel 워크시트에 매핑 했으면 작성 개체  
 스키마 요소를 매핑할 때의 **XML 원본은** 워크시트, Visual Studio에 작업 창에서 자동으로 여러 개체를 만든 하 고 프로젝트에 추가 합니다.  
  
-   제어 합니다. 통합 문서에 매핑된 각 개체에 대 한는 <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> 제어 (-반복 되지 않는 스키마 요소) 또는 <xref:Microsoft.Office.Tools.Excel.ListObject> 제어 (반복 되는 스키마 요소) 프로그래밍 모델에서 만들어집니다. <xref:Microsoft.Office.Tools.Excel.ListObject> 만 통합 문서에서 매핑과 매핑된 개체를 삭제 하 여 컨트롤을 삭제할 수 있습니다. 컨트롤에 대 한 자세한 내용은 참조 [호스트 항목 및 호스트 컨트롤 개요](../vsto/host-items-and-host-controls-overview.md)합니다.  
  
-   BindingSource입니다. 만들 때는 <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> 워크시트에는 반복 되지 않는 스키마 요소를 매핑하는 방법으로 <xref:System.Windows.Forms.BindingSource> 만들어집니다 및 <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> 컨트롤이 바인딩되는 <xref:System.Windows.Forms.BindingSource>합니다. 바인딩해야는 <xref:System.Windows.Forms.BindingSource> 형식화 된 인스턴스와 같은 문서에 매핑된 스키마와 일치 하는 데이터 원본의 인스턴스에 <xref:System.Data.DataSet> 생성 된 클래스입니다. 설정 하 여 바인딩을 만듭니다는 <xref:System.Windows.Forms.BindingSource.DataSource%2A> 및 <xref:System.Windows.Forms.BindingSource.DataMember%2A> 에 노출 된 속성의 **속성** 창.  
  
    > [!NOTE]  
    >  <xref:System.Windows.Forms.BindingSource> 자동으로 만들어지지는지 않습니다 <xref:Microsoft.Office.Tools.Excel.ListObject> 개체입니다. 에 수동으로 바인딩해야는 <xref:Microsoft.Office.Tools.Excel.ListObject> 설정 하 여 데이터 원본에는 <xref:System.Windows.Forms.BindingSource.DataSource%2A> 및 <xref:System.Windows.Forms.BindingSource.DataMember%2A> 속성에는 **속성** 창.  
  
### <a name="office-mapped-schemas-and-the-visual-studio-data-sources-window"></a>Office 매핑된 스키마와 Visual Studio 데이터 소스 창  
 Office 및 Visual Studio의 매핑된 스키마 기능 **데이터 소스** 창 수를 보고 편집 하거나 Excel 워크시트에서 데이터를 표시 합니다. 두 경우 모두 데이터 요소 Excel 워크시트로 끌 수 있습니다. 두 방법 모두 데이터를 통해 바인딩된 컨트롤을 만들는 <xref:System.Windows.Forms.BindingSource> 와 같은 데이터 원본에는 <xref:System.Data.DataSet> 또는 웹 서비스입니다.  
  
> [!NOTE]  
>  워크시트에 반복 되는 스키마 요소를 매핑하는 경우에 Visual Studio 만들어집니다는 <xref:Microsoft.Office.Tools.Excel.ListObject>합니다. <xref:Microsoft.Office.Tools.Excel.ListObject> 를 통해 데이터에 자동으로 바인딩되지 않은 <xref:System.Windows.Forms.BindingSource>합니다. 에 수동으로 바인딩해야는 <xref:Microsoft.Office.Tools.Excel.ListObject> 설정 하 여 데이터 원본에는 <xref:System.Windows.Forms.BindingSource.DataSource%2A> 및 <xref:System.Windows.Forms.BindingSource.DataMember%2A> 속성에는 **속성** 창.  
  
 다음 표에서 두 방법 간의 차이점 중 일부를 보여 줍니다.  
  
|XML 스키마|데이터 소스 창|  
|----------------|-------------------------|  
|Office 인터페이스를 사용합니다.|사용 하 여 **데이터 소스** Visual Studio의 창.|  
|가져오기 및 XML 파일에서 데이터 내보내기 기본 제공 Office 기능을 사용할 수 있습니다.|기능을 프로그래밍 방식으로 내보내기 및 가져오기를 제공 해야 합니다.|  
|생성된 된 컨트롤을 데이터로 채우는 코드를 작성 해야 합니다.|추가 된 컨트롤의 **데이터 소스** 창 채우려는 데이터베이스 서버에서 사용할 때 필요한 연결 문자열과 함께 자동으로 생성 된 코드는 필요한 합니다.|  
  
## <a name="behavior-when-schemas-are-attached-to-word-documents"></a>스키마를 Word 문서에 첨부할 때의 동작  
 문서 수준 Office 프로젝트에서 사용 되는 Word 문서에 스키마를 연결 하는 경우에 데이터 개체 만들어지지 않습니다. 그러나 문서에는 스키마 요소를 매핑할 때 컨트롤이 만들어집니다. 컨트롤 형식의 어떤 유형의 매핑할; 요소에 따라 달라 집니다. 요소 생성 반복 <xref:Microsoft.Office.Tools.Word.XMLNodes> 컨트롤과 생성-반복 되지 않는 요소 <xref:Microsoft.Office.Tools.Word.XMLNode> 컨트롤입니다. 자세한 내용은 참조 [XMLNodes 컨트롤](../vsto/xmlnodes-control.md) 및 [XMLNode 컨트롤](../vsto/xmlnode-control.md)합니다.  
  
## <a name="deployment-of-solutions-that-include-xml-schemas"></a>XML 스키마가 포함 된 솔루션 배포  
 문서에 매핑되는 XML 스키마를 사용 하는 솔루션을 배포 하려면 설치 관리자를 만들어야 합니다. 설치 관리자는 사용자의 컴퓨터에 스키마 라이브러리에서 스키마를 등록 해야 합니다. 스키마를 등록 하면 Word에서 사용자가 열 때 문서에 있는 요소를 기반으로 임시 스키마를 생성 하기 때문에 솔루션은 계속 작동 합니다. 그러나 사용자에 대해 또는 프로젝트를 만드는 데 사용 하는 스키마를 저장 하는 유효성 검사를 수행할 수 없습니다. 설치 관리자에 대 한 자세한 내용은 참조 [응용 프로그램 배포, 서비스 및 구성 요소](/visualstudio/deployment/deploying-applications-services-and-components)합니다.  
  
 스키마 라이브러리에 등록 되어 있는지 여부를 확인 하 여 프로젝트에 코드를 추가할 수 있습니다. 그렇지 않은 경우 사용자를 경고할 수 있습니다.  
  
 [!code-vb[Trin_VstcoreDataWord#1](../vsto/codesnippet/VisualBasic/Trin_VstcoreDataWordVB/ThisDocument.vb#1)]
 [!code-csharp[Trin_VstcoreDataWord#1](../vsto/codesnippet/CSharp/Trin_VstcoreDataWordCS/ThisDocument.cs#1)]  
  
## <a name="see-also"></a>참고 항목  
 [방법: Visual Studio 내부의 Word 문서에 스키마 매핑](../vsto/how-to-map-schemas-to-word-documents-inside-visual-studio.md)   
 [방법: Visual Studio 내에서 워크시트에 스키마 매핑](../vsto/how-to-map-schemas-to-worksheets-inside-visual-studio.md)  
  
  