---
title: LINQ to SQL 클래스를 O/R 디자이너를 사용 하 여 간의 관계를 만드는 방법
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: 56133e65-81f3-44c3-bc28-ffdd0671a0d2
author: gewarren
ms.author: gewarren
manager: douge
ms.prod: visual-studio-dev15
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 1fee78966a04da53e3b61b85a3440ea8e459771d
ms.sourcegitcommit: e13e61ddea6032a8282abe16131d9e136a927984
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/26/2018
---
# <a name="how-to-create-an-association-between-linq-to-sql-classes-or-designer"></a>방법: LINQ to SQL 클래스 (O/R 디자이너) 간에 연결 만들기
[!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)]에서 엔터티 클래스 간의 연결은 데이터베이스 테이블 간의 관계와 비슷합니다. 사용 하 여 엔터티 클래스 간의 연결을 만들 수는 **연결 편집기** 대화 상자.

사용 하는 경우 부모 클래스와 자식 클래스를 선택 해야 합니다는 **연결 편집기** 대화 상자에서 연결을 만들 합니다. 부모 클래스는 기본 키가 있는 엔터티 클래스이고, 자식 클래스는 외래 키가 있는 엔터티 클래스입니다. 예를 들어 Northwind Customers 및 Orders 테이블에 매핑되는 엔터티 클래스를 만들면 Customer 클래스는 부모 클래스가 되고 Order 클래스는 자식 클래스가 됩니다.

> [!NOTE]
>  테이블을 끌어 오면 **서버 탐색기**/**데이터베이스 탐색기** 에 [!INCLUDE[vs_ordesigner_long](../data-tools/includes/vs_ordesigner_long_md.md)] ([!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]), 연결이 자동으로 기존에 따라 생성 됩니다 데이터베이스에서 외래 키 관계입니다.

## <a name="association-properties"></a>연결 속성
O/R 디자이너에서 연결을 선택 하는 경우, 연결을 만든 후 몇 가지 구성 가능한 속성이에 **속성** 창. 연결은 관련 클래스 간의 선입니다. 다음 표에서는 연결 속성을 설명합니다.

|속성|설명|
|--------------|-----------------|
|**카디널리티**|연결이 일대다 연결인지 또는 일대일 연결인지를 제어합니다.|
|**자식 속성**|연결의 외래 키 쪽에서 자식 레코드의 컬렉션이거나 자식 레코드에 대한 참조인 부모 속성을 만들지 여부를 지정합니다. 예를 들어 Customer와 Order 간의 연결에서에서 하는 경우는 **자식 속성** 로 설정 된 **True**, Orders 라는 속성이 부모 클래스에 만들어집니다.|
|**Parent 속성**|연결된 부모 클래스를 참조하는 자식 클래스의 속성입니다. 예를 들어 Customer와 Order 간의 연결에서 연결된 주문 고객을 참조하는 Customer라는 속성이 Order 클래스에 만들어집니다.|
|**참여 속성**|연결 속성을 표시 하 고 제공 된 **줄임표** 를 다시 여는 단추 (...)는 **연결 편집기** 대화 상자.|
|**고유**|외래 대상 열에 고유성 제약 조건이 있는지 여부를 지정합니다.|

## <a name="to-create-an-association-between-entity-classes"></a>엔터티 클래스 간에 연결을 만들려면

1.  연결에서 부모 클래스를 나타내는 엔터티 클래스를 마우스 오른쪽 단추로 클릭, 가리킨 **추가**, 클릭 하 고 **연결**합니다.

2.  확인 하는 올바른 **부모 클래스** 에서 선택한는 **연결 편집기** 대화 상자.

3.  선택 된 **자식 클래스** 콤보 상자에서 합니다.

4.  선택 된 **연관 속성** 클래스가 관련 된 합니다. 일반적으로 이는 데이터베이스에 정의된 외래 키 관계에 매핑됩니다. 예를 들어 Customers 및 Orders 연결에서에서의 **연관 속성** 은 각 클래스에 대 한 CustomerID입니다.

5.  클릭 **확인** 연결을 만듭니다.

## <a name="see-also"></a>참고자료

- [LINQ to SQL Tools in Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)(Visual Studio의 LINQ to SQL 도구)
- [연습: LINQ to SQL 클래스 만들기](how-to-create-linq-to-sql-classes-mapped-to-tables-and-views-o-r-designer.md)
- [LINQ to SQL](/dotnet/framework/data/adonet/sql/linq/index)
- [DataContext 메서드 (O/R 디자이너)](../data-tools/datacontext-methods-o-r-designer.md)
- [방법: 기본 키 표현](/dotnet/framework/data/adonet/sql/linq/how-to-represent-primary-keys)