---
title: 데이터 클래스 상속 (O R 디자이너) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: af32653c-f4e6-4217-8c5a-e32b322b4918
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: a27b3978e1cfad5cb2fefae63104dc51c2efdc50
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="data-class-inheritance-or-designer"></a>데이터 클래스 상속 (O/R 디자이너)
다른 개체와 마찬가지로 [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] 클래스도 상속을 사용할 수 있고 다른 클래스에서 파생될 수 있습니다. 코드에서 클래스 하나가 다른 클래스에서 상속되도록 선언하여 개체 간의 상속 관계를 지정할 수 있습니다. 데이터베이스에서 상속 관계는 여러 가지 방법으로 만들어집니다. [!INCLUDE[vs_ordesigner_long](../data-tools/includes/vs_ordesigner_long_md.md)] ([!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)])는 관계형 시스템에서 주로 구현되는 단일 테이블 상속 개념을 지원합니다.  
  
 단일 테이블 상속에서는 기본 클래스와 파생 클래스의 열을 모두 포함하는 데이터베이스 테이블이 하나 있습니다. 관계형 데이터의 경우 판별자 열에는 해당 레코드가 어느 클래스에 속해 있는지를 판별하는 값이 포함됩니다. 예를 들어 회사에 고용되어 있는 모든 사람들이 포함되어 있는 Persons 테이블을 생각해 봅시다. 어떤 사람들은 사원이고 어떤 사람들은 관리자입니다. Persons 테이블에는 관리자의 값이 1이고 직원의 값이 2인 Type이라는 이름의 열이 있습니다. Type 열은 판별자 열입니다. 이 시나리오에서는 직원 서브클래스를 만든 후 Type 값이 2인 레코드로만 클래스를 채울 수 있습니다.  
  
 사용 하 여 엔터티 클래스에서 상속을 구성 하는 경우는 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]를 두 번 디자이너 하려면 상속 데이터가 들어 있는 단일 테이블을 끌어: 상속 계층 구조의 각 클래스에 대해 한 번입니다. 테이블 디자이너에 추가한 후 놓고 연결한 상속 항목을는 **개체 관계형 디자이너** 도구 상자와 다음의 네 가지 상속 속성 설정에는 **속성** 창.  
  
## <a name="inheritance-properties"></a>상속 속성  
 다음 표에는 상속 속성과 해당 설명이 나와 있습니다.  
  
|속성|설명|  
|--------------|-----------------|  
|Discriminator Property|현재 레코드가 속해 있는 클래스를 결정하는 속성이며 열에 매핑됩니다.|  
|Base Class Discriminator Value|Discriminator Property로 지정된 열에서 레코드가 기본 클래스에 속함을 나타내는 값입니다.|  
|Derived Class Discriminator Value|Discriminator Property로 지정된 속성에서 레코드가 파생 클래스에 속함을 나타내는 값입니다.|  
|Inheritance Default|속성의 값으로 지정 하는 경우에 채워지는 클래스는 **판별자 속성** 일치 하지 않습니다는 **Base Class Discriminator Value** 또는 **파생 클래스 판별자 값**합니다.|  
  
 상속을 사용하고 관계형 데이터에 대응하는 개체 모델을 만드는 것은 다소 복잡할 수 있습니다. 이 항목에서는 상속을 구성하는 데 필요한 기본 개념과 개별 속성에 대한 정보를 제공합니다. 다음 항목에서는 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]를 사용하여 상속을 구성하는 방법을 자세하게 설명합니다.  
  
|항목|설명|  
|-----------|-----------------|  
|[방법: O/R 디자이너를 사용 하 여 상속 구성](../data-tools/how-to-configure-inheritance-by-using-the-o-r-designer.md)|[!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]를 사용하여 단일 테이블 상속을 사용하는 엔터티 클래스를 구성하는 방법을 설명합니다.|  
|[연습: 단일 테이블 상속 (O/R 디자이너)를 사용 하 여 LINQ to SQL 클래스 만들기](../data-tools/walkthrough-creating-linq-to-sql-classes-by-using-single-table-inheritance-o-r-designer.md)|[!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]를 사용하여 단일 테이블 상속을 사용하는 엔터티 클래스를 구성하는 방법에 대한 단계별 지침을 제공합니다.|  
  
## <a name="see-also"></a>참고 항목  
 [LINQ to SQL 도구 Visual Studio에서](../data-tools/linq-to-sql-tools-in-visual-studio2.md)   
 [연습: LINQ to SQL 클래스 (O R 디자이너) 만들기](how-to-create-linq-to-sql-classes-mapped-to-tables-and-views-o-r-designer.md)   
 [연습: 단일 테이블 상속 (O/R 디자이너)를 사용 하 여 LINQ to SQL 클래스 만들기](../data-tools/walkthrough-creating-linq-to-sql-classes-by-using-single-table-inheritance-o-r-designer.md)   
 [시작](/dotnet/framework/data/adonet/sql/linq/getting-started)