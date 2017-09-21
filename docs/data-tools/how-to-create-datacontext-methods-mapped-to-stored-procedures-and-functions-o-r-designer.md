---
title: "방법: 저장 프로시저 및 함수에 매핑된 DataContext 메서드 만들기(O/R 디자이너) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: e7ca32f1-50b3-48af-ad92-ceafd749296a
caps.latest.revision: 2
caps.handback.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: 저장 프로시저 및 함수에 매핑된 DataContext 메서드 만들기(O/R 디자이너)
저장 프로시저 및 함수를 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]에 <xref:System.Data.Linq.DataContext> 메서드로 추가할 수 있습니다.메서드를 호출하여 필요한 매개 변수에 전달하면 데이터베이스의 저장 프로시저 또는 함수가 실행되어 <xref:System.Data.Linq.DataContext> 메서드의 반환 형식으로 데이터를 반환합니다.<xref:System.Data.Linq.DataContext> 메서드에 대한 자세한 내용은 [DataContext 메서드\(O\/R 디자이너\)](../data-tools/datacontext-methods-o-r-designer.md)를 참조하십시오.  
  
> [!NOTE]
>  또한 변경 내용을 엔터티 클래스에서 데이터베이스로 저장한 경우 저장 프로시저를 사용하여 삽입, 업데이트 및 삭제를 수행하는 기본 [!INCLUDE[vbtecdlinq](../data-tools/includes/vbtecdlinq_md.md)] 런타임 동작을 재정의할 수 있습니다.자세한 내용은 [방법: 저장 프로시저를 할당하여 업데이트, 삽입 및 삭제 수행\(O\/R 디자이너\)](../data-tools/how-to-assign-stored-procedures-to-perform-updates-inserts-and-deletes-o-r-designer.md)을 참조하십시오.  
  
## DataContext 메서드 만들기  
 **서버 탐색기\/데이터베이스 탐색기**에서 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]로 저장 프로시저 또는 함수를 끌어 와 <xref:System.Data.Linq.DataContext> 메서드를 만들 수 있습니다.  
  
> [!NOTE]
>  생성된 <xref:System.Data.Linq.DataContext> 메서드의 반환 형식은 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]에서 저장 프로시저 또는 함수를 놓는 위치에 따라 달라집니다.항목을 기존 엔터티 클래스에 직접 놓으면 엔터티 클래스의 반환 형식을 갖는 <xref:System.Data.Linq.DataContext> 메서드가 만들어집니다.항목을 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]의 빈 영역에 놓으면 자동으로 생성된 형식을 반환하는 <xref:System.Data.Linq.DataContext> 메서드가 만들어집니다.메서드 창에 추가한 후 <xref:System.Data.Linq.DataContext> 메서드의 반환 형식을 변경할 수 있습니다.<xref:System.Data.Linq.DataContext> 메서드의 반환 형식을 검사하거나 변경하려면 해당 메서드를 선택하고 **속성** 창에서 **반환 형식** 속성을 검사합니다.자세한 내용은 [방법: DataContext 메서드의 반환 형식 변경\(O\/R 디자이너\)](../data-tools/how-to-change-the-return-type-of-a-datacontext-method-o-r-designer.md)을 참조하십시오.  
  
 [!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
#### 자동으로 생성된 형식을 반환하는 DataContext 메서드를 만들려면  
  
1.  **서버 탐색기**\/**데이터베이스 탐색기**에서 작업중인 데이터베이스의 **저장 프로시저** 노드를 확장합니다.  
  
2.  원하는 저장 프로시저를 찾아 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]의 빈 영역으로 끌어 옵니다.  
  
     자동으로 생성된 반환 형식을 갖는 <xref:System.Data.Linq.DataContext> 메서드가 만들어지고 **메서드** 창에 나타납니다.  
  
#### 엔터티 클래스의 반환 형식을 갖는 DataContext 메서드를 만들려면  
  
1.  **서버 탐색기**\/**데이터베이스 탐색기**에서 작업중인 데이터베이스의 **저장 프로시저** 노드를 확장합니다.  
  
2.  원하는 저장 프로시저를 찾아 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]의 기존 엔터티 클래스로 끌어 옵니다.  
  
     선택한 엔터티 클래스의 반환 형식을 갖는 <xref:System.Data.Linq.DataContext> 메서드가 만들어지고 **메서드** 창에 나타납니다.  
  
> [!NOTE]
>  기존 <xref:System.Data.Linq.DataContext> 메서드의 반환 형식 변경에 대한 자세한 내용은 [방법: DataContext 메서드의 반환 형식 변경\(O\/R 디자이너\)](../data-tools/how-to-change-the-return-type-of-a-datacontext-method-o-r-designer.md)을 참조하십시오.  
  
## 참고 항목  
 [O\/R 디자이너\(개체 관계형 디자이너\)](../data-tools/linq-to-sql-tools-in-visual-studio2.md)   
 [DataContext 메서드\(O\/R 디자이너\)](../data-tools/datacontext-methods-o-r-designer.md)   
 [연습: LINQ to SQL 클래스 만들기\(O\/R 디자이너\)](../Topic/Walkthrough:%20Creating%20LINQ%20to%20SQL%20Classes%20\(O-R%20Designer\).md)   
 [LINQ to SQL](../Topic/LINQ%20to%20SQL.md)   
 [Introduction to LINQ in Visual Basic](/dotnet/visual-basic/programming-guide/language-features/linq/introduction-to-linq)   
 [방법: C\#에서 LINQ 쿼리 작성](../Topic/How%20to:%20Write%20LINQ%20Queries%20in%20C%23.md)