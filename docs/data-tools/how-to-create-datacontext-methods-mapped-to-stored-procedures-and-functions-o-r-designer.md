---
title: "방법: 저장된 프로시저 및 함수 (O R 디자이너)에 매핑된 DataContext 메서드 만들기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: e7ca32f1-50b3-48af-ad92-ceafd749296a
caps.latest.revision: "2"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.workload: data-storage
ms.openlocfilehash: a56bacfd2d726e2ec7bedf69f6c79ce347e3556e
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-create-datacontext-methods-mapped-to-stored-procedures-and-functions-or-designer"></a>방법: 저장된 프로시저 및 함수 (O/R 디자이너)에 매핑된 DataContext 메서드 만들기
저장된 프로시저 및 함수에 추가할 수는 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)] 으로 <xref:System.Data.Linq.DataContext> 메서드. 메서드를 호출 하 고 필요한 매개 변수에 전달은 데이터베이스에서 저장된 프로시저 또는 함수를 실행 하 고 데이터의 반환 형식에 반환 된 <xref:System.Data.Linq.DataContext> 메서드. 에 대 한 자세한 내용은 <xref:System.Data.Linq.DataContext> 메서드 참조 [DataContext 메서드 (O/R 디자이너)](../data-tools/datacontext-methods-o-r-designer.md)합니다.  
  
> [!NOTE]
>  또한 변경 내용을 엔터티 클래스에서 데이터베이스로 저장한 경우 저장 프로시저를 사용하여 삽입, 업데이트 및 삭제를 수행하는 기본 [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] 런타임 동작을 재정의할 수 있습니다. 자세한 내용은 참조 [하는 방법: 저장된 프로시저를 할당 업데이트, 삽입 및 삭제 (O/R 디자이너)를 수행](../data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer.md)합니다.  
  
## <a name="creating-datacontext-methods"></a>DataContext 메서드 만들기  
 만들 수 있습니다 <xref:System.Data.Linq.DataContext> 끌어 메서드 저장 프로시저 또는 함수에서 **서버 탐색기/데이터베이스 탐색기** 에 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]합니다.  
  
> [!NOTE]
>  생성된 <xref:System.Data.Linq.DataContext> 메서드의 반환 형식은 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]에서 저장 프로시저 또는 함수를 놓는 위치에 따라 달라집니다. 항목을 기존 엔터티 클래스에 직접 놓으면 엔터티 클래스의 반환 형식을 갖는 <xref:System.Data.Linq.DataContext> 메서드가 만들어집니다. 항목을 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]의 빈 영역에 놓으면 자동으로 생성된 형식을 반환하는 <xref:System.Data.Linq.DataContext> 메서드가 만들어집니다. 반환 형식을 변경할 수는 <xref:System.Data.Linq.DataContext> 메서드 창에 추가한 후 메서드. 반환 형식을 검사 하거나 변경 하는 <xref:System.Data.Linq.DataContext> 메서드를 선택 하 고 검사는 **반환 형식** 속성에는 **속성** 창. 자세한 내용은 참조 [하는 방법: DataContext 메서드 (O/R 디자이너)의 반환 형식을 변경](../data-tools/how-to-change-the-return-type-of-a-datacontext-method-o-r-designer.md)합니다.  
  
[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
#### <a name="to-create-datacontext-methods-that-return-automatically-generated-types"></a>자동으로 생성된 형식을 반환하는 DataContext 메서드를 만들려면  
  
1.  **서버 탐색기**/**데이터베이스 탐색기**를 확장 하 고는 **Stored Procedures** 사용 하는 데이터베이스의 노드.  
  
2.  원하는 저장 프로시저를 찾아 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]의 빈 영역으로 끌어 옵니다.  
  
     <xref:System.Data.Linq.DataContext> 메서드가 자동으로 생성된 된 반환 형식을 갖는 만들어지고에 표시 된 **메서드** 창.  
  
#### <a name="to-create-datacontext-methods-that-have-the-return-type-of-an-entity-class"></a>엔터티 클래스의 반환 형식을 갖는 DataContext 메서드를 만들려면  
  
1.  **서버 탐색기**/**데이터베이스 탐색기**를 확장 하 고는 **Stored Procedures** 사용 하는 데이터베이스의 노드.  
  
2.  원하는 저장 프로시저를 찾아 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]의 기존 엔터티 클래스로 끌어 옵니다.  
  
     <xref:System.Data.Linq.DataContext> 메서드가 선택한 엔터티 클래스의 반환 형식을 갖는 만들어지고에 표시 된 **메서드** 창.  
  
> [!NOTE]
>  기존 반환 형식을 변경 하는 방법에 대 한 정보에 대 한 <xref:System.Data.Linq.DataContext> 메서드 참조 [하는 방법: DataContext 메서드 (O/R 디자이너)의 반환 형식을 변경](../data-tools/how-to-change-the-return-type-of-a-datacontext-method-o-r-designer.md)합니다.  
  
## <a name="see-also"></a>참고 항목  
 [LINQ to SQL 도구 Visual Studio에서](../data-tools/linq-to-sql-tools-in-visual-studio2.md)   
 [DataContext 메서드 (O/R 디자이너)](../data-tools/datacontext-methods-o-r-designer.md)   
 [연습: LINQ to SQL 클래스 만들기](how-to-create-linq-to-sql-classes-mapped-to-tables-and-views-o-r-designer.md)   
 [LINQ to SQL](/dotnet/framework/data/adonet/sql/linq/index)   
 [Visual Basic의 LINQ 소개](/dotnet/visual-basic/programming-guide/language-features/linq/introduction-to-linq)   
 [C#의 LINQ](/dotnet/csharp/linq/linq-in-csharp)