---
title: "문서 수준 사용자 지정의 캐시된 데이터"
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
  - "데이터 캐싱[Visual Studio에서 Office 개발], 데이터 캐싱 정보"
  - "데이터[Visual Studio에서 Office 개발], 캐시"
  - "데이터[Visual Studio에서 Office 개발], 문서 수준 솔루션"
  - "데이터 캐싱[Visual Studio에서 Office 개발], 데이터 캐싱 정보"
  - "데이터 아일랜드[Visual Studio에서 Office 개발]"
  - "문서 수준 사용자 지정[Visual Studio에서 Office 개발], 데이터 모델"
  - "보기[Visual Studio에서 Office 개발]"
ms.assetid: 84808462-2c5d-4dc8-ab69-491d492b4a51
caps.latest.revision: 27
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 26
---
# 문서 수준 사용자 지정의 캐시된 데이터
  문서 수준 사용자 지정의 기본 목표는 Office 문서에서 뷰와 데이터를 분리하는 것입니다.  데이터는 문서에 저장되는 숫자, 텍스트 등의 정보이며  뷰는 Microsoft Office Word 및 Microsoft Office Excel의 사용자 인터페이스 및 개체 모델입니다.  
  
 Visual Studio에서는 데이터를 *데이터 캐시*라고도 하는 *데이터 아일랜드*로 포함할 수 있도록 하여 문서 수준 사용자 지정에서 뷰와 데이터를 분리합니다.  Word 또는 Excel을 시작하지 않고도 데이터를 직접 읽거나 수정할 수 있습니다.  이 방법은 Microsoft Office가 설치되어 있지 않은 서버에서 문서의 데이터를 수정해야 하는 경우에 유용합니다.  Word 및 Excel은 서버에서 실행하기 위해 디자인된 것이 나이라 클라이언트 환경에서 사용하기 위한 것입니다.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
 문서 수준 사용자 지정에 대한 자세한 내용은 [Office 솔루션 개발 개요&#40;VSTO&#41;](../vsto/office-solutions-development-overview-vsto.md) 및 [문서 수준 사용자 지정 아키텍처](../vsto/architecture-of-document-level-customizations.md)를 참조하십시오.  
  
## 캐시된 데이터 프로그래밍 모델 이해  
 데이터 아일랜드에는 특정 요구 사항을 충족하는 솔루션의 개체가 포함될 수 있습니다.  이러한 개체로는 <xref:System.Data.DataSet> 개체 및 <xref:System.Data.DataTable> 개체와 <xref:System.Xml.Serialization.XmlSerializer> 클래스에서 serialize할 수 있는 그 밖의 개체가 있습니다.  자세한 내용은 [데이터 캐싱](../vsto/caching-data.md)을 참조하십시오.  
  
 캐시된 데이터의 뷰를 제공하려면 문서의 Windows Forms 컨트롤 및 *호스트 컨트롤*을 데이터 아일랜드의 개체에 바인딩합니다.  데이터 아일랜드와 데이터 바인딩된 컨트롤 간의 데이터 바인딩을 통해 둘 사이의 동기화가 유지됩니다.  컨트롤에 종속되지 않은 데이터에 유효성 검사 코드를 추가할 수도 있습니다.  자세한 내용은 [Office 솔루션의 컨트롤에 데이터 바인딩](../vsto/binding-data-to-controls-in-office-solutions.md)을 참조하십시오.  
  
 호스트 컨트롤은 Excel 및 Word 개체 모델에 있는 네이티브 개체의 확장된 버전입니다.  네이티브 개체와 달리 호스트 컨트롤은 관리되는 데이터 개체에 직접 바인딩할 수 있습니다.  자세한 내용은 [호스트 항목 및 호스트 컨트롤 개요](../vsto/host-items-and-host-controls-overview.md) 및 [Office 문서의 Windows Forms 컨트롤 개요](../vsto/windows-forms-controls-on-office-documents-overview.md)를 참조하십시오.  
  
## 서버의 캐시된 데이터에 액세스  
 문서의 캐시된 데이터에 액세스하려면 <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> 클래스를 사용합니다.  이 클래스는 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]의 일부로서, Excel 또는 Word를 실행하지 않고 서버에서 사용할 수 있습니다.  사용자가 캐시된 데이터를 수정한 후 문서를 열면 해당 데이터에 바인딩된 모든 컨트롤이 변경 내용과 자동으로 동기화되어 사용자에게 업데이트된 데이터가 제공됩니다.  자세한 내용은 [서버에 있는 문서의 데이터 액세스](../vsto/accessing-data-in-documents-on-the-server.md)을 참조하십시오.  
  
 Excel과 Word는 서버에서 데이터를 기록하기 위해 필요한 것이 아니라 클라이언트에서 데이터를 보기 위해서만 필요한 것입니다.  서버에 Excel과 Word를 설치할 필요도 없습니다.  이 경우 확장성이 높아지며 데이터 아일랜드가 포함된 문서를 서버에서 빠르게 일괄 처리할 수 있습니다.  
  
## 오프라인 사용을 위한 데이터 캐싱  
 데이터 아일랜드에 데이터를 저장하면 오프라인 시나리오를 사용할 수 있게 됩니다.  사용자가 처음으로 문서를 열거나 서버에 있는 문서를 요청하면 데이터 아일랜드에 최신 데이터가 채워집니다.  데이터 아일랜드가 문서에서 캐싱되면 오프라인에서 사용할 수 있습니다.  즉, 연결된 상태가 아니더라도 사용자\(또는 코드\)가 데이터를 조작할 수 있습니다.  다시 온라인 상태가 되면 데이터 변경 사항이 서버 데이터 소스에 전파될 수 있습니다.  
  
## 캐시된 데이터 및 사용자 지정 XML 부분 비교  
 사용자 지정 XML 부분은 임의의 XML 부분을 문서에 저장하기 위한 수단으로 2007 Microsoft Office system에서 도입되었습니다.  사용자 지정 XML 부분은 데이터 캐시와 동일한 여러 시나리오에서 유용하지만 데이터 아일랜드와 사용자 지정 XML 부분에는 약간의 차이점이 있습니다.  사용자 지정 XML 부분에 대한 자세한 내용은 [사용자 지정 XML 부분 개요](../vsto/custom-xml-parts-overview.md)를 참조하십시오.  
  
 다음 표에서는 몇 가지 차이점과 유사점을 보여 줍니다.  
  
||데이터 캐시|사용자 지정 XML 부분|  
|-|------------|-------------------|  
|사용할 수 있는 Office 응용 프로그램|다음 응용 프로그램의 문서 수준 사용자 지정<br /><br /> -   Excel<br />-   Word|다음 응용 프로그램의 문서 수준 및 응용 프로그램 수준 솔루션<br /><br /> -   Excel<br />-   PowerPoint<br />-   Word|  
|저장할 수 있는 데이터 형식|특정 요구 사항을 충족하는 사용자 지정 어셈블리의 공용 개체.  자세한 내용은 [데이터 캐싱](../vsto/caching-data.md)을 참조하십시오.|모든 XML 데이터|  
|Microsoft Office 응용 프로그램을 시작하지 않고 데이터에 액세스할 수 있는지 여부|가능. [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)] 런타임에서 제공하는 <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> 클래스 사용|가능. <xref:System.IO.Packaging> 네임스페이스의 클래스 또는 Open XML 형식 SDK 사용|  
  
## 참고 항목  
 [Office 솔루션의 데이터](../vsto/data-in-office-solutions.md)   
 [Visual Studio의 Office 솔루션 아키텍처](../vsto/architecture-of-office-solutions-in-visual-studio.md)  
  
  