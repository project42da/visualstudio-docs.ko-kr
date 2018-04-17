---
title: DataContext 메서드 (O R 디자이너) | Microsoft Docs
ms.custom: ''
ms.date: 11/04/2016
ms.topic: conceptual
ms.assetid: c149f4e5-3b61-4c33-892e-3e26d47f3eeb
author: gewarren
ms.author: gewarren
manager: douge
ms.technology: vs-data-tools
ms.workload:
- data-storage
ms.openlocfilehash: 9c0eda7461ffe8f90edfb8b9ddaa10a9fa4caf3b
ms.sourcegitcommit: 6a9d5bd75e50947659fd6c837111a6a547884e2a
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 04/16/2018
---
# <a name="datacontext-methods-or-designer"></a>DataContext 메서드(O/R 디자이너)
<xref:System.Data.Linq.DataContext> 메서드 (의 컨텍스트에서 [LINQ to SQL 도구 Visual Studio에서](../data-tools/linq-to-sql-tools-in-visual-studio2.md))은 방법으로는 <xref:System.Data.Linq.DataContext> 데이터베이스에서 저장된 프로시저 및 함수를 실행 하는 클래스입니다.  
  
 <xref:System.Data.Linq.DataContext> 클래스는 SQL Server 데이터베이스와 해당 데이터베이스에 매핑되는 [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] 엔터티 클래스 간의 연결 통로 역할을 하는 [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] 클래스입니다. <xref:System.Data.Linq.DataContext> 클래스에는 연결 문자열 정보 및 데이터베이스에 연결 하 고 데이터베이스에서 데이터를 조작 하기 위한 메서드가 포함 되어 있습니다. 기본적으로는 <xref:System.Data.Linq.DataContext> 클래스와 같은 호출할 수 있는 여러 메서드가 포함 되어는 <xref:System.Data.Linq.DataContext.SubmitChanges%2A> 업데이트 된 데이터를 보내는 메서드 [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] 데이터베이스에는 클래스입니다. 추가로 만들 수 있습니다 <xref:System.Data.Linq.DataContext> 저장된 프로시저 및 함수에 매핑되는 메서드가 있습니다. 즉 이러한 사용자 지정 메서드를 호출하면 <xref:System.Data.Linq.DataContext> 메서드가 매핑되는 데이터베이스의 저장 프로시저 또는 함수가 실행됩니다. 클래스를 확장하는 메서드를 추가하는 것처럼 <xref:System.Data.Linq.DataContext> 클래스에 새 메서드를 추가할 수 있습니다. 그러나에 대 한 토론에 <xref:System.Data.Linq.DataContext> 의 컨텍스트에서 메서드는 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)], 이기는 <xref:System.Data.Linq.DataContext> 저장된 프로시저 및 해당 함수에 매핑되는 메서드.  
  
## <a name="methods-pane"></a>메서드 창  
 저장 프로시저 및 함수에 매핑되는 <xref:System.Data.Linq.DataContext> 메서드는 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]의 메서드 창에 표시됩니다. 메서드 창 옆쪽에 있는 창입니다는 **엔터티** 창 (기본 디자인 화면). 메서드 창에 모두 나열 <xref:System.Data.Linq.DataContext> 메서드를 사용 하 여 만든는 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]합니다. 기본적으로 메서드 창은 비어 있습니다. 저장된 프로시저 또는 함수에서 끌어 **서버 탐색기**/**데이터베이스 탐색기** 에 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)] 만들려는 <xref:System.Data.Linq.DataContext> 메서드 메서드 창을 채웁니다. 자세한 내용은 참조 [하는 방법: 저장된 프로시저 및 함수 (O/R 디자이너)에 매핑된 DataContext 만들기 메서드](../data-tools/how-to-create-datacontext-methods-mapped-to-stored-procedures-and-functions-o-r-designer.md)합니다.  
  
> [!NOTE]
>  열기 및 마우스 오른쪽 단추로 클릭 하 여 메서드 창 닫기는 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)] 클릭 한 다음 **메서드 창 숨김** 또는 **메서드 창 표시**, 하거나 바로 가기 키 CTRL + 1을 사용 합니다.  
  
## <a name="two-types-of-datacontext-methods"></a>DataContext 메서드의 두 가지 형식  
 DataContext 메서드는 데이터베이스의 저장 프로시저와 함수에 매핑되는 메서드로 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]의 메서드 창에서 만들고 추가할 수 있습니다. 두 가지 유형의 없는 <xref:System.Data.Linq.DataContext> ; 하나 이상의 결과 집합을 반환 하는 메서드와 하지 않는:  
  
-   결과 집합을 하나 이상 반환하는 <xref:System.Data.Linq.DataContext> 메서드  
  
     응용 프로그램이 저장 프로시저 및 함수를 데이터베이스에서 실행하고 결과를 반환하는 작업만 수행할 때 이 <xref:System.Data.Linq.DataContext> 메서드를 만듭니다. 자세한 내용은 참조 [하는 방법: 저장된 프로시저 및 함수 (O/R 디자이너)에 매핑된 DataContext 만들기 메서드](../data-tools/how-to-create-datacontext-methods-mapped-to-stored-procedures-and-functions-o-r-designer.md), System.Data.Linq.ISingleResult\<T >, 및 <xref:System.Data.Linq.IMultipleResults>합니다.  
  
-   특정 엔터티 클래스에 대한 Inserts, Updates, Deletes 등과 같이 결과 집합을 반환하지 않는 <xref:System.Data.Linq.DataContext> 메서드  
  
     이 종류의 만들기 <xref:System.Data.Linq.DataContext> 메서드를 응용 프로그램에 기본값을 사용 하는 대신 저장된 프로시저를 실행할 때 [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] 절약 시간제에 대해 동작이 엔터티 클래스와 데이터베이스 간에 데이터를 수정 합니다. 자세한 내용은 참조 [하는 방법: 저장된 프로시저를 할당 업데이트, 삽입 및 삭제 (O/R 디자이너)를 수행](../data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer.md)합니다.  
  
## <a name="return-types-of-datacontext-methods"></a>DataContext 메서드의 반환 형식  
 저장된 프로시저 및 함수를 끌 때 **서버 탐색기**/**데이터베이스 탐색기** 에 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)], 생성 된 반환 형식 <xref:System.Data.Linq.DataContext> 메서드 항목을 드롭 하는 위치에 따라. 항목을 기존 엔터티 클래스 위에 직접 놓으면 만듭니다는 <xref:System.Data.Linq.DataContext> 엔터티 클래스의 반환 형식 갖는 방법으로,의 빈 영역으로 항목 삭제는 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)] 두 창 중 하나에 만듭니다는 <xref:System.Data.Linq.DataContext> 반환 하는 메서드는 자동으로 생성 된 형식입니다. 만든 자동 생성 형식의 이름은 저장 프로시저 또는 함수가 반환한 필드에 매핑되는 저장 프로시저 또는 함수의 이름 및 속성과 일치합니다.  
  
> [!NOTE]
>  메서드 창에 추가한 후 <xref:System.Data.Linq.DataContext> 메서드의 반환 형식을 변경할 수 있습니다. 반환 형식을 검사 하거나 변경 하는 <xref:System.Data.Linq.DataContext> 메서드를 선택 하 고 검사는 **반환 형식** 속성에는 **속성** 창. 자세한 내용은 참조 [하는 방법: DataContext 메서드 (O/R 디자이너)의 반환 형식을 변경](../data-tools/how-to-change-the-return-type-of-a-datacontext-method-o-r-designer.md)합니다.  
  
 데이터베이스에서 O/R 디자이너 화면으로 끌어 오는 개체는 데이터베이스의 개체 이름을 기초로 이름이 자동으로 지정됩니다. 같은 개체를 두 번 이상 끌어 오면 이름을 구별할 수 있도록 새 이름 끝에 숫자가 추가됩니다. 데이터베이스 개체 이름에 공백이 포함되어 있거나 Visual Basic 또는 C#에서 지원되지 않는 문자가 사용되었으면 해당 공백이나 잘못된 문자가 밑줄로 대체됩니다.  
  
## <a name="see-also"></a>참고 항목  
 [LINQ to SQL 도구 Visual Studio에서](../data-tools/linq-to-sql-tools-in-visual-studio2.md)   
 [LINQ to SQL](/dotnet/framework/data/adonet/sql/linq/index)   
 [저장된 프로시저](/dotnet/framework/data/adonet/sql/linq/stored-procedures)   
 [방법: 저장된 프로시저 및 함수 (O/R 디자이너)에 매핑된 DataContext 메서드 만들기](../data-tools/how-to-create-datacontext-methods-mapped-to-stored-procedures-and-functions-o-r-designer.md)   
 [방법: 저장된 프로시저를 할당 업데이트, 삽입 및 삭제 (O/R 디자이너)를 수행 합니다.](../data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer.md)   
 [연습: 사용자 지정 삽입, 업데이트 하 고 엔터티 클래스의 동작을 삭제](../data-tools/walkthrough-customizing-the-insert-update-and-delete-behavior-of-entity-classes.md)   
 [연습: LINQ to SQL 클래스 (O R 디자이너) 만들기](how-to-create-linq-to-sql-classes-mapped-to-tables-and-views-o-r-designer.md)