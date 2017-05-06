---
title: "서버에 있는 문서의 데이터 액세스"
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
  - "데이터[Visual Studio에서 Office 개발], 서버에서 액세스"
  - "데이터 액세스[Visual Studio에서 Office 개발]"
ms.assetid: 14a42e96-ed2f-48a1-a0c0-e19f9eba4956
caps.latest.revision: 32
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 31
---
# 서버에 있는 문서의 데이터 액세스
  Microsoft Office Word 또는 Microsoft Office Excel의 개체 모델을 사용하지 않고도 문서 수준 사용자 지정의 데이터를 대상으로 프로그래밍 작업을 할 수 있습니다.  즉, Word 또는 Excel이 설치되어 있지 않은 서버의 문서에 포함된 데이터에 액세스할 수 있습니다.  예를 들어 서버의 코드\(예: [!INCLUDE[vstecasp](../sharepoint/includes/vstecasp-md.md)] 페이지의 코드\)에서 문서의 데이터를 사용자 지정하고 이렇게 사용자 지정된 문서를 최종 사용자에게 보낼 수 있습니다.  최종 사용자가 문서를 열면 사용자 지정된 데이터가 솔루션 어셈블리의 데이터 바인딩 코드를 통해 문서에 바인딩됩니다.  이는 문서의 데이터가 사용자 인터페이스와 구분되어 있기 때문에 가능합니다.  자세한 내용은 [문서 수준 사용자 지정의 캐시된 데이터](../vsto/cached-data-in-document-level-customizations.md)을 참조하십시오.  
  
 [!INCLUDE[appliesto_alldoc](../vsto/includes/appliesto-alldoc-md.md)]  
  
## 서버에서 사용할 데이터 캐싱  
 문서의 데이터 개체를 캐시하려면 디자인 타임에 해당 데이터 개체를 <xref:Microsoft.VisualStudio.Tools.Applications.Runtime.CachedAttribute> 특성으로 표시하거나 런타임에 호스트 항목의 `StartCaching` 메서드를 사용합니다.  데이터 개체를 문서에 캐시하면 [!INCLUDE[vsto_runtime](../vsto/includes/vsto-runtime-md.md)]에서는 개체를 문서에 저장된 XML 문자열로 serialize합니다.  개체는 특정 요구 사항을 충족해야 캐시할 수 있습니다.  자세한 내용은 [데이터 캐싱](../vsto/caching-data.md)을 참조하십시오.  
  
 서버 쪽 코드에서는 데이터 캐시의 모든 데이터 개체를 조작할 수 있습니다.  캐시된 데이터 인스턴스에 바인딩되는 컨트롤은 사용자 인터페이스와 동기화되므로 클라이언트에서 문서를 열 때 데이터에 대한 모든 서버 쪽 변경 내용이 자동으로 표시됩니다.  
  
## 캐시의 데이터에 액세스  
 콘솔 응용 프로그램, Windows Forms 응용 프로그램 또는 웹 페이지 같은 Office 이외의 응용 프로그램에서 캐시의 데이터에 액세스할 수 있습니다.  캐시된 데이터에 액세스하는 응용 프로그램에는 완전 신뢰가 필요합니다. 부분 신뢰 웹 응용 프로그램을 사용하면 Office 문서에서 캐시된 데이터를 삽입, 검색 또는 변경할 수 없습니다.  
  
 데이터 캐시는 <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> 클래스의 <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.CachedData%2A> 속성에 의해 노출되는 컬렉션 계층 구조를 통해 액세스할 수 있습니다.  
  
-   <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.CachedData%2A> 속성은 문서 수준 사용자 지정의 모든 캐시된 데이터를 포함하는 <xref:Microsoft.VisualStudio.Tools.Applications.CachedData>를 반환합니다.  
  
-   각 <xref:Microsoft.VisualStudio.Tools.Applications.CachedData>에는 하나 이상의 <xref:Microsoft.VisualStudio.Tools.Applications.CachedDataHostItem> 개체가 포함됩니다.  <xref:Microsoft.VisualStudio.Tools.Applications.CachedDataHostItem>에는 단일 클래스에 정의된 모든 캐시된 데이터 개체가 포함됩니다.  
  
-   각 <xref:Microsoft.VisualStudio.Tools.Applications.CachedDataHostItem>에는 하나 이상의 <xref:Microsoft.VisualStudio.Tools.Applications.CachedDataItem> 개체가 포함됩니다.  <xref:Microsoft.VisualStudio.Tools.Applications.CachedDataItem>은 캐시된 단일 데이터 개체를 나타냅니다.  
  
 다음 코드 예제에서는 Excel 통합 문서 프로젝트의 `Sheet1` 클래스에 있는 캐시된 문자열에 액세스하는 방법을 보여 줍니다.  이 예제는 <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.Save%2A> 메서드에 대해 제공되는 보다 큰 예제의 일부입니다.  
  
 [!code-csharp[Trin_ServerDocument#12](../snippets/csharp/VS_Snippets_OfficeSP/Trin_ServerDocument/CS/Form1.cs#12)]
 [!code-vb[Trin_ServerDocument#12](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_ServerDocument/VB/Form1.vb#12)]  
  
## 캐시의 데이터 수정  
 캐시된 데이터 개체를 수정하려면 일반적으로 다음 단계를 수행합니다.  
  
1.  캐시된 개체의 XML 표현을 개체의 새 인스턴스로 deserialize합니다.  캐시된 데이터 개체를 나타내는 <xref:Microsoft.VisualStudio.Tools.Applications.CachedDataItem>의 <xref:Microsoft.VisualStudio.Tools.Applications.CachedDataItem.Xml%2A> 속성을 사용하여 XML에 액세스할 수 있습니다.  
  
2.  이 복사본에 대한 변경 작업을 수행합니다.  
  
3.  다음 옵션 중 하나를 사용하여 변경된 개체를 다시 데이터 캐시로 serialize합니다.  
  
    -   변경 내용을 자동으로 serialize하려면 <xref:Microsoft.VisualStudio.Tools.Applications.CachedDataItem.SerializeDataInstance%2A> 메서드를 사용합니다.  이 메서드는 **DiffGram** 형식을 사용하여 <xref:System.Data.DataSet>, <xref:System.Data.DataTable> 및 형식화된 데이터 집합 개체를 데이터 캐시에 serialize합니다.  **DiffGram** 형식을 사용하면 오프라인 문서에서 데이터 캐시를 변경한 내용이 서버에 올바르게 전달됩니다.  
  
    -   고유한 방식으로 변경 사항을 캐시된 데이터로 serialize하려는 경우 <xref:Microsoft.VisualStudio.Tools.Applications.CachedDataItem.Xml%2A> 속성에 직접 씁니다.  <xref:System.Data.Common.DataAdapter>를 사용하여 <xref:System.Data.DataSet>, <xref:System.Data.DataTable> 또는 형식화된 데이터 집합의 데이터에 대한 변경 내용으로 데이터베이스를 업데이트하는 경우 **DiffGram** 형식을 지정합니다.  그렇지 않으면 <xref:System.Data.Common.DataAdapter>가 기존 행을 수정하는 대신 새 행을 추가하여 데이터베이스를 업데이트합니다.  
  
### 현재 값을 deserialize하지 않고 데이터 수정  
 현재 값을 먼저 deserialize하지 않고 캐시된 개체의 값을 수정하려는 경우가 있습니다.  예를 들어 문자열 또는 정수와 같은 단순 형식의 개체 값을 변경하거나 서버의 문서에 있는 캐시된 <xref:System.Data.DataSet>를 초기화하려는 경우가 이에 해당합니다.  이러한 경우 캐시된 개체의 현재 값을 먼저 deserialize하지 않고 <xref:Microsoft.VisualStudio.Tools.Applications.CachedDataItem.SerializeDataInstance%2A> 메서드를 사용할 수 있습니다.  
  
 다음 코드 예제에서는 Excel 통합 문서 프로젝트의 `Sheet1` 클래스에 있는 캐시된 문자열의 값을 변경하는 방법을 보여 줍니다.  이 예제는 <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.Save%2A> 메서드에 대해 제공되는 보다 큰 예제의 일부입니다.  
  
 [!code-csharp[Trin_ServerDocument#11](../snippets/csharp/VS_Snippets_OfficeSP/Trin_ServerDocument/CS/Form1.cs#11)]
 [!code-vb[Trin_ServerDocument#11](../snippets/visualbasic/VS_Snippets_OfficeSP/Trin_ServerDocument/VB/Form1.vb#11)]  
  
### 데이터 캐시의 Null 값 수정  
 문서가 저장되고 닫힐 때 **null** 값이 있는 개체는 데이터 캐시에 저장되지 않습니다.  이 제한으로 인해 캐시된 데이터를 수정할 때 다음과 같은 결과가 발생합니다.  
  
-   데이터 캐시의 개체를 **null** 값으로 설정하면 문서가 열릴 때 데이터 캐시의 모든 개체가 자동으로 **null**로 설정되고 문서가 저장되고 닫힐 때 데이터 캐시 전체가 지워집니다.  즉, 캐시된 개체가 모두 데이터 캐시에서 제거되고 <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument.CachedData%2A> 컬렉션이 비어 있게 됩니다.  
  
-   데이터 캐시의 **null** 개체를 사용하여 솔루션을 만들 경우 문서가 처음으로 열리기 전에 <xref:Microsoft.VisualStudio.Tools.Applications.ServerDocument> 클래스를 사용하여 이러한 개체를 초기화하려면 데이터 캐시의 모든 개체를 초기화해야 합니다.  일부 개체만 초기화하면 문서가 열릴 때 모든 개체가 **null**로 설정되고 문서가 저장되고 닫힐 때 데이터 캐시 전체가 지워집니다.  
  
## 캐시의 형식화된 데이터 집합에 액세스  
 Office 솔루션 및 Office 이외의 응용 프로그램\(예: Windows Forms 응용 프로그램 또는 [!INCLUDE[vstecasp](../sharepoint/includes/vstecasp-md.md)] 프로젝트\)에서 형식화된 데이터 집합의 데이터에 액세스하려면 형식화된 데이터 집합을 두 프로젝트 모두에서 참조되는 별도의 어셈블리에 정의해야 합니다.  **데이터 소스 구성 마법사** 또는 **데이터 집합 디자이너**를 사용하여 각 프로젝트에 형식화된 데이터 집합을 추가하는 경우 .NET Framework는 두 프로젝트의 형식화된 데이터 집합을 서로 다른 형식으로 취급합니다.  형식화된 데이터 집합 만들기에 대한 자세한 내용은 [방법: 형식화된 데이터 집합 만들기](../Topic/Creating%20and%20configuring%20datasets%20in%20Visual%20Studio.md)를 참조하십시오.  
  
## 참고 항목  
 [Accessing Data in Documents on the Server](../vsto/accessing-data-in-documents-on-the-server.md)   
 [문서 수준 사용자 지정의 캐시된 데이터](../vsto/cached-data-in-document-level-customizations.md)  
  
  