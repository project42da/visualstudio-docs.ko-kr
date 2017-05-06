---
title: "방법: 오프라인이나 서버에서 사용할 데이터 캐싱"
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
  - "데이터[Visual Studio에서 Office 개발], 캐싱"
  - "데이터 캐싱[Visual Studio에서 Office 개발], 오프라인 사용"
  - "데이터 캐싱[Visual Studio에서 Office 개발], 서버 사용"
  - "데이터 집합[Visual Studio에서 Office 개발], 캐싱"
  - "Office 응용 프로그램[Visual Studio에서 Office 개발], 데이터"
  - "오프라인 데이터[Visual Studio에서 Office 개발]"
ms.assetid: 6246b187-9413-4336-821d-2259b1adec5a
caps.latest.revision: 49
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 48
---
# 방법: 오프라인이나 서버에서 사용할 데이터 캐싱
  데이터 항목을 문서에서 캐시하도록 표시하여 오프라인에서 사용할 수 있습니다.  이렇게 하면 문서가 서버에 저장되어 있는 경우 문서의 데이터를 다른 코드로 조작할 수도 있습니다.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
 코드에서 데이터 항목을 선언한 경우 해당 데이터 항목을 캐시하도록 표시할 수 있으며, <xref:System.Data.DataSet>를 사용하는 경우에는 **속성** 창에서 속성을 설정하여 이를 표시할 수 있습니다.  <xref:System.Data.DataSet> 또는 <xref:System.Data.DataTable>이 아닌 데이터 항목을 캐시하려면 해당 데이터 항목이 문서에서 캐시될 수 있는 조건을 충족하는지 확인합니다.  자세한 내용은 [데이터 캐싱](../vsto/caching-data.md)을 참조하십시오.  
  
> [!NOTE]  
>  Visual Basic에서 **Cached** 및 **WithEvents**로 표시하여 만든 데이터 집합과 **CacheInDocument** 속성을 **True**로 설정하여 **데이터 소스** 창이나 **도구 상자**에서 끌어 놓은 데이터 집합의 캐시 이름 앞에는 밑줄\(\_\)이 추가됩니다.  예를 들어 데이터 집합을 만들고 그 이름을 Customers로 지정한 경우 캐시에서 <xref:Microsoft.VisualStudio.Tools.Applications.CachedDataItem> 이름은 \_Customers가 됩니다.  <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument>를 사용하여 이 캐시된 항목에 액세스하는 경우 Customers가 아닌 \_Customers를 지정해야 합니다.  
  
### 코드를 사용하여 문서에서 데이터를 캐시하려면  
  
1.  프로젝트에서 데이터 항목의 공용 필드 또는 속성을 `ThisDocument` 클래스\(Word 프로젝트의 경우\) 또는 `ThisWorkbook` 클래스\(Excel 프로젝트의 경우\)와 같은 호스트 항목 클래스의 멤버로 선언합니다.  
  
2.  이 멤버에 <xref:Microsoft.VisualStudio.Tools.Applications.Runtime.CachedAttribute> 특성을 적용하여 데이터 항목을 문서의 데이터 캐시에 저장하도록 표시합니다.  다음 예제에서는 <xref:System.Data.DataSet>에 대한 필드 선언에 이 특성을 적용합니다.  
  
     [!code-csharp[Trin_VstcoreDataExcel#11](../snippets/csharp/VS_Snippets_OfficeSP/Trin_VstcoreDataExcel/CS/Sheet1.cs#11)]
     [!code-vb[Trin_VstcoreDataExcel#11](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_VstcoreDataExcel/VB/Sheet1.vb#11)]  
  
3.  데이터 항목의 인스턴스를 만들고 해당되는 경우 이를 데이터베이스에서 로드하는 코드를 추가합니다.  
  
     데이터 항목은 해당 항목을 처음 만들 때만 로드됩니다. 이후에는 문서와 함께 캐시가 유지되므로 이를 업데이트하려면 다른 코드를 작성해야 합니다.  
  
### 속성 창을 사용하여 문서에서 데이터 집합을 캐시하려면  
  
1.  Visual Studio 디자이너의 도구를 사용하여 프로젝트에 데이터 집합을 추가합니다. 예를 들어 **데이터 소스** 창을 사용하여 프로젝트에 데이터 소스를 추가합니다.  
  
2.  데이터 집합의 인스턴스가 하나도 없으면 이를 만들고 디자이너에서 인스턴스를 선택합니다.  
  
3.  **속성** 창에서 **CacheInDocument** 속성을 **True**로 설정합니다.  
  
     자세한 내용은 [Office 프로젝트의 속성](../vsto/properties-in-office-projects.md)을 참조하십시오.  
  
4.  **속성** 창에서 **Modifiers** 속성을 **Public**으로 설정합니다. 기본값은 **Internal**입니다.  
  
## 참고 항목  
 [데이터 캐싱](../vsto/caching-data.md)   
 [방법: Office 문서에서 프로그래밍 방식으로 데이터 소스 캐싱](../vsto/how-to-programmatically-cache-a-data-source-in-an-office-document.md)   
 [방법: 암호로 보호된 문서의 데이터 캐시](../vsto/how-to-cache-data-in-a-password-protected-document.md)   
 [서버에 있는 문서의 데이터 액세스](../vsto/accessing-data-in-documents-on-the-server.md)   
 [데이터 저장](../data-tools/saving-data.md)  
  
  