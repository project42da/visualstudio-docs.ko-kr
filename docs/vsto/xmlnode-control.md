---
title: "XMLNode 컨트롤 | Microsoft Docs"
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
helpviewer_keywords: XMLNode control
ms.assetid: 4f5c7f17-62aa-483c-ab0d-b04614ab065d
caps.latest.revision: "39"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: c35726314dc679289554e24d4150da4294cf8a0b
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="xmlnode-control"></a>XMLNode 컨트롤
  **중요 한** Microsoft Word에 대 한이 항목에 정보는 이점과 개인 및 United States 및 해당 지역 외부에 있는 사용자 또는 사용자를 사용 하는 조직의 사용에 대해 독점적으로 발표 된 또는 개발 실행 되는 프로그램, Microsoft Word 2010 년 1 월, Microsoft 구현의 특정 기능을 제거 하는 경우 하기 전에 Microsoft에서 사용이 허가 된 제품에서에서와 관련 된 사용자 지정 XML Microsoft Word입니다. Microsoft Word에 대 한이 정보를 읽거나 개인 이나 조직에는 미국이 나 Microsoft Word 2010 년 1 월 10 일 이후에 Microsoft에서 사용이 허가 된 제품에서 실행 되는 프로그램을 개발 하거나를 사용 하는 사용자의 지역에서 사용 될 수 있습니다. ; 이러한 제품 해당 날짜 이전에 사용이 허가 또는 구입 해야 하 고 미국 이외의 용도로 사용이 허가 된 제품와 동일 하 게 작동 하지 않습니다.  
  
 [!INCLUDE[appliesto_wdalldoc](../vsto/includes/appliesto-wdalldoc-md.md)]  
  
 <xref:Microsoft.Office.Tools.Word.XMLNode> 컨트롤은 매핑된 XML 노드 개체 이벤트를 노출 하 고 데이터에 바인딩될 수입니다. <xref:Microsoft.Office.Tools.Word.XMLNode> 컨트롤이-반복 되지 않는 스키마 요소는 Microsoft Office Word 문서에 매핑될 경우에 만들어집니다. Visual Studio가 XML 노드를 만든 후 Word 개체 모델을 트래버스 하지 않고 직접 프로그래밍할 수 있습니다.  
  
 <xref:Microsoft.Office.Tools.Word.XMLNode> 만 Word에서 요소 매핑을 제거 하 여 컨트롤을 삭제할 수 있습니다.  
  
## <a name="binding-data-to-the-control"></a>컨트롤에 데이터 바인딩  
 <xref:Microsoft.Office.Tools.Word.XMLNode> 컨트롤은 단순 데이터 바인딩을 지원 합니다. 사용 하 여 데이터 원본에 바인딩될 해야 XML 노드는 <xref:System.Windows.Forms.IBindableComponent.DataBindings%2A> 속성입니다. 바인딩된 데이터 집합의 데이터가 업데이트 되는 <xref:Microsoft.Office.Tools.Word.XMLNode> 컨트롤이 변경 내용을 반영 합니다.  
  
## <a name="formatting"></a>서식  
 에 적용할 수 있는 서식은 <xref:Microsoft.Office.Interop.Word.XMLNode> 개체에 적용할 수는 <xref:Microsoft.Office.Tools.Word.XMLNode> 제어 합니다. 글꼴, 밑줄 스타일 및 스타일 문자를 포함 합니다.  
  
## <a name="events"></a>이벤트  
 <xref:Microsoft.Office.Tools.Word.XMLNode> 컨트롤에 대해 다음 이벤트를 사용할 수 있습니다.  
  
-   <xref:Microsoft.Office.Tools.Word.XMLNode.AfterInsert>  
  
-   <xref:Microsoft.Office.Tools.Word.XMLNode.BeforeDelete>  
  
-   <xref:Microsoft.Office.Tools.Word.XMLNode.BindingContextChanged>  
  
-   <xref:Microsoft.Office.Tools.Word.XMLNode.ContextEnter>  
  
-   <xref:Microsoft.Office.Tools.Word.XMLNode.ContextLeave>  
  
-   <xref:Microsoft.Office.Tools.Word.XMLNode.Deselect>  
  
-   <xref:System.ComponentModel.IComponent.Disposed>  
  
-   <xref:Microsoft.Office.Tools.Word.XMLNode.Select>  
  
-   <xref:Microsoft.Office.Tools.Word.XMLNode.ValidationError>  
  
## <a name="comparing-events"></a>이벤트 비교  
 특정 상황에 맞는 안으로 커서를 이동할 때 이벤트를 캡처할 수 <xref:Microsoft.Office.Tools.Word.XMLNode> 제어 합니다. 예를 들어 있을 수 있습니다는 <xref:Microsoft.Office.Tools.Word.XMLNode> 라는 컨트롤 `Customer` 자식이 있는 <xref:Microsoft.Office.Tools.Word.XMLNode> 라는 컨트롤 `Company`, 및 `Company` 에 두 명의 자식 <xref:Microsoft.Office.Tools.Word.XMLNode> 라는 컨트롤 `CompanyName` 및 `CompanyRegion` 다음과 같습니다:  
  
```  
<Customer>  
    <Company>  
        <CompanyName>  
        <CompanyRegion>  
```  
  
 작업 창에 컨트롤을 표시 하려는 경우 때마다 커서가 이동에 `Company` 노드를 중요 하지 않습니다는 커서에 배치할지 여부를 `CompanyName` 또는 `CompanyRegion` 의 컨텍스트 내에서 둘 다 되기 때문에 `Company`합니다. 이 경우에서 코드를 작성할 수 있습니다는 <xref:Microsoft.Office.Tools.Word.XMLNode.ContextEnter> 이벤트의 `Company`합니다.  
  
 대부분의 경우, 커서가 <xref:Microsoft.Office.Tools.Word.XMLNode> 둘 다 제어는 <xref:Microsoft.Office.Tools.Word.XMLNode.Select> 및 <xref:Microsoft.Office.Tools.Word.XMLNode.ContextEnter> 이벤트가 발생 합니다. 다음 표에서 이러한 이벤트 간의 차이점을 보여 줍니다.  
  
|이벤트 선택|ContextEnter 이벤트|  
|------------------|------------------------|  
|커서에 배치 된 경우에 발생 한 <xref:Microsoft.Office.Tools.Word.XMLNode>합니다.|커서에 배치 된 경우에 발생 한 <xref:Microsoft.Office.Tools.Word.XMLNode> 또는 노드 범위 밖에 영역에서 하위 노드 중 하나입니다. 즉, 컨텍스트가 변경 되는 때에 발생 합니다.|  
  
 예를 들어 이동 하는 경우 외부에서 커서 `Customer` 에 `CompanyName`, <xref:Microsoft.Office.Tools.Word.XMLNode.ContextEnter> 이벤트에 대 한 `Customer`, `Company`, 및 `CompanyName` 발생 합니다. 다음에서 커서를 이동 하면 `CompanyName` 를 `CompanyRegion`만 <xref:Microsoft.Office.Tools.Word.XMLNode.ContextEnter> 이벤트에 대 한 `CompanyRegion` 도달 하 여 둘 다의 컨텍스트 내에서 여전히 발생 `Company` 및 `Customer`합니다.  
  
 경우에 동일한 차이점이 <xref:Microsoft.Office.Tools.Word.XMLNode.ContextLeave> 이벤트 및 <xref:Microsoft.Office.Tools.Word.XMLNode.Deselect> 이벤트입니다.  
  
## <a name="see-also"></a>참고 항목  
 [Host Items and Host Controls Overview](../vsto/host-items-and-host-controls-overview.md)   
 [확장 된 개체를 사용 하 여 Word 자동화](../vsto/automating-word-by-using-extended-objects.md)   
 [XMLNodes 컨트롤](../vsto/xmlnodes-control.md)   
 [방법: Word 문서에 XMLNode 컨트롤 추가](../vsto/how-to-add-xmlnode-controls-to-word-documents.md)   
 [방법: Visual Studio 내부의 Word 문서에 스키마 매핑](../vsto/how-to-map-schemas-to-word-documents-inside-visual-studio.md)   
 [호스트 항목 및 호스트 컨트롤의 프로그래밍에 대한 제한 사항](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)  
  
  