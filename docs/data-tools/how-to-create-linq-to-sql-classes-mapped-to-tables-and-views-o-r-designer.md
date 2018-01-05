---
title: "방법: LINQ to SQL 클래스 테이블 및 뷰 (O R 디자이너) 매핑된 만들기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: 0fb78bbc-7a78-4ab4-b32f-85ece912e660
caps.latest.revision: "3"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.workload: data-storage
ms.openlocfilehash: 3d295cc9527aae2f566f5ec4d1ba92a2b129fbd4
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-linq-to-sql-classes-mapped-to-tables-and-views-or-designer"></a>방법: LINQ to SQL 클래스 매핑 테이블 및 뷰에 (O/R 디자이너) 만들기
[!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)]데이터베이스 테이블 및 뷰에 매핑된 클래스 라고 *엔터티 클래스*합니다. 엔터티 클래스는 레코드에 매핑되지만 레코드를 구성 하는 개별 열에 매핑되는 엔터티 클래스의 각 속성입니다. 엔터티 클래스를 기반으로 하는 데이터베이스 테이블 또는 뷰에에서 테이블 또는 뷰를 끌어 만들 **서버 탐색기**/**데이터베이스 탐색기** 에 [LINQ to SQL 도구에서 Visual Studio](../data-tools/linq-to-sql-tools-in-visual-studio2.md)합니다. [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)] 는 클래스를 생성 하 고 특정 적용 [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] 특성이 [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] 기능 (데이터 통신 및 편집 기능과 <xref:System.Data.Linq.DataContext>). 에 대 한 자세한 내용은 [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] 클래스 참조 [LINQ to SQL 개체 모델](/dotnet/framework/data/adonet/sql/linq/the-linq-to-sql-object-model)합니다.  
  
> [!NOTE]
>  [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]는 일대일 매핑 관계만 지원하는 단순 개체 관계형 매퍼입니다. 즉, 엔터티 클래스는 데이터베이스 테이블 또는 뷰와 1:1 매핑 관계만 갖습니다. 엔터티 클래스를 여러 테이블에 매핑하는 복잡한 매핑은 지원되지 않습니다. 그러나 엔터티 클래스를 여러 관련 테이블을 연결하는 뷰에 매핑할 수 있습니다.  
  
## <a name="create-linq-to-sql-classes-that-are-mapped-to-database-tables-or-views"></a>데이터베이스 테이블 또는 뷰에 매핑된 LINQ to SQL 클래스 만들기  
 테이블 또는 뷰를 끌어 **서버 탐색기**/**데이터베이스 탐색기** 에 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)] 외에 엔터티 클래스가 만들어집니다는 <xref:System.Data.Linq.DataContext> 에 사용 되는 메서드 업데이트를 수행 합니다.  
  
 기본적으로 [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] 런타임에서는 업데이트 가능한 엔터티 클래스의 변경 내용을 데이터베이스에 다시 저장하는 논리를 만듭니다. 이 논리는 열 정의 및 기본 키 정보와 같은 테이블 스키마를 기반으로 합니다. 이러한 동작을 원하지 않으면 기본 [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] 런타임 동작을 사용하는 대신 저장 프로시저를 사용하여 삽입, 업데이트 및 삭제를 수행하도록 엔터티 클래스를 구성할 수 있습니다. 자세한 내용은 참조 [하는 방법: 저장된 프로시저를 할당 업데이트, 삽입 및 삭제 (O/R 디자이너)를 수행](../data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer.md)합니다.  
  
[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
#### <a name="to-create-linq-to-sql-classes-that-are-mapped-to-database-tables-or-views"></a>데이터베이스 테이블 또는 뷰에 매핑된 LINQ to SQL 클래스를 만들려면  
  
1.  **서버**/**데이터베이스 탐색기**를 확장 하 고 **테이블** 또는 **뷰** 를 데이터베이스 테이블 찾거나 뷰 응용 프로그램에서 사용 하려면  
  
2.  [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]로 테이블 또는 뷰를 끌어 옵니다.  
  
     엔터티 클래스가 만들어져 디자인 화면에 표시됩니다. 엔터티 클래스에는 선택한 테이블 또는 뷰의 열에 매핑되는 속성이 있습니다.  
  
## <a name="create-an-object-data-source-and-display-the-data-on-a-form"></a>개체 데이터 소스를 만들어 폼에 데이터 표시  
 사용 하 여 엔터티 클래스를 만든 후의 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)], 개체 데이터 소스를 만들고 채울 수 있습니다는 [데이터 소스 창](add-new-data-sources.md) 엔터티 클래스를 사용 합니다.  
  
#### <a name="to-create-an-object-data-source-based-on-linq-to-sql-entity-classes"></a>LINQ to SQL 엔터티 클래스 기반의 개체 데이터 소스를 만들려면  
  
1.  에 **빌드** 메뉴를 클릭 하 여 **솔루션 빌드** 프로젝트를 빌드해야 합니다.  
  
2.  **데이터** 메뉴에서 **데이터 소스 표시**를 클릭합니다.  
  
3.  **데이터 소스** 창에서 **새 데이터 소스 추가**를 클릭합니다.  
  
4.  클릭 **개체** 에 **데이터 소스 형식 선택** 페이지 한 다음 클릭 **다음**합니다.  
  
5.  노드를 확장하여 클래스를 찾아 선택합니다.  
  
    > [!NOTE]
    >  경우는 **고객** 클래스를 사용할 수 없는 경우, 마법사를 취소 합니다. 프로젝트를 빌드할 및 마법사를 다시 실행 합니다.  
  
6.  클릭 **마침** 데이터 소스를 만들고 추가 하는 **고객** 엔터티 클래스를는 **데이터 소스** 창.  
  
7.  항목을 끌어는 **데이터 소스** 창에서 폼으로 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [LINQ to SQL 도구 Visual Studio에서](../data-tools/linq-to-sql-tools-in-visual-studio2.md)   
 [연습: LINQ to SQL 클래스 (O R 디자이너) 만들기](how-to-create-linq-to-sql-classes-mapped-to-tables-and-views-o-r-designer.md)   
 [DataContext 메서드 (O/R 디자이너)](../data-tools/datacontext-methods-o-r-designer.md)   
 [방법: 저장된 프로시저 및 함수 (O/R 디자이너)에 매핑된 DataContext 메서드 만들기](../data-tools/how-to-create-datacontext-methods-mapped-to-stored-procedures-and-functions-o-r-designer.md)   
 [LINQ to SQL 개체 모델](/dotnet/framework/data/adonet/sql/linq/the-linq-to-sql-object-model)   
 [연습: 사용자 지정 삽입, 업데이트 하 고 엔터티 클래스의 동작을 삭제](../data-tools/walkthrough-customizing-the-insert-update-and-delete-behavior-of-entity-classes.md)   
  [방법: LINQ to SQL 클래스 (O/R 디자이너) 사이의 연결 (관계) 만들기](../data-tools/how-to-create-an-association-relationship-between-linq-to-sql-classes-o-r-designer.md)