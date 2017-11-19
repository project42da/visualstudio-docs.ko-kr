---
title: "DataRelation을 사용 하 여 데이터 집합 간의 관계를 만드는 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vbData.Microsoft.VSDesigner.DataSource.DesignRelation
- vbdata.Microsoft.VSDesigner.DataSource.DesignRelation
helpviewer_keywords:
- relationships, about relationships
- datasets [Visual Basic], relationships
- relationships, datasets
ms.assetid: cfe274f0-71fe-40f6-994e-7c7f6273c9ba
caps.latest.revision: "15"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.openlocfilehash: bfc537118f6c1769ec98893099daa0c61d1b5b1d
ms.sourcegitcommit: ee42a8771f0248db93fd2e017a22e2506e0f9404
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 11/09/2017
---
# <a name="create-relationships-between-datasets"></a>데이터 집합 간에 관계 만들기
관련된 데이터를 포함 하는 데이터 집합 테이블을 사용 하 여 <xref:System.Data.DataRelation> 서로 관련된 레코드를 반환 하 고 테이블 간의 부모/자식 관계를 나타내기 위해 개체입니다. 관련된 테이블을 사용 하 여 데이터 집합에 추가 **데이터 소스 구성 마법사**, 또는 **데이터 집합 디자이너**, 작성 및 구성의 <xref:System.Data.DataRelation> 있습니다에 대 한 개체입니다.  
  
<xref:System.Data.DataRelation> 개체 두 기능을 수행 합니다.  
  
-   해당 이름을 사용할 수 사용 하는 레코드와 관련 된 레코드입니다. 부모 레코드에 있는 경우 자식 레코드를 제공 (<xref:System.Data.DataRow.GetChildRows%2A>) 및 하위 레코드를 사용 하는 경우 부모 레코드 (<xref:System.Data.DataRow.GetParentRow%2A>).  
  
-   부모 레코드를 삭제 하면 관련된 자식 레코드를 삭제 하는 등의 참조 무결성 제약 조건을 적용할 수 있습니다.  
  
실제 조인 및의 기능 간의 차이점을 이해 해야는 <xref:System.Data.DataRelation> 개체입니다. 실제 조인의 레코드 부모 및 자식 테이블에서 가져온 되며 단일 기본 레코드 집합에 배치 합니다. 사용 하는 경우는 <xref:System.Data.DataRelation> 개체 없는 새 레코드 집합이 생성 됩니다. 대신, DataRelation 테이블 간의 관계를 추적 하 고 부모 및 자식 레코드를 동기화 합니다.  
  
## <a name="datarelation-objects-and-constraints"></a>DataRelation 개체 및 제약 조건  
A <xref:System.Data.DataRelation> 개체는 또한 만들고 다음과 같은 제약 조건을 적용 합니다.  
  
-   Unique 제약 조건을,이 테이블의 열에 중복 항목이 없으면 보장 합니다.  
  
-   데이터 집합에서 부모 및 자식 테이블 간에 참조 무결성을 유지 하기 위해 사용할 수 있는 foreign key 제약 합니다.  
  
지정 하는 제약 조건을 <xref:System.Data.DataRelation> 개체가 자동으로 해당 개체를 만들거나 속성을 설정 하 여 구현 됩니다. 사용 하 여 foreign key 제약 조건을 만들면는 <xref:System.Data.DataRelation> 개체, 인스턴스는 <xref:System.Data.ForeignKeyConstraint> 클래스에 추가 되는 <xref:System.Data.DataRelation> 개체의 <xref:System.Data.DataRelation.ChildKeyConstraint%2A> 속성입니다.  
  
Unique 제약 조건을 구현 단순히 설정 하거나는 <xref:System.Data.DataColumn.Unique%2A> 속성의 데이터 열을 `true` 의 인스턴스를 추가 하 여는 <xref:System.Data.UniqueConstraint> 클래스를 <xref:System.Data.DataRelation> 개체의 <xref:System.Data.DataRelation.ParentKeyConstraint%2A> 속성입니다. 참조 데이터 집합의 제약을 일시 중지에 대 한 내용은 [데이터 집합을 채우는 동안 제약 조건을 해제할](../data-tools/turn-off-constraints-while-filling-a-dataset.md)합니다.  
  
### <a name="referential-integrity-rules"></a>참조 무결성 규칙  
외래 키 제약 조건의 일부로 세 지점에 적용 되는 참조 무결성 규칙을 지정할 수 있습니다.  
  
-   부모 레코드를 업데이트 하는 경우  
  
-   부모 레코드를 삭제 하는 경우  
  
-   변경 승인 또는 거부  
  
만들 수 있는 규칙에 지정 된는 <xref:System.Data.Rule> 다음 표에 나열 된 열거형과 됩니다.  
  
|외래 키 제약 조건 규칙|작업|  
|----------------------------------|------------|  
|<xref:System.Data.Rule.Cascade>|자식 테이블의 관련된 레코드에 부모 레코드가 변경 (업데이트 또는 삭제)도 이루어집니다.|  
|<xref:System.Data.Rule.SetNull>|자식 레코드는 삭제 되지 않지만 자식 레코드의 외래 키로 설정 되어 <xref:System.DBNull>합니다. 이 설정을 사용 하 여 자식 레코드 수로 유지 되 "고아"-부모 레코드에 없는 관계 즉, 갖습니다. **참고:** 자식 테이블에 잘못 된 데이터가이 규칙을 사용 하 여 발생할 수 있습니다.|  
|<xref:System.Data.Rule.SetDefault>|관련된 자식 레코드의 외래 키가 기본값으로 설정 (열의에서 설정한 <xref:System.Data.DataColumn.DefaultValue%2A> 속성).|  
|<xref:System.Data.Rule.None>|관련된 자식 레코드에는 변경 되지 않습니다. 이 설정을 사용 하 여 자식 레코드는 잘못 된 부모 레코드에 대 한 참조를 포함할 수 있습니다.|  
  
데이터 집합 테이블에서 업데이트에 대 한 자세한 내용은 참조 [데이터는 데이터베이스에 다시 저장](../data-tools/save-data-back-to-the-database.md)합니다.  
  
### <a name="constraint-only-relations"></a>제약 조건만 관계  
만들 때 한 <xref:System.Data.DataRelation> 개체 관계 제약 조건을 적용 하는 데에 사용할 수를 지정 하는 옵션이 있습니다-즉,이 사용 되지 것입니다도 관련된 레코드에 액세스할 수 있습니다. 약간 더 효율적 이며 관련 레코드 기능 보다 더 적은 메서드가 들어 있는 데이터 집합을 생성 하려면이 옵션을 사용할 수 있습니다. 그러나 관련된 레코드에 액세스할 수 없습니다. 예를 들어 제약 조건만 관계에서 자식 레코드를가지고 있는 부모 레코드를 삭제 하면 및 자식 레코드에 부모를 통해 액세스할 수 없습니다.  
  
## <a name="manually-creating-a-data-relation-in-the-dataset-designer"></a>데이터 집합 디자이너에서 데이터 관계를 수동으로 만들기  
Visual Studio에서 데이터 디자인 도구를 사용 하 여 데이터 테이블을 만들 때 데이터 원본에서 정보를 수집할 수 있는 경우 관계가 자동으로 생성 됩니다. 데이터 테이블을 수동으로 추가 하는 경우는 **DataSet** 탭은 **도구 상자**, 수동으로 관계를 만들어야 할 수 있습니다. 만들기에 대 한 내용은 <xref:System.Data.DataRelation> 개체를 프로그래밍 방식으로 참조 [Datarelation 추가](/dotnet/framework/data/adonet/dataset-datatable-dataview/adding-datarelations)합니다.  
  
데이터 테이블 간의 관계에서 선으로 표시 된 **데이터 집합 디자이너**, 관계의 일 대 다 측면을 보여 주는 키 및 무한대 모양의 합니다. 기본적으로는 관계의 이름을 디자인 화면에 나타나지 않습니다.  
  
[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
#### <a name="to-create-a-relationship-between-two-data-tables"></a>두 데이터 테이블 간의 관계를 만들려면  
  
1.  데이터 집합을 열고는 **데이터 집합 디자이너**합니다. 자세한 내용은 참조 [연습: 데이터 집합 디자이너에서 데이터 집합 만들기](walkthrough-creating-a-dataset-with-the-dataset-designer.md)합니다.  
  
2.  끌어서는 **관계** 에서 개체는 **DataSet** 관계에서 자식 데이터 테이블로 도구 상자입니다.  
  
     **관계** 대화 상자가 열리고 채우기는 **자식 테이블** 끌어 온 테이블에 있는 상자는 **관계** 개체입니다.  
  
3.  부모 테이블에서 선택 된 **부모 테이블** 상자입니다. 부모 테이블은 일 대 다 관계의 "일" 쪽에 레코드가 있습니다.  
  
4.  올바른 자식 테이블에 표시 되는지 확인은 **자식 테이블** 상자입니다. 자식 테이블 대 다 관계의 "다" 쪽에 레코드를 포함합니다.  
  
5.  관계에 대 한 이름을 입력는 **이름** 하거나 기본 이름을 선택한 테이블에 기초 합니다. 이 실제 이름을 <xref:System.Data.DataRelation> 코드에서 개체입니다.  
  
6.  테이블을 조인 하는 열을 선택는 **키 열** 및 **외래 키 열** 나열 합니다.  
  
7.  와 관계, 제약 조건 또는 둘 다를 만들 것인지 선택 합니다.   
  
8.  선택 하거나 선택 취소 된 **중첩 관계** 상자입니다. 이 옵션을 선택 하는 <xref:System.Data.DataRelation.Nested%2A> 속성을 `true`, 해당 하면 자식 행은 해당 행은 XML 데이터로 작성 되거나와 동기화 하는 경우 부모 열 내에 중첩 될 해당 관계의 및 <xref:System.Xml.XmlDataDocument>합니다. 자세한 내용은 참조 [Datarelation 중첩](/dotnet/framework/data/adonet/dataset-datatable-dataview/nesting-datarelations)합니다.  
  
9. 이러한 테이블에서 레코드를 변경 하는 경우 적용할 규칙을 설정 합니다. 자세한 내용은 <xref:System.Data.Rule>을 참조하십시오.  
  
10. 클릭 **확인** 관계를 만듭니다. 디자이너는 두 테이블 사이 관계 선이 나타납니다.  
  
#### <a name="to-display-a-relation-name-in-the-dataset-designer"></a>데이터 집합 디자이너에서 관계 이름을 표시 하려면  
  
1.  데이터 집합을 열고는 **데이터 집합 디자이너**합니다. 자세한 내용은 참조 [연습: 데이터 집합 디자이너에서 데이터 집합 만들기](walkthrough-creating-a-dataset-with-the-dataset-designer.md)합니다.  
  
2.  **데이터** 메뉴는 **관계 레이블 표시** 관계 이름을 표시 하는 명령입니다. 관계 이름 해당 명령의 선택을 취소 합니다.

## <a name="see-also"></a>참고 항목
[Visual Studio에서 데이터 집합 만들기 및 구성](../data-tools/create-and-configure-datasets-in-visual-studio.md)