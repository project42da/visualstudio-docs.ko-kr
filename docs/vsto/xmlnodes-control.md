---
title: "XMLNodes 컨트롤 | Microsoft Docs"
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
  - "XMLNodes 컨트롤"
  - "XMLNodes 컨트롤, 이벤트"
ms.assetid: 25ba7a21-aabb-4cce-b0d7-57b4add3b485
caps.latest.revision: 36
author: "kempb"
ms.author: "kempb"
manager: "ghogen"
caps.handback.revision: 36
---
# XMLNodes 컨트롤
  **중요 한** Microsoft Word와 관련 된이 항목에 설정 된 정보 혜택 및 개인과 누가 미국과 해당 영토 밖에 위치한 되 나 누구를 사용 하 여 또는 2010 년 1 월 Microsoft 제거 경우 Microsoft Word에서 사용자 지정 XML에 관련 된 특정 기능을 구현 하기 전에 Microsoft에서 사용이 허가 된 제품을 Microsoft Word를 실행 하는 프로그램 개발 회사의 사용에 대 한 독점적으로 제공 됩니다.  Microsoft Word에 대한 정보는 2010년 1월 10일 이후 Microsoft에서 사용 허가를 받고 Microsoft Word에서 실행되는 프로그램을 사용 또는 개발하고 있는 미국 또는 미국 자치령의 개인 또는 조직에서 읽거나 사용하지 못할 수 있습니다. 이런 제품은 해당 날짜 이전에 사용 허가를 받거나 미국이 아닌 다른 곳에서 사용하기 위해 구매하고 사용 허가를 받은 동일한 제품처럼 작동하지 않습니다.  
  
 [!INCLUDE[appliesto_wdalldoc](../vsto/includes/appliesto-wdalldoc-md.md)]  
  
 <xref:Microsoft.Office.Tools.Word.XMLNodes> 컨트롤은 이벤트를 노출하는 매핑된 XML 노드 개체의 컬렉션입니다.  <xref:Microsoft.Office.Tools.Word.XMLNodes> 컨트롤은 반복되는 스키마 요소를 Microsoft Office Word 문서에 매핑하는 경우에만 작성됩니다.  반복되는 요소에 자식 요소가 포함되어 있으면 각 자식 요소도 <xref:Microsoft.Office.Tools.Word.XMLNodes> 컨트롤로 작성됩니다.  
  
 Visual Studio에서 XML 노드의 컬렉션을 만들면 Word 개체 모델을 순회하지 않고도 컨트롤에 대한 프로그램을 직접 작성할 수 있습니다.  <xref:Microsoft.Office.Tools.Word.XMLNodes> 컨트롤은 문서에서 요소 매핑을 제거해야만 삭제할 수 있습니다.  
  
> [!NOTE]  
>  <xref:Microsoft.Office.Tools.Word.XMLNodes.Item%2A> 속성을 통해 <xref:Microsoft.Office.Tools.Word.XMLNodes> 컨트롤의 자식 요소에 액세스하면 <xref:Microsoft.Office.Tools.Word.XMLNode> 컨트롤 대신 <xref:Microsoft.Office.Interop.Word.XMLNode> 개체가 반환됩니다.  자세한 내용은 [호스트 항목 및 호스트 컨트롤의 프로그래밍에 대한 제한 사항](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)을 참조하십시오.  
  
## 컨트롤에 데이터 바인딩  
 <xref:Microsoft.Office.Tools.Word.XMLNodes> 컨트롤은 데이터 바인딩을 지원하지 않습니다.  <xref:Microsoft.Office.Tools.Word.XMLNodes> 컨트롤에는 복합 데이터 바인딩 기능이 없고 단순 데이터 바인딩에서는 반복되는 데이터를 표현할 수 없기 때문입니다.  
  
## 형식 지정  
 문서 내의 텍스트에 적용할 수 있는 모든 형식을 <xref:Microsoft.Office.Tools.Word.XMLNodes> 컨트롤에 적용할 수 있습니다.  
  
## 이벤트  
 <xref:Microsoft.Office.Tools.Word.XMLNodes> 컨트롤에 사용할 수 있는 이벤트는 다음과 같습니다.  
  
-   <xref:Microsoft.Office.Tools.Word.XMLNodes.AfterInsert>  
  
-   <xref:Microsoft.Office.Tools.Word.XMLNodes.BeforeDelete>  
  
-   <xref:Microsoft.Office.Tools.Word.XMLNodes.ContextEnter>  
  
-   <xref:Microsoft.Office.Tools.Word.XMLNodes.ContextLeave>  
  
-   <xref:Microsoft.Office.Tools.Word.XMLNodes.Deselect>  
  
-   <xref:System.ComponentModel.IComponent.Disposed>  
  
-   <xref:Microsoft.Office.Tools.Word.XMLNodes.Select>  
  
-   <xref:Microsoft.Office.Tools.Word.XMLNodes.ValidationError>  
  
## 이벤트 비교  
 사용자가 특정 <xref:Microsoft.Office.Tools.Word.XMLNodes> 컨트롤의 컨텍스트 안으로 커서를 옮기면 이벤트를 캡처할 수 있습니다.  예를 들어 다음과 같이 `Customer`라는 <xref:Microsoft.Office.Tools.Word.XMLNodes> 컨트롤에 `Company`라는 자식 <xref:Microsoft.Office.Tools.Word.XMLNodes> 컨트롤 하나가 있고 `Company`에 `CompanyName` 및 `CompanyRegion`이라는 자식 <xref:Microsoft.Office.Tools.Word.XMLNodes> 컨트롤 두 개가 있는 경우를 생각해 볼 수 있습니다.  
  
```  
<Customer>  
    <Company>  
        <CompanyName>  
        <CompanyRegion>  
```  
  
 커서가 `Company` 노드로 이동할 때마다 작업 창에 컨트롤을 표시하려는 경우 커서가 `CompanyName`에 있는지 `CompanyRegion`에 있는지 여부는 중요하지 않습니다. 이 두 컨트롤은 모두 `Company`의 컨텍스트 내에 있기 때문입니다.  이 경우 `Company`의 <xref:Microsoft.Office.Tools.Word.XMLNodes.ContextEnter> 이벤트에 코드를 작성할 수 있습니다.  
  
 대부분의 경우 커서가 <xref:Microsoft.Office.Tools.Word.XMLNodes> 컨트롤로 이동하면 <xref:Microsoft.Office.Tools.Word.XMLNodes.Select> 및 <xref:Microsoft.Office.Tools.Word.XMLNodes.ContextEnter> 이벤트가 모두 발생합니다.  다음 표에서는 이러한 이벤트의 차이점을 보여 줍니다.  
  
|Select 이벤트|ContextEnter 이벤트|  
|----------------|----------------------|  
|커서가 <xref:Microsoft.Office.Tools.Word.XMLNodes> 컬렉션의 노드 중 하나에 배치된 경우에 발생합니다.|커서가 노드의 컨텍스트 바깥쪽 영역에서 <xref:Microsoft.Office.Tools.Word.XMLNodes> 컬렉션의 노드나 하위 노드 중 하나에 배치된 경우에 발생합니다.  즉, 이 이벤트는 컨텍스트가 변경되어 여러 개의 중첩된 <xref:Microsoft.Office.Tools.Word.XMLNodes> 컨트롤이 발생할 수 있는 경우에만 발생합니다.|  
  
 예를 들어 `Customer`의 바깥쪽에서 `CompanyName`으로 커서를 옮기면 `Customer`, `Company` 및 `CompanyName`에 대한 <xref:Microsoft.Office.Tools.Word.XMLNodes.ContextEnter> 이벤트가 발생합니다.  `CompanyName`에서 `CompanyRegion`으로 커서를 옮기면 `CompanyRegion`에 대한 <xref:Microsoft.Office.Tools.Word.XMLNodes.ContextEnter> 이벤트만 발생합니다. `Company` 및 `Customer` 모두에 대한 컨텍스트가 동일하기 때문입니다.  문서에 여러 개의 `Company` 노드가 있을 수 있습니다.  한 `Company`의 `CompanyName` 노드에서 다른 `Company`의 `CompanyName` 노드로 커서를 옮기면 컨텍스트가 동일하므로 <xref:Microsoft.Office.Tools.Word.XMLNodes.Select> 이벤트만 발생합니다.  
  
 <xref:Microsoft.Office.Tools.Word.XMLNodes.ContextLeave> 이벤트와 <xref:Microsoft.Office.Tools.Word.XMLNodes.Deselect> 이벤트 사이에도 이와 같은 차이점이 있습니다.  
  
## 참고 항목  
 [호스트 항목 및 호스트 컨트롤 개요](../vsto/host-items-and-host-controls-overview.md)   
 [확장된 개체를 사용하여 Word 자동화](../vsto/automating-word-by-using-extended-objects.md)   
 [XMLNode 컨트롤](../vsto/xmlnode-control.md)   
 [방법: Word 문서에 XMLNodes 컨트롤 추가](../vsto/how-to-add-xmlnodes-controls-to-word-documents.md)   
 [방법: Visual Studio 내부의 Word 문서에 스키마 매핑](../vsto/how-to-map-schemas-to-word-documents-inside-visual-studio.md)   
 [호스트 항목 및 호스트 컨트롤의 프로그래밍에 대한 제한 사항](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)  
  
  