---
title: '방법: XML 스키마 탐색기에서 작업 영역에 노드 추가'
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-xml-tools
ms.topic: conceptual
ms.assetid: 3b5a5749-9693-4b29-b0c2-8e07e0e55514
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 3e1f5821d3a4207d89eb62b9344cff967c73b536
ms.sourcegitcommit: 58052c29fc61c9a1ca55a64a63a7fdcde34668a4
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 06/04/2018
ms.locfileid: "34752055"
---
# <a name="how-to-add-nodes-to-the-workspace-from-the-xml-schema-explorer"></a>방법: XML 스키마 탐색기에서 작업 영역에 노드 추가

이 항목에서는 노드를 추가 하는 방법에 설명 된 [XML 스키마 디자이너 작업 영역](../xml-tools/xml-schema-designer-workspace.md) 에서 **XML 스키마 탐색기**합니다. 이 작업을 끌어서에서 노드를 삭제 하 여 수행할 수 있습니다는 **XML 스키마 탐색기** XSD 디자이너 뷰로 또는 사용 하 여는 **XML 스키마 탐색기** 상황에 맞는 메뉴입니다. 수행 된 검색 결과로 강조 표시 된 노드를 추가할 수도 있습니다는 **XML 스키마 탐색기**합니다. 자세한 내용은 참조 [하는 방법: 작업 영역에 스키마 집합 검색 결과 노드 추가](../xml-tools/how-to-add-schema-set-search-result-nodes-to-the-workspace.md)합니다.

> [!NOTE]
> 전역 노드만에 추가할 수는 [XML 스키마 디자이너 작업 영역](../xml-tools/xml-schema-designer-workspace.md)합니다.

## <a name="to-add-nodes-through-the-xml-explorer-context-menu"></a>XML 탐색기 상황에 맞는 메뉴를 통해 노드를 추가 하려면

1.  단계에 따라 [하는 방법: XSD 스키마 파일 만들기 및 편집](../xml-tools/how-to-create-and-edit-an-xsd-schema-file.md)합니다.

2.  마우스 오른쪽 단추로 클릭는 `PurchaseOrderType` XSD 탐색기에서 노드. 선택 **그래프 뷰로 표시**합니다.

     그래프 뷰의 디자인 화면에 `purchaseOrderType` 노드가 나타납니다.

## <a name="to-drag-and-drop-a-node-on-to-a-view"></a>노드를 뷰로 끌어서 놓으려면

1.  마우스 오른쪽 단추로 클릭는 `PurchaseOrderType` 그래프 보기에서 노드. 선택 **XML 스키마 탐색기에 표시**합니다.

     이 노드를 강조 표시는 **XML 스키마 탐색기**합니다.

2.  마우스 오른쪽 단추로 클릭는 `PurchaseOrderType` 에서 노드는 **XML 스키마 탐색기** 선택 **모든 참조 표시**합니다.

     `purchaseOrder` 노드가 강조 표시됩니다.

3.  `purchaseOrder` 노드를 그래픽 뷰로 끕니다.

     `purchaseOrder` 노드 및 `PurchaseOrderType` 노드가 그래프 뷰의 디자인 화면에 나란히 나타납니다. 이 두 노드는 서로 관련되어 있으므로(`purchaseOrder` 요소가 `PurchaseOrderType` 형식임) 두 노드 사이에 화살표가 그려집니다.

## <a name="to-add-nodes-using-the-schema-explorer-search-capability"></a>스키마 탐색기 검색 기능을 사용하여 노드를 추가하려면

1.  검색 텍스트 상자에 "purchaseOrder"를 입력는 [XML 탐색기](../xml-tools/xml-schema-explorer.md) 도구 모음 및 검색 단추를 클릭 합니다.

     ![XML 스키마 탐색기 키워드 검색](../xml-tools/media/schemaexplorersearch.gif)

     검색 결과에서 강조 표시 됩니다는 **XML 스키마 탐색기** 세로 스크롤 막대의 눈금 표시로 하 고 있습니다.

2.  검색 결과 클릭 하 여 작업 영역에 추가 된 **작업 영역에 선택한 노드 추가** 요약 결과 창에서 단추입니다.

     ![XML 스키마 탐색기 검색 결과](../xml-tools/media/schemaexplorersearchresult.gif)

     `purchaseOrder` 노드 및 `PurchaseOrderType` 노드의 디자인 화면에 나란히 나타납니다는 [그래프 보기](../xml-tools/graph-view.md)합니다. 이 두 노드는 서로 관련되어 있으므로(`purchaseOrder` 요소가 `PurchaseOrderType` 형식임) 두 노드 사이에 화살표가 그려집니다.

## <a name="see-also"></a>참고자료

- [XML 스키마 탐색기](../xml-tools/xml-schema-explorer.md)