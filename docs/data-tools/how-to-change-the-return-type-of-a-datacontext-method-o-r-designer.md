---
title: "방법: DataContext 메서드의 반환 형식 변경(O/R 디자이너) | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: c5b66bff-6dbb-43c0-bffa-317133ca5b9e
caps.latest.revision: 2
caps.handback.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 방법: DataContext 메서드의 반환 형식 변경(O/R 디자이너)
저장 프로시저 또는 함수를 기반으로 만들어진 <xref:System.Data.Linq.DataContext> 메서드의 반환 형식은 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]에서 저장 프로시저 또는 함수를 놓는 위치에 따라 달라집니다.저장 프로시저 또는 함수에서 반환된 데이터의 스키마가 엔터티 클래스의 모양과 일치하는 경우 항목을 기존 엔터티 클래스에 직접 놓으면 엔터티 클래스의 반환 형식을 갖는 <xref:System.Data.Linq.DataContext> 메서드가 만들어집니다.항목을 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]의 빈 영역에 놓으면 자동으로 생성된 형식을 반환하는 <xref:System.Data.Linq.DataContext> 메서드가 만들어집니다.메서드 창에 추가한 후 <xref:System.Data.Linq.DataContext> 메서드의 반환 형식을 변경할 수 있습니다.<xref:System.Data.Linq.DataContext> 메서드의 반환 형식을 검사하거나 변경하려면 해당 메서드를 선택하고 **속성** 창에서 **반환 형식** 속성을 클릭합니다.  
  
> [!NOTE]
>  반환 형식을 엔터티 클래스로 설정한 <xref:System.Data.Linq.DataContext> 메서드를 **속성** 창을 사용하여 자동 생성된 형식을 반환하도록 되돌릴 수 없습니다.자동으로 생성된 형식을 반환하도록 <xref:System.Data.Linq.DataContext> 메서드를 되돌리려면 원래 데이터베이스 개체를 O\/R 디자이너로 끌어 와야 합니다.  
  
 [!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
### DataContext 메서드의 반환 형식을 자동으로 생성된 형식에서 엔터티 클래스로 변경하려면  
  
1.  메서드 창에서 <xref:System.Data.Linq.DataContext> 메서드를 선택합니다.  
  
2.  **속성** 창에서 **반환 형식**을 선택한 다음 **반환 형식** 목록에서 사용 가능한 엔터티 클래스를 선택합니다.원하는 엔터티 클래스가 목록에 없으면 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]에서 해당 클래스 추가하거나 만들어 목록에 추가합니다.  
  
3.  .dbml 파일을 저장합니다.  
  
### DataContext 메서드의 반환 형식을 엔터티 클래스에서 자동으로 생성된 형식으로 다시 변경하려면  
  
1.  메서드 창에서 <xref:System.Data.Linq.DataContext> 메서드를 선택한 다음 삭제합니다.  
  
2.  **서버 탐색기**\/**데이터베이스 탐색기**에서 데이터베이스 개체를 O\/R 디자이너의 빈 영역으로 끌어 옵니다.  
  
3.  .dbml 파일을 저장합니다.  
  
## 참고 항목  
 [O\/R 디자이너\(개체 관계형 디자이너\)](../data-tools/linq-to-sql-tools-in-visual-studio2.md)   
 [LINQ to SQL](../Topic/LINQ%20to%20SQL.md)   
 [DataContext 메서드\(O\/R 디자이너\)](../data-tools/datacontext-methods-o-r-designer.md)   
 [방법: 저장 프로시저 및 함수에 매핑된 DataContext 메서드 만들기\(O\/R 디자이너\)](../data-tools/how-to-create-datacontext-methods-mapped-to-stored-procedures-and-functions-o-r-designer.md)