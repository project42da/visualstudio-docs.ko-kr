---
title: "문서 수준 사용자 지정의 XML 스키마 및 데이터 | Microsoft Docs"
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
  - "Visual Studio에서 Office 개발, XML"
  - "스키마[Visual Studio에서 Office 개발]"
  - "XML[Visual Studio에서 Office 개발], XML 스키마"
  - "XML 스키마[Visual Studio에서 Office 개발]"
  - "XML 스키마[Visual Studio에서 Office 개발], XML 스키마 및 데이터 정보"
ms.assetid: 74bd5773-6cb0-44fb-9738-75e2f2c6e48d
caps.latest.revision: 28
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 27
---
# 문서 수준 사용자 지정의 XML 스키마 및 데이터
  **중요 한** Microsoft Word와 관련 된이 항목에 설정 된 정보 혜택 및 개인과 누가 미국과 해당 영토 밖에 위치한 되 나 누구를 사용 하 여 또는 2010 년 1 월 Microsoft 제거 경우 Microsoft Word에서 사용자 지정 XML에 관련 된 특정 기능을 구현 하기 전에 Microsoft에서 사용이 허가 된 제품을 Microsoft Word를 실행 하는 프로그램 개발 회사의 사용에 대 한 독점적으로 제공 됩니다.  Microsoft Word에 대한 정보는 2010년 1월 10일 이후 Microsoft에서 사용 허가를 받고 Microsoft Word에서 실행되는 프로그램을 사용 또는 개발하고 있는 미국 또는 미국 자치령의 개인 또는 조직에서 읽거나 사용하지 못할 수 있습니다. 이런 제품은 해당 날짜 이전에 사용 허가를 받거나 미국이 아닌 다른 곳에서 사용하기 위해 구매하고 사용 허가를 받은 동일한 제품처럼 작동하지 않습니다.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
 Microsoft Office Excel 및 Microsoft Office Word에서는 스키마를 문서에 매핑할 수 있는 기능을 제공합니다.  이 기능을 사용하면 간편하게 XML 데이터를 문서에 가져오거나 문서에서 XML 데이터를 내보낼 수 있습니다.  
  
 Visual Studio에서는 문서 수준 사용자 지정의 매핑된 스키마 요소를 프로그래밍 모델에 컨트롤로 노출합니다.  Excel의 경우 Visual Studio는 데이터베이스, 웹 서비스 및 개체의 데이터에 대한 컨트롤 바인딩을 지원합니다.  Visual Studio는 최종 사용자가 Word 및 Excel 솔루션을 더욱 편리하게 사용할 수 있도록 스키마 매핑된 문서와 함께 사용할 수 있는 작업 창을 지원합니다.  자세한 내용은 [작업 창 개요](../vsto/actions-pane-overview.md)을 참조하십시오.  
  
> [!NOTE]  
>  multipart XML 스키마는 Excel 솔루션에서 사용할 수 없습니다.  
  
## 스키마를 Excel 통합 문서에 연결할 때 작성되는 개체  
 통합 문서에 스키마를 연결하면 Visual Studio에서는 여러 개의 개체를 자동으로 만들고 프로젝트에 해당 개체를 추가합니다.  이러한 개체는 Excel에서 관리하므로 Visual Studio 도구를 사용하여 삭제하지 말아야 합니다.  이러한 개체를 삭제하려면 워크시트에서 매핑된 요소를 제거하거나 Excel 도구를 사용하여 스키마를 연결 해제해야 합니다.  
  
 다음 두 개의 주 개체가 있습니다.  
  
-   XML 스키마\(XSD 파일\).  통함 문서의 모든 스키마에 대해 Visual Studio는 스키마를 프로젝트에 추가합니다.  이 스키마는 **솔루션 탐색기**에서 XSD 확장명이 있는 프로젝트 항목으로 표시됩니다.  
  
-   형식화된 <xref:System.Data.DataSet> 클래스.  이 클래스는 스키마를 기반으로 만들어집니다.  이 데이터 집합 클래스는 **클래스 뷰**에 표시됩니다.  
  
## 스키마 요소를 Excel 워크시트에 매핑할 때 작성되는 개체  
 스키마 요소를 **XML 소스** 작업 창에서 워크시트에 매핑하면 Visual Studio에서는 다음과 같이 여러 개체를 자동으로 만들고 프로젝트에 추가합니다.  
  
-   컨트롤.  통합 문서에 매핑된 각 개체에 대해 <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> 컨트롤\(반복되지 않는 스키마 요소\) 또는 <xref:Microsoft.Office.Tools.Excel.ListObject> 컨트롤\(반복되는 스키마 요소\)이 프로그래밍 모델에 만들어집니다.  <xref:Microsoft.Office.Tools.Excel.ListObject> 컨트롤을 삭제하려면 통합 문서에서 매핑과 매핑된 개체를 삭제해야 합니다.  컨트롤에 대한 자세한 내용은 [호스트 항목 및 호스트 컨트롤 개요](../vsto/host-items-and-host-controls-overview.md)를 참조하십시오.  
  
-   BindingSource.  반복되지 않는 스키마 요소를 워크시트에 매핑하여 <xref:Microsoft.Office.Tools.Excel.XmlMappedRange>를 만들면 <xref:System.Windows.Forms.BindingSource>가 만들어지고 <xref:Microsoft.Office.Tools.Excel.XmlMappedRange> 컨트롤이 <xref:System.Windows.Forms.BindingSource>에 바인딩됩니다.  <xref:System.Windows.Forms.BindingSource>는 형식화하여 작성된 <xref:System.Data.DataSet> 클래스의 인스턴스 같이 문서에 매핑된 스키마에 일치하는 데이터 소스의 인스턴스에 바인딩해야 합니다.  **속성** 창에 노출된 <xref:System.Windows.Forms.BindingSource.DataSource%2A> 및 <xref:System.Windows.Forms.BindingSource.DataMember%2A> 속성을 설정하여 바인딩을 만듭니다.  
  
    > [!NOTE]  
    >  <xref:System.Windows.Forms.BindingSource>는 <xref:Microsoft.Office.Tools.Excel.ListObject> 개체에 대해 만들어지지 않습니다.  **속성** 창의 <xref:System.Windows.Forms.BindingSource.DataSource%2A> 및 <xref:System.Windows.Forms.BindingSource.DataMember%2A> 속성을 설정하여 <xref:Microsoft.Office.Tools.Excel.ListObject>를 데이터 소스에 수동으로 바인딩해야 합니다.  
  
### Office의 매핑된 스키마와 Visual Studio 데이터 소스 창  
 Office의 매핑된 스키마 기능과 Visual Studio **데이터 소스** 창을 사용하면 보고하거나 편집하기 위한 데이터를 Excel 워크시트에 쉽게 표시할 수 있습니다.  두 경우 모두 데이터 요소를 Excel 워크시트로 끌 수 있습니다.  어떠한 방법을 사용하건 <xref:System.Data.DataSet> 또는 웹 서비스 같은 데이터 소스에 <xref:System.Windows.Forms.BindingSource>를 통해 데이터 바인딩되는 컨트롤이 작성됩니다.  
  
> [!NOTE]  
>  반복되는 스키마 요소를 워크시트에 매핑하면 Visual Studio에서는 <xref:Microsoft.Office.Tools.Excel.ListObject>를 만듭니다.  <xref:Microsoft.Office.Tools.Excel.ListObject>는 <xref:System.Windows.Forms.BindingSource>를 통해 데이터에 자동으로 바인딩되지 않습니다.  **속성** 창의 <xref:System.Windows.Forms.BindingSource.DataSource%2A> 및 <xref:System.Windows.Forms.BindingSource.DataMember%2A> 속성을 설정하여 <xref:Microsoft.Office.Tools.Excel.ListObject>를 데이터 소스에 수동으로 바인딩해야 합니다.  
  
 다음 표에서는 두 방법 사이의 몇 가지 차이를 보여 줍니다.  
  
|XML 스키마|데이터 소스 창|  
|-------------|--------------|  
|Office 인터페이스를 사용합니다.|Visual Studio의 **데이터 소스** 창을 사용합니다.|  
|XML 파일에서 데이터를 가져오고 내보내기 위한 기본 제공 Office 기능을 활성화합니다.|프로그래밍 방식으로 가져오기 및 내보내기 기능을 제공해야 합니다.|  
|데이터로 생성된 컨트롤을 채우기 위한 코드를 작성해야 합니다.|**데이터 소스** 창에서 추가된 컨트롤에는 이를 채우기 위한 코드가 데이터베이스 서버에서 사용할 때 필요한 연결 문자열과 함께 자동으로 생성됩니다.|  
  
## 스키마를 Word 문서에 연결할 때의 동작  
 문서 수준 Office 프로젝트에 사용되는 Word 문서에 스키마를 연결할 때는 데이터 개체가 작성되지 않습니다.  그러나 스키마 요소를 문서에 매핑하면 컨트롤이 작성됩니다.  컨트롤 형식은 매핑하는 요소의 형식에 따라 달라집니다. 반복되는 요소는 <xref:Microsoft.Office.Tools.Word.XMLNodes> 컨트롤을 생성하고, 반복되지 않는 요소는 <xref:Microsoft.Office.Tools.Word.XMLNode> 컨트롤을 생성합니다.  자세한 내용은 [XMLNodes 컨트롤](../vsto/xmlnodes-control.md) 및 [XMLNode 컨트롤](../vsto/xmlnode-control.md)를 참조하십시오.  
  
## XML 스키마가 포함된 솔루션 배포  
 문서에 매핑된 XML 스키마를 사용하는 솔루션을 배포하려면 설치 관리자를 만들어야 합니다.  이 설치 관리자는 사용자 컴퓨터의 스키마 라이브러리에 해당 스키마를 등록해야 합니다.  스키마를 등록하지 않아도 솔루션은 실행됩니다. 사용자가 문서를 열면 이 문서의 요소를 기반으로 Word에서 임시 스키마가 생성되기 때문입니다.  그러나 이 경우 프로젝트를 만드는 데 사용한 스키마의 유효성을 검사하거나 이 스키마를 저장할 수는 없습니다.  설치 관리자에 대한 자세한 내용은 [응용 프로그램, 서비스 및 구성 요소 배포](../deployment/deploying-applications-services-and-components.md)를 참조하십시오.  
  
 스키마가 라이브러리에 있고 등록되어 있는지 검사하기 위한 코드를 프로젝트에 추가할 수도 있습니다.  스키마가 등록되어 있지 않으면 사용자에게 경고 메시지를 표시할 수 있습니다.  
  
 [!code-csharp[Trin_VstcoreDataWord#1](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreDataWord/CS/ThisDocument.cs#1)]
 [!code-vb[Trin_VstcoreDataWord#1](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreDataWord/VB/ThisDocument.vb#1)]  
  
## 참고 항목  
 [방법: Visual Studio 내부의 Word 문서에 스키마 매핑](../vsto/how-to-map-schemas-to-word-documents-inside-visual-studio.md)   
 [방법: Visual Studio 내에서 워크시트에 스키마 매핑](../vsto/how-to-map-schemas-to-worksheets-inside-visual-studio.md)  
  
  