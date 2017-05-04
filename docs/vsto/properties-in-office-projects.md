---
title: "Office 프로젝트의 속성 | Microsoft Docs"
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
  - "신뢰 어셈블리 위치 속성"
  - "Cache in Document 속성"
  - "속성[Visual Studio에서 Office 개발]"
  - "호스트 항목의 네임스페이스 속성"
  - "Office 프로젝트[Visual Studio에서 Office 개발], 속성"
  - "프로젝트[Visual Studio에서 Office 개발], 속성"
  - "Value2 속성"
ms.assetid: 1284d6c3-8200-4151-88ce-0b5c7765af25
caps.latest.revision: 34
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 33
---
# Office 프로젝트의 속성
  Visual Studio에서 Office 프로젝트에 사용할 수 있는 몇 가지 중요한 속성이 있습니다. 이러한 속성은 **속성** 창에서 액세스할 수 있습니다.  
  
 [!INCLUDE[appliesto_all](../vsto/includes/appliesto-all-md.md)]  
  
## 호스트 항목의 네임스페이스  
 Visual C\# 프로젝트에서 **호스트 항목의 네임스페이스** 속성을 사용하여 호스트 항목 클래스\(예: `ThisAddIn`, `ThisWorkbook` 또는 `ThisDocument` 클래스\)의 네임스페이스를 변경할 수 있습니다. 이 속성은 **솔루션 탐색기**에서 문서 수준 프로젝트의 문서 노드\(예: ExcelWorkbook1.xlsx 또는 WordDocument1.docx\)를 선택하거나 VSTO 추가 기능 프로젝트\(예: Excel 또는 Word\)의 응용 프로그램 노드를 선택하면 **속성** 창에 나타납니다.  
  
 Visual C\# Office 프로젝트를 만들 때 프로젝트의 이름에 따라 호스트 항목에 네임스페이스가 제공됩니다. 코드 파일을 직접 편집하는 대신 **호스트 항목의 네임스페이스** 속성을 사용하여 네임스페이스를 변경하는 것이 좋습니다. 이 속성을 사용하는 경우 네임스페이스는 표시된 코드 파일뿐만 아니라 생성된\(숨겨진\) 코드 파일에서 변경됩니다.  
  
## CacheInDocument  
 **CacheInDocument** 속성은 Visual Studio 디자이너에서 <xref:System.Data.DataSet>의 인스턴스를 선택할 때 문서 수준 프로젝트의 **속성** 창에 나타납니다. 공용 멤버만 캐시될 수 있습니다. <xref:System.Data.DataSet>을 캐시하려는 경우 **Modifiers** 속성이 **Public**으로 설정되어 있는지 확인하세요.  
  
 이 속성은 부울 값을 사용합니다.  
  
-   문서에서 데이터 집합을 캐시하려면 **true**를 선택합니다.  
  
-   문서에서 데이터 집합을 캐시하지 않으려면 **false**를 선택합니다.  
  
 데이터 캐싱에 대한 자세한 내용은 [문서 수준 사용자 지정의 캐시된 데이터](../vsto/cached-data-in-document-level-customizations.md)를 참조하세요.  
  
## Value2  
 **Value2** 속성은 Excel 통합 문서 또는 서식 파일 프로젝트에만 사용할 수 있습니다. 이 속성은 워크시트 디자이너에서 <xref:Microsoft.Office.Tools.Excel.NamedRange> 컨트롤을 선택할 때 **속성** 창에서 **Databindings** 속성 노드 아래에 표시됩니다.  
  
 **속성** 창에서 **Value2** 속성을 사용하여 <xref:Microsoft.Office.Tools.Excel.NamedRange>의 <xref:Microsoft.Office.Tools.Excel.NamedRange.Value2%2A> 속성을 데이터 원본의 필드에 바인딩할 수 있습니다.  
  
## 참고 항목  
 [Office 솔루션 디자인 및 만들기](../vsto/designing-and-creating-office-solutions.md)   
 [Office 프로젝트 템플릿 개요](../vsto/office-project-templates-overview.md)   
 [Office 프로젝트의 이벤트](../vsto/events-in-office-projects.md)  
  
  