---
title: "Visual Studio O/R 디자이너 개요 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 45e477c0-5c6b-41f9-b2d0-2808fb4f6537
caps.latest.revision: "10"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.openlocfilehash: c493a7ea448277275072ab71cf013333ccb9b4ea
ms.sourcegitcommit: f0ddee934713ea9126fa107018a57a94a05eafd3
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/12/2017
---
# <a name="linq-to-sql-tools-in-visual-studio"></a>LINQ to SQL 도구 Visual Studio에서
LINQ to SQL에는 Microsoft에서 릴리스한 첫 번째 개체-관계형 매핑 기술을 했습니다. 기본 시나리오에서 잘 작동 하 고 계속 Visual Studio에서 지원 하지만 더 이상 현재 개발에 포함 됩니다. LINQ to SQL을 이미 사용 하는 레거시 응용 프로그램 유지 관리 하는 경우 또는 SQL Server를 사용 하는 다중 테이블 매핑이 필요 하지 않은 간단한 응용 프로그램에서 사용 합니다. 일반적으로 새 응용 프로그램 개체 관계형 매퍼 계층에 필요한 경우 Entity Framework를 사용 해야 합니다.  
  
Visual Studio에서 LINQ to SQL 클래스 개체 관계형 디자이너 (O/R 디자이너)를 사용 하 여 SQL 테이블을 표시 하는 만들 있습니다.  
  
[!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]의 디자인 화면은 두 영역으로 구분되어 있습니다. 왼쪽에는 엔터티 창이, 오른쪽에는 메서드 창이 표시됩니다. 엔터티 창은 엔터티 클래스, 연결 및 상속 계층을 표시하는 기본 디자인 화면입니다. 메서드 창은 저장 프로시저와 함수에 매핑되는 <xref:System.Data.Linq.DataContext> 메서드를 표시하는 디자인 화면입니다.  
  
[!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)] 시각적 디자인 화면을 만들기 위한 제공 [LINQ to SQL](/dotnet/framework/data/adonet/sql/linq/index) 엔터티 클래스 및 데이터베이스의 개체를 기반으로 하는 연결 (관계). 즉, [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]는 데이터베이스의 개체에 매핑되는 응용 프로그램의 개체 모델을 만드는 데 사용되며 엔터티 클래스와 데이터베이스 간에 데이터를 주고 받는 데 사용되는 강력한 형식의 <xref:System.Data.Linq.DataContext>를 생성합니다. 또한 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]에서는 데이터를 반환하고 엔터티 클래스를 채우기 위해 저장 프로시저 및 함수를 <xref:System.Data.Linq.DataContext> 메서드에 매핑하는 기능을 제공합니다. 마지막으로 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]에서는 엔터티 클래스 간의 상속 관계를 디자인하는 기능을 제공합니다.  
  
## <a name="opening-the-or-designer"></a>O/R 디자이너 열기  
 LINQ to SQL 엔터티 모델 프로젝트를 추가 하려면 선택 **프로젝트**, **새 항목 추가** 선택한 후 **LINQ to SQL 클래스** 프로젝트 항목의 목록에서:  
  
 ![LINQ to SQL 클래스](../data-tools/media/raddata-linq-to-sql-classes.png "raddata LINQ to SQL 클래스")  
  
 Visual Studio는.dbml 파일을 만들고 솔루션에 추가 합니다. 이것이 XML 매핑 파일 및 해당 관련 된 코드 파일입니다.  
  
 ![솔루션 탐색기에 있는 LINQ to SQL 클래스](../data-tools/media/raddata-linq-to-sql-classes-in-solution-explorer.png "raddata LINQ to SQL 솔루션 탐색기에서 클래스")  
  
 .Dbml 파일을 선택 하면 Visual Studio에 모델을 시각적으로 만들 수 있도록 O/R 디자이너 화면에 표시 됩니다. 다음 그림은 Northwind Customers 및 Orders 테이블 서버 탐색기에서 끌어 놓았을 후 디자이너를 보여 줍니다. 테이블 간의 관계를 note 합니다.  
  
 ![TO SQL 디자이너](../data-tools/media/raddata-linq-to-sql-designer.png "raddata LINQ to SQL 디자이너")  
  
> [!IMPORTANT]
>  [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]는 일대일 매핑 관계만 지원하는 단순 개체 관계형 매퍼입니다. 즉, 엔터티 클래스는 데이터베이스 테이블 또는 뷰와 1:1 매핑 관계만 갖습니다. 조인 된 테이블에 엔터티 클래스 매핑 복잡 한 매핑은 지원 되지 않습니다. 복잡 한 매핑에 대 한 Entity Framework를 사용 합니다. 또한 이 디자이너는 단방향 코드 생성기입니다. 이는 디자이너 화면에서 변경한 내용만이 코드 파일에 반영된다는 의미입니다. 코드 파일에 수동으로 변경한 내용은 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]에 반영되지 않습니다. 코드 파일에서 수동으로 변경한 모든 내용은 디자이너를 저장하고 코드를 다시 생성할 때 덮어쓰여집니다. 에 의해 생성 된 클래스를 확장 하 고 사용자 코드를 추가 하는 방법에 대 한 내용은 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)], 참조 [하는 방법: O/R 디자이너에서 코드 생성 확장](../data-tools/how-to-extend-code-generated-by-the-o-r-designer.md)합니다.  
  
## <a name="creating-and-configuring-the-datacontext"></a>DataContext 만들기 및 구성  
 추가한 후는 **LINQ to SQL 클래스** 항목 열기 및 프로젝트에는 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)], 빈 디자인 화면에는 빈 나타냅니다 <xref:System.Data.Linq.DataContext> 구성 가능한 상태가 됩니다. <xref:System.Data.Linq.DataContext> 디자인 화면으로 끌어 첫 번째 항목에서 제공 하는 연결 정보로 구성 됩니다. 따라서 <xref:System.Data.Linq.DataContext>는 디자인 화면에 놓여진 첫째 항목의 연결 정보를 사용하여 구성됩니다. 에 대 한 자세한 내용은 <xref:System.Data.Linq.DataContext> 클래스 참조 [DataContext 메서드 (O/R 디자이너)](../data-tools/datacontext-methods-o-r-designer.md)합니다.  
  
## <a name="creating-entity-classes-that-map-to-database-tables-and-views"></a>데이터베이스 테이블 및 뷰에 매핑된 엔터티 클래스 만들기  
 데이터베이스 테이블 및 뷰를 끌어 테이블 및 뷰에 매핑할 엔터티 클래스를 만들 수 있습니다 **서버 탐색기**/**데이터베이스 탐색기** 에 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]합니다. 앞 단원에서 설명한 것처럼 <xref:System.Data.Linq.DataContext>는 디자인 화면으로 끌어 온 첫째 항목에서 제공된 연결 정보를 사용하여 구성됩니다. 다른 연결을 사용하는 후속 항목이 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]에 추가되는 경우 <xref:System.Data.Linq.DataContext>에 대한 연결을 변경할 수 있습니다. 자세한 내용은 참조 [하는 방법: 만들 LINQ to SQL 클래스 테이블 및 뷰 (O/R 디자이너) 매핑된](../data-tools/how-to-create-linq-to-sql-classes-mapped-to-tables-and-views-o-r-designer.md)합니다.  
  
## <a name="creating-datacontext-methods-that-call-stored-procedures-and-functions"></a>저장 프로시저 및 함수를 호출하는 DataContext 메서드 만들기  
 만들 수 있습니다 <xref:System.Data.Linq.DataContext> 호출 하는 메서드 (매핑됩니다) 저장 프로시저 및 함수에서 끌어서 **서버 탐색기**/**데이터베이스 탐색기** 는 끌어다[!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]. 저장 프로시저 및 함수는 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]에 <xref:System.Data.Linq.DataContext>의 메서드로 추가됩니다.  
  
> [!NOTE]
>  저장된 프로시저 및 함수를 끌 때 **서버 탐색기**/**데이터베이스 탐색기** 에 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)], 생성 된 반환 형식 <xref:System.Data.Linq.DataContext> 메서드 항목을 드롭 하는 위치에 따라. 자세한 내용은 참조 [DataContext 메서드 (O/R 디자이너)](../data-tools/datacontext-methods-o-r-designer.md)합니다.  
  
## <a name="configuring-a-datacontext-to-use-stored-procedures-to-save-data-between-entity-classes-and-a-database"></a>저장 프로시저를 사용하여 엔터티 클래스와 데이터베이스 간의 데이터를 저장하도록 DataContext 구성  
 앞에서 설명한 대로 저장 프로시저 및 함수를 호출하는 <xref:System.Data.Linq.DataContext> 메서드를 만들 수 있습니다. 또한 삽입, 업데이트 및 삭제를 수행하는 기본 [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] 런타임 동작에 사용될 수 있는 저장 프로시저를 지정할 수 있습니다. 자세한 내용은 참조 [하는 방법: 저장된 프로시저를 할당 업데이트, 삽입 및 삭제 (O/R 디자이너)를 수행](../data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer.md)합니다.  
  
## <a name="inheritance-and-the-or-designer"></a>상속 및 O/R 디자이너  
 다른 개체와 마찬가지로 [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] 클래스도 상속을 사용할 수 있고 다른 클래스에서 파생될 수 있습니다. 데이터베이스에서 상속 관계는 여러 가지 방법으로 만들어집니다. [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]는 관계형 시스템에서 주로 구현되는 단일 테이블 상속 개념을 지원합니다. 자세한 내용은 참조 [하는 방법: O/R 디자이너를 사용 하 여 상속 구성](../data-tools/how-to-configure-inheritance-by-using-the-o-r-designer.md)합니다.  
  
## <a name="linq-to-sql-queries"></a>LINQ to SQL 쿼리  
 만든 엔터티 클래스는 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)] 사용 하도록 설계 [LINQ (Language-Integrated Query)](/dotnet/csharp/linq/)합니다. 자세한 내용은 참조 [하는 방법: 정보에 대 한 쿼리](/dotnet/framework/data/adonet/sql/linq/how-to-query-for-information)합니다.  
  
## <a name="separating-the-generated-datacontext-and-entity-class-code-into-different-namespaces"></a>생성된 DataContext와 엔터티 클래스 코드를 별도의 네임스페이스로 분리  
 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)] 제공는 **컨텍스트 Namespace** 및 **엔터티 Namespace** 속성에는 <xref:System.Data.Linq.DataContext>합니다. 이들 속성은 <xref:System.Data.Linq.DataContext> 및 엔터티 클래스 코드가 어떤 네임스페이스로 생성되는지를 결정합니다. 기본적으로 이들 속성은 비어 있으며 <xref:System.Data.Linq.DataContext> 및 엔터티 클래스는 응용 프로그램의 네임스페이스로 생성됩니다. 응용 프로그램의 네임 스페이스 이외의 네임 스페이스에 코드를 생성 하는 값을 입력에서 **컨텍스트 Namespace** 및/또는 **엔터티 Namespace** 속성입니다.
  
## <a name="reference-content"></a>참조 콘텐츠
<xref:System.Linq>  
<xref:System.Data.Linq>  
  
## <a name="see-also"></a>참고 항목
[LINQ to SQL (.NET Framework)](/dotnet/framework/data/adonet/sql/linq/index)    
[질문과 대답 (.NET Framework)](/dotnet/framework/data/adonet/sql/linq/frequently-asked-questions) 