---
title: XMLNodes 컨트롤 | Microsoft Docs
ms.custom: ''
ms.date: 02/02/2017
ms.technology:
- office-development
ms.topic: conceptual
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- XMLNodes control, events
- XMLNodes control
author: TerryGLee
ms.author: tglee
manager: douge
ms.workload:
- office
ms.openlocfilehash: 0bb3451f491e4a663a99488f4b2099d58f0018eb
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="xmlnodes-control"></a>XMLNodes 컨트롤
  **중요 한** Microsoft Word에 대 한이 항목에 정보는 이점과 개인 및 United States 및 해당 지역 외부에 있는 사용자 또는 사용자를 사용 하는 조직의 사용에 대해 독점적으로 발표 된 또는 개발 실행 되는 프로그램, Microsoft Word 2010 년 1 월, Microsoft 구현의 특정 기능을 제거 하는 경우 하기 전에 Microsoft에서 사용이 허가 된 제품에서에서와 관련 된 사용자 지정 XML Microsoft Word입니다. Microsoft Word에 대 한이 정보를 읽거나 개인 이나 조직에는 미국이 나 Microsoft Word 2010 년 1 월 10 일 이후에 Microsoft에서 사용이 허가 된 제품에서 실행 되는 프로그램을 개발 하거나를 사용 하는 사용자의 지역에서 사용 될 수 있습니다. ; 이러한 제품 해당 날짜 이전에 사용이 허가 또는 구입 해야 하 고 미국 이외의 용도로 사용이 허가 된 제품와 동일 하 게 작동 하지 않습니다.  
  
 [!INCLUDE[appliesto_wdalldoc](../vsto/includes/appliesto-wdalldoc-md.md)]  
  
 <xref:Microsoft.Office.Tools.Word.XMLNodes> 컨트롤은 이벤트를 노출 하는 매핑된 XML 노드 개체의 컬렉션입니다. <xref:Microsoft.Office.Tools.Word.XMLNodes> 컨트롤이 반복 스키마 요소는 Microsoft Office Word 문서에 매핑될 경우에 만들어집니다. 반복 되는 요소에 자식 요소가 있으면 자식 요소는 각각도 생성 됩니다는 <xref:Microsoft.Office.Tools.Word.XMLNodes> 제어 합니다.  
  
 XML 노드의 컬렉션을 생성 하는 Visual Studio에서 Word 개체 모델을 트래버스 하지 않고 직접 컨트롤에 대해 프로그래밍할 수 있습니다. <xref:Microsoft.Office.Tools.Word.XMLNodes> 컨트롤이 문서에서 요소 매핑을 제거 하 여만 삭제할 수 있습니다.  
  
> [!NOTE]  
>  자식 요소를 액세스 하는 경우는 <xref:Microsoft.Office.Tools.Word.XMLNodes> 를 통해 제어는 <xref:Microsoft.Office.Tools.Word.XMLNodes.Item%2A> 속성을 반환는 <xref:Microsoft.Office.Interop.Word.XMLNode> 개체 대신 <xref:Microsoft.Office.Tools.Word.XMLNode> 제어 합니다. 자세한 내용은 [호스트 항목 및 호스트 컨트롤의 프로그래밍에 대한 제한 사항](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)을 참조하세요.  
  
## <a name="binding-data-to-the-control"></a>컨트롤에 데이터 바인딩  
 <xref:Microsoft.Office.Tools.Word.XMLNodes> 컨트롤에 데이터 바인딩을 지원 하지 않습니다. 때문에 이것이 <xref:Microsoft.Office.Tools.Word.XMLNodes> 컨트롤에 복잡 한 데이터 바인딩 기능이 없으면 및 단순 데이터 바인딩 표현할 수 없으면 반복 되는 데이터입니다.  
  
## <a name="formatting"></a>서식  
 문서 내에서 텍스트에 적용할 수 있는 서식은에 적용할 수 있습니다는 <xref:Microsoft.Office.Tools.Word.XMLNodes> 제어 합니다.  
  
## <a name="events"></a>이벤트  
 에 대해 사용할 수 있는 이벤트는 <xref:Microsoft.Office.Tools.Word.XMLNodes> 제어 됩니다.  
  
-   <xref:Microsoft.Office.Tools.Word.XMLNodes.AfterInsert>  
  
-   <xref:Microsoft.Office.Tools.Word.XMLNodes.BeforeDelete>  
  
-   <xref:Microsoft.Office.Tools.Word.XMLNodes.ContextEnter>  
  
-   <xref:Microsoft.Office.Tools.Word.XMLNodes.ContextLeave>  
  
-   <xref:Microsoft.Office.Tools.Word.XMLNodes.Deselect>  
  
-   <xref:System.ComponentModel.IComponent.Disposed>  
  
-   <xref:Microsoft.Office.Tools.Word.XMLNodes.Select>  
  
-   <xref:Microsoft.Office.Tools.Word.XMLNodes.ValidationError>  
  
## <a name="comparing-events"></a>이벤트 비교  
 특정 상황에 맞는 안으로 커서를 이동할 때 이벤트를 캡처할 수 <xref:Microsoft.Office.Tools.Word.XMLNodes> 제어 합니다. 예를 들어 있을 수 있습니다는 <xref:Microsoft.Office.Tools.Word.XMLNodes> 라는 컨트롤 `Customer` 자식이 있는 <xref:Microsoft.Office.Tools.Word.XMLNodes> 라는 컨트롤 `Company`, 및 `Company` 에 두 명의 자식 <xref:Microsoft.Office.Tools.Word.XMLNodes> 라는 컨트롤 `CompanyName` 및 `CompanyRegion` 다음과 같습니다:  
  
```  
<Customer>  
    <Company>  
        <CompanyName>  
        <CompanyRegion>  
```  
  
 작업 창에 컨트롤을 표시 하려는 경우 때마다 커서가 이동에 `Company` 노드를 중요 하지 않습니다는 커서에 배치할지 여부를 `CompanyName` 또는 `CompanyRegion` 의 컨텍스트 내에서 둘 다 되기 때문에 `Company`합니다. 이 경우에서 코드를 작성할 수 있습니다는 <xref:Microsoft.Office.Tools.Word.XMLNodes.ContextEnter> 이벤트의 `Company`합니다.  
  
 대부분의 경우, 커서가 <xref:Microsoft.Office.Tools.Word.XMLNodes> 둘 다 제어는 <xref:Microsoft.Office.Tools.Word.XMLNodes.Select> 및 <xref:Microsoft.Office.Tools.Word.XMLNodes.ContextEnter> 이벤트가 발생 합니다. 다음 표에서 이러한 이벤트의 차이점을 보여 줍니다.  
  
|이벤트 선택|ContextEnter 이벤트|  
|------------------|------------------------|  
|커서의 노드 중 하나에 배치 된 경우에 발생는 <xref:Microsoft.Office.Tools.Word.XMLNodes> 컬렉션입니다.|커서 노드 또는 노드의 하위 항목 중 하나에 배치 된 경우에 발생는 <xref:Microsoft.Office.Tools.Word.XMLNodes> 컨텍스트 노드의 바깥쪽 영역에서의 컬렉션입니다. 즉,이 이벤트는 발생 된 컨텍스트를 변경 하는 경우에 여러 중첩 발생할 수 있습니다 및 <xref:Microsoft.Office.Tools.Word.XMLNodes> 컨트롤입니다.|  
  
 외부에서 커서를 이동할 때 예를 들어 `Customer` 에 `CompanyName`, <xref:Microsoft.Office.Tools.Word.XMLNodes.ContextEnter> 에 대 한 이벤트 `Customer`, `Company`, 및 `CompanyName` 발생 합니다. 다음에서 커서를 이동 하면 `CompanyName` 를 `CompanyRegion`, <xref:Microsoft.Office.Tools.Word.XMLNodes.ContextEnter> 이벤트에 대해서만 `CompanyRegion` 컨텍스트 둘 다에 대해 동일 하기 때문에 발생 `Company` 및 `Customer`합니다. 여러 개 있을 수 `Company` 문서에서 노드. 커서를 이동 하는 경우는 `CompanyName` 하나의 노드 `Company` 에 `CompanyName` 의 다른 노드에 `Company`, 컨텍스트가 동일 하므로 <xref:Microsoft.Office.Tools.Word.XMLNodes.Select> 이벤트가 발생 합니다.  
  
 경우에 동일한 차이점이 <xref:Microsoft.Office.Tools.Word.XMLNodes.ContextLeave> 이벤트 및 <xref:Microsoft.Office.Tools.Word.XMLNodes.Deselect> 이벤트입니다.  
  
## <a name="see-also"></a>참고 항목  
 [호스트 항목 및 호스트 컨트롤 개요](../vsto/host-items-and-host-controls-overview.md)   
 [확장 된 개체를 사용 하 여 Word 자동화](../vsto/automating-word-by-using-extended-objects.md)   
 [XMLNode 컨트롤](../vsto/xmlnode-control.md)   
 [방법: Word 문서에 XMLNodes 컨트롤 추가](../vsto/how-to-add-xmlnodes-controls-to-word-documents.md)   
 [방법: Visual Studio 내부의 Word 문서에 스키마 매핑](../vsto/how-to-map-schemas-to-word-documents-inside-visual-studio.md)   
 [호스트 항목 및 호스트 컨트롤의 프로그래밍에 대한 제한 사항](../vsto/programmatic-limitations-of-host-items-and-host-controls.md)  
  
  