---
title: "방법: O R 디자이너에서 생성 된 코드 확장 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: d6d1122e-2f55-4607-8d8b-48c3c22600fb
caps.latest.revision: "3"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.openlocfilehash: cc60c4fe5ff014b1088509c8e5c4982bf7f4322a
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-extend-code-generated-by-the-or-designer"></a>방법: O/R 디자이너에서 생성된 코드 확장
[!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]에서 생성한 코드는 디자이너 화면에서 엔터티 클래스 및 다른 개체를 변경하면 다시 생성됩니다. 이러한 코드의 다시 생성으로 인해 일반적으로 디자이너에서 코드를 다시 생성하면 생성된 코드에 추가한 모든 코드를 덮어씁니다. [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]에서는 덮어쓸 수 없는 코드를 추가할 수 있는 partial 클래스 파일을 생성할 수 있는 기능을 제공합니다. 사용자 고유의 코드를 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]에서 생성한 코드에 추가하는 예는 데이터 유효성 검사를 LINQ to SQL(엔터티) 클래스에 추가하는 것입니다. 자세한 내용은 참조 [하는 방법: 엔터티 클래스에 유효성 검사 추가](../data-tools/how-to-add-validation-to-entity-classes.md)합니다.  
  
[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
## <a name="adding-code-to-an-entity-class"></a>엔터티 클래스에 코드 추가  
  
#### <a name="to-create-a-partial-class-and-add-code-to-an-entity-class"></a>Partial 클래스를 만들고 엔터티 클래스에 코드를 추가하려면  
  
1.  열거나 새 LINQ to SQL 클래스 파일을 만듭니다 (**.dbml** 파일)에 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]합니다. (두 번 클릭 하 고 **.dbml** 파일을 **솔루션 탐색기**/**데이터베이스 탐색기**.)  
  
2.  에 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)], 유효성 검사를 추가 하 고 클릭 한 다음 클래스를 마우스 오른쪽 단추로 클릭 **코드 보기**합니다.  
  
     선택한 엔터티 클래스의 partial 클래스와 함께 코드 편집기가 열립니다.  
  
3.  엔터티 클래스의 partial 클래스 선언에 사용자 코드를 추가합니다.  
  
## <a name="adding-code-to-a-datacontext"></a>DataContext에 코드 추가  
  
#### <a name="to-create-a-partial-class-and-add-code-to-a-datacontext"></a>Partial 클래스를 만들고 DataContext에 코드를 추가하려면  
  
1.  열거나 새 LINQ to SQL 클래스 파일을 만듭니다 (**.dbml** 파일)에 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]합니다. (두 번 클릭 하 고 **.dbml** 파일을 **솔루션 탐색기**/**데이터베이스 탐색기**.)  
  
2.  에 [!INCLUDE[vs_ordesigner_short](../data-tools/includes/vs_ordesigner_short_md.md)]디자이너의 빈 영역을 마우스 오른쪽 단추로 클릭 한 다음 클릭 **코드 보기**합니다.  
  
     DataContext의 partial 클래스와 함께 코드 편집기가 열립니다.  
  
3.  DataContext의 partial 클래스 선언에 사용자 코드를 추가합니다.  
  
## <a name="see-also"></a>참고 항목  
 [LINQ to SQL 도구 Visual Studio에서](../data-tools/linq-to-sql-tools-in-visual-studio2.md)   
 [연습: LINQ to SQL 클래스 (O R 디자이너) 만들기](how-to-create-linq-to-sql-classes-mapped-to-tables-and-views-o-r-designer.md)   
 [LINQ to SQL](/dotnet/framework/data/adonet/sql/linq/index)   
 