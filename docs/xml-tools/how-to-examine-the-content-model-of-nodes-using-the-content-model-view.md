---
title: XML 스키마 디자이너에서 콘텐츠 모델 뷰를 사용 하 여 노드의 콘텐츠 모델 검사
ms.date: 11/04/2016
ms.prod: visual-studio-dev15
ms.technology: vs-xml-tools
ms.topic: conceptual
ms.assetid: c42ddac8-b0e3-48d6-9832-112a19d6c104
author: gewarren
ms.author: gewarren
manager: douge
ms.workload:
- multiple
ms.openlocfilehash: 650478a92ea2dabc9aeef239a68bdff428429cd7
ms.sourcegitcommit: 697162f54d3c4e30df702fd0289e447e211e3a85
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 05/25/2018
---
# <a name="how-to-examine-the-content-model-of-nodes-using-the-content-model-view"></a>방법: 콘텐츠 모델 뷰를 사용 하 여 노드의 콘텐츠 모델 검사

사용 하 여 노드를 탐색 하는 방법에 설명 된 [콘텐츠 모델 뷰](../xml-tools/content-model-view.md)합니다.

## <a name="to-create-a-new-xsd-file-and-display-the-root-element-in-the-content-model-view"></a>콘텐츠 모델 뷰에서 새 XSD 파일을 만들고 루트 요소를 표시하려면

1.  새 XML 스키마 파일을 만듭니다.

2.  클릭 **기본 XML 스키마 파일 표시 및 편집 하려면 XML 편집기를 사용 하 여** 시작 보기에서 합니다.

3.  XML 스키마 샘플 코드를 복사 [샘플 XML 스키마: 구매 주문 스키마](../xml-tools/sample-xsd-file-purchase-order-schema.md) 기본적으로 새 XSD 파일에 추가 된 코드를 붙여 넣습니다.

4.  선택 된 `purchaseOrder` 마우스 오른쪽 단추로 클릭 하 여 스키마 탐색기에서 요소는 `purchaseOrder` XML 편집기에서 요소를 선택 하 고 **XML 탐색기에 표시**합니다.

5.  마우스 오른쪽 단추로 클릭는 `purchaseOrder` 고 XML 탐색기에서 **콘텐츠 모델 뷰로 표시**합니다.

     콘텐츠 모델 뷰는 해당 디자인 화면에 `purchaseOrder` 요소를 표시합니다.

6.  각 노드를 두 번 클릭하거나 각 노드 오른쪽에 있는 양방향 화살표를 클릭하여 `shipTo`, `billTo` 및 `items` 노드를 확장합니다.

     이제 `purchaseOrder` 요소의 노드가 확장되고 요소의 콘텐츠 모델을 볼 수 있습니다.

7.  `purchaseOrder` 요소 아래의 노드를 클릭하고 이동 경로 탐색 막대를 확인하여 스키마 집합에서 선택한 노드가 위치한 곳을 봅니다.

8.  클릭는 **설명서 표시** 숨깁니다 XSD 도구 모음에서 단추입니다. 또한 디자인 화면을 마우스 오른쪽 단추로 클릭하여 설명서를 표시하거나 숨길 수 있습니다.

9. 단추로 클릭 하는 `purchaseOrder` 노드 선택한 **샘플 XML 생성** XML 인스턴스 문서를 볼 수 있습니다.