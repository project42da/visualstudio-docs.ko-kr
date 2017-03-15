---
title: "LINQ to SQL 도구 Visual Studio2에서 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 45e477c0-5c6b-41f9-b2d0-2808fb4f6537
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# LINQ to SQL 도구 Visual Studio에서
LINQ to SQL에는 첫 번째 개체-관계형 매핑 기술은 Microsoft에서 출시 했습니다. 기본 시나리오에서 잘 작동 하 고 계속 Visual Studio에서 지원 하지만 더 이상 현재 개발 중인 쉽습니다. LINQ to SQL은 이미 사용 하는 레거시 응용 프로그램을 유지 관리할 때 또는 SQL Server를 사용 하는 다중 테이블 매핑할 필요가 없는 간단한 응용 프로그램에서 사용 합니다. 일반적으로 새 응용 프로그램 개체 관계형 매퍼 레이어 필요할 때 Entity Framework를 사용 해야 합니다.  
  
 Visual Studio에서 만들면 LINQ to SQL 클래스를 사용 하 여 SQL 테이블을 나타내는 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]합니다.  
  
 
          [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]의 디자인 화면은 두 영역으로 구분되어 있습니다. 왼쪽에는 엔터티 창이, 오른쪽에는 메서드 창이 표시됩니다. 엔터티 창은 엔터티 클래스, 연결 및 상속 계층을 표시하는 기본 디자인 화면입니다. 메서드 창에는 표시 하는 디자인 화면에서 <xref:System.Data.Linq.DataContext> 저장된 프로시저 및 함수에 매핑되는 방법입니다.  
  
  [!INCLUDE[vs_ordesigner_long](../data-tools/includes/vs_ordesigner_long_md.md)] ([!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)])을 만들기 위한 시각적 디자인 화면을 제공 [LINQ to SQL](../Topic/LINQ%20to%20SQL.md) 엔터티 클래스와 데이터베이스의 개체를 기반으로 하는 연결 (관계). 즉, [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]는 데이터베이스의 개체에 매핑되는 응용 프로그램의 개체 모델을 만드는 데 사용되며 또한 강력한 형식의 생성 <xref:System.Data.Linq.DataContext> 엔터티 클래스와 데이터베이스 간에 데이터를 주고받는 데 사용 됩니다.  [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)] 또한 저장된 프로시저를 매핑하는 기능을 제공 하 고 함수를 <xref:System.Data.Linq.DataContext> 데이터를 반환 하 고 엔터티 클래스를 채우기 위한 메서드. 마지막으로 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]에서는 엔터티 클래스 간의 상속 관계를 디자인하는 기능을 제공합니다.  
  
## <a name="opening-the-or-designer"></a>O/R 디자이너 열기  
 LINQ to SQL 엔터티 모델 프로젝트를 추가 하려면 선택 **프로젝트 &#124; 새 항목 추가** 선택  **LINQ to SQL 클래스** 프로젝트 항목의 목록에서:  
  
 ![LINQ to SQL 클래스](../data-tools/media/raddata-linq-to-sql-classes.png "raddata LINQ to SQL Classes")  
  
 Visual Studio는.dbml 파일을 만들고 솔루션에 추가 합니다. 이것은 XML 매핑 파일 및 해당 관련된 코드 파일입니다.  
  
 ![LINQ to SQL 클래스 솔루션 탐색기에서](../data-tools/media/raddata-linq-to-sql-classes-in-solution-explorer.png "raddata LINQ to SQL classes in Solution Explorer")  
  
 .Dbml 파일을 선택 하면 Visual Studio에서는 O/R 디자이너 화면에 시각적으로 모델을 만들 수 있도록 합니다. 다음 그림에서는 서버 탐색기에서 끌어 놓았을 Northwind Customers 및 Orders 테이블 후 디자이너를 보여 줍니다. 테이블 간의 관계를 note 합니다.  
  
 ![LINQ to SQL 디자이너](../data-tools/media/raddata-linq-to-sql-designer.png "raddata LINQ to SQL Designer")  
  
> [!IMPORTANT]
>  
          [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]는 일대일 매핑 관계만 지원하는 단순 개체 관계형 매퍼입니다. 즉, 엔터티 클래스는 데이터베이스 테이블 또는 뷰와 1:1 매핑 관계만 갖습니다. 엔터티 클래스를 조인 된 테이블에 매핑하는 등의 복잡 한 매핑은 지원 되지 않습니다. 복잡 한 매핑에 대 한 Entity Framework를 사용 합니다. 또한 이 디자이너는 단방향 코드 생성기입니다. 이는 디자이너 화면에서 변경한 내용만이 코드 파일에 반영된다는 의미입니다. 코드 파일에 수동으로 변경한 내용은 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]에 반영되지 않습니다. 코드 파일에서 수동으로 변경한 모든 내용은 디자이너를 저장하고 코드를 다시 생성할 때 덮어쓰여집니다. 에 의해 생성 된 클래스를 확장 하 고 사용자 코드를 추가 하는 방법에 대 한 내용은 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)], 참조 [하는 방법: O/R 디자이너에서 코드 생성 확장](../Topic/How%20to:%20Extend%20Code%20Generated%20by%20the%20O-R%20Designer.md)합니다.  
  
## <a name="creating-and-configuring-the-datacontext"></a>DataContext 만들기 및 구성  
 추가한 후는 **LINQ to SQL 클래스** 열기 및 프로젝트에 항목은 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)], 빈 디자인 화면에는 빈 나타냅니다 <xref:System.Data.Linq.DataContext> 구성할 준비가 됩니다.  <xref:System.Data.Linq.DataContext> 디자인 화면으로 끌어 온 첫째 항목에서 제공 하는 연결 정보로 구성 됩니다. 따라서는 <xref:System.Data.Linq.DataContext> 디자인 화면에 놓여진 첫째 항목에서 연결 정보를 사용 하 여 구성 됩니다. 에 대 한 자세한 내용은 <xref:System.Data.Linq.DataContext> 클래스 참조 [DataContext 메서드 (O/R 디자이너)](../data-tools/datacontext-methods-o-r-designer.md)합니다.  
  
## <a name="creating-entity-classes-that-map-to-database-tables-and-views"></a>데이터베이스 테이블 및 뷰에 매핑된 엔터티 클래스 만들기  
 데이터베이스 테이블 및 뷰를 끌어 테이블 및 뷰에 매핑된 엔터티 클래스를 만들 수 있습니다 **서버 탐색기**/**데이터베이스 탐색기** 에 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]합니다. 이전 섹션에 표시 된 대로 <xref:System.Data.Linq.DataContext> 디자인 화면으로 끌어 온 첫째 항목에서 제공 된 연결 정보로 구성 되어 있습니다. 다른 연결을 사용 하는 후속 항목에 추가 됩니다는 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)], 에 대 한 연결을 변경할 수는 <xref:System.Data.Linq.DataContext>합니다. 자세한 내용은 참조 [하는 방법: 만들기 LINQ to SQL 클래스 테이블 및 뷰 (O/R 디자이너)에 매핑된](../Topic/How%20to:%20Create%20LINQ%20to%20SQL%20classes%20mapped%20to%20tables%20and%20views%20\(O-R%20Designer\).md)합니다.  
  
## <a name="creating-datacontext-methods-that-call-stored-procedures-and-functions"></a>저장 프로시저 및 함수를 호출하는 DataContext 메서드 만들기  
 만들 수 있습니다 <xref:System.Data.Linq.DataContext> 메서드를 호출 하는 (매핑됩니다) 저장 프로시저 및 함수에서 끌어서 **서버 탐색기**/**데이터베이스 탐색기** 에 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]합니다. 저장된 프로시저 및 함수에 추가 되는 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)] 의 메서드로 <xref:System.Data.Linq.DataContext>합니다.  
  
> [!NOTE]
>  저장된 프로시저 및 함수를 끌어 오면 **서버 탐색기**/**데이터베이스 탐색기** 에 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)], 생성 된 반환 형식이 <xref:System.Data.Linq.DataContext> 메서드 항목을 놓는 위치에 따라 달라 집니다. 자세한 내용은 참조 [DataContext 메서드 (O/R 디자이너)](../data-tools/datacontext-methods-o-r-designer.md)합니다.  
  
## <a name="configuring-a-datacontext-to-use-stored-procedures-to-save-data-between-entity-classes-and-a-database"></a>저장 프로시저를 사용하여 엔터티 클래스와 데이터베이스 간의 데이터를 저장하도록 DataContext 구성  
 앞서 설명한 것 처럼 만들 수 있습니다 <xref:System.Data.Linq.DataContext> 저장된 프로시저 및 함수를 호출 하는 메서드입니다. 또한 삽입, 업데이트 및 삭제를 수행하는 기본 [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] 런타임 동작에 사용될 수 있는 저장 프로시저를 지정할 수 있습니다. 자세한 내용은 참조 [하는 방법: 저장된 프로시저를 할당 업데이트, 삽입 및 삭제 (O/R 디자이너)를 수행](../data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer.md)합니다.  
  
## <a name="inheritance-and-the-or-designer"></a>상속 및 O/R 디자이너  
 다른 개체와 마찬가지로 [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] 클래스도 상속을 사용할 수 있고 다른 클래스에서 파생될 수 있습니다. 데이터베이스에서 상속 관계는 여러 가지 방법으로 만들어집니다. [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]는 관계형 시스템에서 주로 구현되는 단일 테이블 상속 개념을 지원합니다. 자세한 내용은 참조 [하는 방법: O/R 디자이너를 사용 하 여 상속 구성](../data-tools/how-to-configure-inheritance-by-using-the-o-r-designer.md)합니다.  
  
## <a name="linq-to-sql-queries"></a>LINQ to SQL 쿼리  
 만든 엔터티 클래스는 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)] 사용 하도록 설계 된 [LINQ (Language-Integrated Query)](../Topic/LINQ%20\(Language-Integrated%20Query\).md)합니다. 자세한 내용은 참조 [하는 방법: 정보 쿼리](../Topic/How%20to:%20Query%20for%20Information.md)합니다.  
  
## <a name="separating-the-generated-datacontext-and-entity-class-code-into-different-namespaces"></a>생성된 DataContext와 엔터티 클래스 코드를 별도의 네임스페이스로 분리  
  [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)] 제공는 **컨텍스트 네임 스페이스** 및 **엔터티 네임 스페이스** 속성에는 <xref:System.Data.Linq.DataContext>합니다. 이러한 속성 결정 네임 스페이스는 <xref:System.Data.Linq.DataContext> 에 엔터티 클래스 코드가 생성 됩니다. 기본적으로 이러한 속성은 빈 및 <xref:System.Data.Linq.DataContext> 및 엔터티 클래스는 응용 프로그램의 네임 스페이스에 생성 됩니다. 에 값을 입력 하는 응용 프로그램의 네임 스페이스 이외의 네임 스페이스에 코드를 생성 하는 **컨텍스트 네임 스페이스** 및/또는 **엔터티 네임 스페이스** 속성입니다.  
  
## <a name="in-this-section"></a>단원 내용  
 [DataContext 메서드 (O/R 디자이너)](../data-tools/datacontext-methods-o-r-designer.md)  
 파악할 <xref:System.Data.Linq.DataContext> 메서드 및를 만드는 방법.  
  
 [데이터 클래스 상속 (O/R 디자이너)](../data-tools/data-class-inheritance-o-r-designer.md)  
 단일 테이블 상속의 개념과 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]에서의 구현 방법에 대해 설명합니다.  
  
 [방법: LINQ to SQL 클래스 테이블 및 뷰 (O/R 디자이너)에 매핑된 만들기](../Topic/How%20to:%20Create%20LINQ%20to%20SQL%20classes%20mapped%20to%20tables%20and%20views%20\(O-R%20Designer\).md)  
 데이터베이스에서 테이블 및 뷰에 매핑되는 엔터티 클래스를 만드는 방법에 대해 설명합니다.  
  
 [방법: LINQ to SQL 클래스 (O/R 디자이너) 사이 연결 (관계) 만들기](../data-tools/how-to-create-an-association-relationship-between-linq-to-sql-classes-o-r-designer.md)  
 [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] 엔터티 클래스 간의 관계를 만드는 방법에 대해 설명합니다.  
  
 [방법: 저장된 프로시저 및 함수 (O/R 디자이너)에 매핑된 DataContext 메서드 만들기](../data-tools/how-to-create-datacontext-methods-mapped-to-stored-procedures-and-functions-o-r-designer.md)  
 만드는 방법을 설명 <xref:System.Data.Linq.DataContext> 호출 될 때 저장된 프로시저 또는 함수를 실행 하는 방법입니다.  
  
 [방법: 저장된 프로시저를 할당 업데이트, 삽입 및 삭제 (O/R 디자이너)를 수행 합니다.](../data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer.md)  
 구성 하는 방법에 설명는 <xref:System.Data.Linq.DataContext> 클래스 다시 엔터티에서 데이터를 저장할 때 저장된 프로시저를 사용 하는 데이터베이스에 있습니다.  
  
 [방법: DataContext 메서드 (O/R 디자이너)의 반환 형식 변경](../data-tools/how-to-change-the-return-type-of-a-datacontext-method-o-r-designer.md)  
 반환 형식을 설정 하는 방법에 설명 된 <xref:System.Data.Linq.DataContext> 메서드를 엔터티 클래스의 형식 또는 O/R 디자이너에서 만든 자동 생성 된 형식 이어야 합니다.  
  
 [방법: 엔터티 클래스에 유효성 검사 추가](../data-tools/how-to-add-validation-to-entity-classes.md)  
 속성 변경 및 엔터티 클래스 업데이트 동안 코드를 추가할 수 있도록 해주는 부분 메서드(Partial Method)를 생성하는 방법에 대해 설명합니다.  
  
 [방법: 복수형 설정 및 해제 (O/R 디자이너)](../data-tools/how-to-turn-pluralization-on-and-off-o-r-designer.md)  
 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]에 추가된 클래스의 자동 이름 바꾸기를 설정하고 해제하는 방법에 대해 설명합니다.  
  
 [방법: O/R 디자이너를 사용 하 여 상속 구성](../data-tools/how-to-configure-inheritance-by-using-the-o-r-designer.md)  
 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]에서 단일 테이블 상속을 사용하여 엔터티 클래스를 구성하는 방법에 대해 설명합니다.  
  
 [방법: O/R 디자이너에서 생성 된 코드 확장](../Topic/How%20to:%20Extend%20Code%20Generated%20by%20the%20O-R%20Designer.md)  
 O/R 디자이너에 있는 개체를 변경함으로써 코드가 다시 생성될 때 덮어쓰여지지 않을 코드를 추가하는 방법과 위치에 대해 설명합니다.  
  
 [연습: 단일 테이블 상속 (O/R 디자이너)를 사용 하 여 LINQ to SQL 클래스 만들기](../data-tools/walkthrough-creating-linq-to-sql-classes-by-using-single-table-inheritance-o-r-designer.md)  
 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]에서 단일 테이블 상속을 사용하여 엔터티 클래스를 구성하는 단계별 지침을 제공합니다.  
  
 [연습: 사용자 삽입 지정을 업데이트 하 고, 엔터티 클래스의 동작을 삭제 합니다.](../data-tools/walkthrough-customizing-the-insert-update-and-delete-behavior-of-entity-classes.md)  
 구성에 대 한 단계별 지침을 제공는 <xref:System.Data.Linq.DataContext> 클래스 다시 엔터티에서 데이터를 저장할 때 저장된 프로시저를 사용 하는 데이터베이스에 있습니다.  
  
## <a name="reference-content"></a>참조 콘텐츠  
 <xref:System.Linq>  
  
 <xref:System.Data.Linq>  
  
## <a name="see-also"></a>참고 항목  
 [.NET 용 visual Studio 데이터 도구](../data-tools/visual-studio-data-tools-for-dotnet.md)   
 [질문과 대답](../Topic/Frequently%20Asked%20Questions.md)   
 [LINQ to SQL](../Topic/LINQ%20to%20SQL.md)   
 [Visual Studio에서 데이터 액세스](../data-tools/accessing-data-in-visual-studio.md)