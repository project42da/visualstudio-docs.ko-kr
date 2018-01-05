---
title: "매개 변수가 있는 TableAdapter 쿼리 만들기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- VB
- CSharp
helpviewer_keywords:
- data [Visual Studio], TableAdapters
- TableAdapters, parameterized queries
- data [Visual Studio], searching data
- queries [Visual Studio], creating
- TableAdapters, searching data
- queries [Visual Studio], TableAdapters
ms.assetid: 104d1d19-b5a9-4071-b81e-1b3af08e9c7b
caps.latest.revision: "20"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.workload: data-storage
ms.openlocfilehash: 65c4ab52ead981d54cf9b0c64c7a3c1c941de5b0
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="create-parameterized-tableadapter-queries"></a>매개 변수가 있는 TableAdapter 쿼리 만들기
매개 변수가 있는 쿼리는 쿼리의 WHERE 절 조건을 충족하는 데이터를 반환합니다. 예를 들어 고객 목록을 반환하는 SQL 문 끝에 `WHERE City = @City`를 추가하여 특정 구/군/시의 고객만 표시하도록 고객 목록을 매개 변수화할 수 있습니다.  
  
 매개 변수가 있는 TableAdapter 쿼리를 만들는 **데이터 집합 디자이너**합니다. Windows 응용 프로그램에서 만들 수 있습니다는 **데이터 소스 매개 변수화** 명령을 **데이터** 메뉴. **데이터 소스 매개 변수화** 명령 매개 변수 값을 입력 하 고 쿼리를 실행할 수 있는 폼에 컨트롤을 만듭니다.  
  
> [!NOTE]
>  매개 변수가 있는 쿼리를 생성할 때는 대 한 코딩 하는 데이터베이스에 관련 된 매개 변수 표기법을 사용 합니다. 예를 들어 Access 및 OleDb 데이터 소스는 물음표 '?'를 사용하여 매개 변수를 표기하므로 WHERE 절은 `WHERE City = ?`와 같습니다.  
  
> [!NOTE]
>  대화 상자와 메뉴 명령은 활성 설정 또는 사용 중인 버전에 따라 도움말에서 설명 하는 것에서 달라질 수 있습니다. 설정을 변경 하려면로 이동 된 **도구** 메뉴와 선택 **설정 가져오기 및 내보내기**합니다. 자세한 내용은 [Visual Studio IDE 개인 설정](../ide/personalizing-the-visual-studio-ide.md)을 참조하세요.  
  
## <a name="create-a-parameterized-tableadapter-query"></a>매개 변수가 있는 TableAdapter 쿼리 만들기  
  
#### <a name="to-create-a-parameterized-query-in-the-dataset-designer"></a>데이터 집합 디자이너에서 매개 변수가 있는 쿼리를 만들려면  
  
-   원하는 매개 변수가 포함된 WHERE 절을 SQL 문에 추가하여 새 TableAdapter를 만듭니다. 자세한 내용은 참조 [만들기 및 Tableadapter를 구성](../data-tools/create-and-configure-tableadapters.md)합니다.  
  
     또는  
  
-   원하는 매개 변수가 포함된 WHERE 절을 SQL 문에 추가하여 기존 TableAdapter에 쿼리를 추가합니다.
  
#### <a name="to-create-a-parameterized-query-while-designing-a-data-bound-form"></a>데이터 바인딩된 폼을 디자인하면서 매개 변수가 있는 쿼리를 만들려면  
  
1.  데이터 집합에 이미 바인딩되어 있는 폼의 컨트롤을 선택합니다. 자세한 내용은 참조 [Visual Studio에서 데이터를 바인딩할 Windows Forms 컨트롤](../data-tools/bind-windows-forms-controls-to-data-in-visual-studio.md)합니다.  
  
2.  에 **데이터** 메뉴 선택 **쿼리 추가**합니다.  
  
3.  완료 된 **검색 조건 작성기** 을 SQL 문에 필요한 매개 변수는 WHERE 절 추가 대화 상자를 합니다.  
  
### <a name="to-add-a-query-to-an-existing-data-bound-form"></a>기존 데이터 바인딩된 폼에 쿼리를 추가하려면  
  
1.  양식을 엽니다는 **Windows Forms 디자이너**합니다.  
  
2.  에 **데이터** 메뉴 선택 **쿼리 추가** 또는 **데이터 스마트 태그**합니다.  
  
    > [!NOTE]
    >  경우 **쿼리 추가** 에서 사용할 수 없으면는 **데이터** 메뉴에서 매개 변수화를 추가 하는 데이터 소스가 표시 하면 양식의 컨트롤에 지정 합니다. 예를 들어 폼의 <xref:System.Windows.Forms.DataGridView> 컨트롤에 데이터가 표시되는 경우 해당 컨트롤을 선택합니다. 폼의 개별 컨트롤에 데이터가 표시되는 경우에는 데이터 바인딩된 컨트롤을 선택합니다.  
  
3.  에 **선택 데이터 소스 테이블** 영역에서 추가 매개 변수화를 하려면 원하는 테이블을 선택 합니다.  
  
4.  에 이름을 입력 된 **새 쿼리 이름** 새 쿼리를 만드는 경우 상자입니다.  
  
     또는  
  
     쿼리를 선택는 **기존 쿼리 이름** 상자입니다.  
  
5.  에 **쿼리 텍스트** 매개 변수를 사용 하는 쿼리를 입력 합니다.  
  
6.  **확인**을 선택합니다.  
  
     매개 변수를 입력 하는 컨트롤 및 **부하** 단추에 폼에 추가 됩니다 한 <xref:System.Windows.Forms.ToolStrip> 제어 합니다.  
  
#### <a name="querying-for-null-values"></a>Null 값에 대 한 쿼리  
TableAdapter 매개 변수 값이 없는 현재 레코드를 쿼리 하려는 경우 null 값 할당할 수 있습니다. 예를 들어 포함 된 다음 쿼리에 `ShippedDate` 매개 변수에서 해당 `WHERE` 절:  
  
 ```sql
SELECT CustomerID, OrderDate, ShippedDate  
FROM Orders  
WHERE (ShippedDate = @ShippedDate) OR (ShippedDate IS NULL)
```  
  
 TableAdapter에 대 한 쿼리 인 경우를 다음 코드로 배송 되지 않은 모든 주문에 대해 쿼리할 수 있습니다.  
  
 [!code-csharp[VbRaddataTableAdapters#8](../data-tools/codesnippet/CSharp/create-parameterized-tableadapter-queries_1.cs)]
 [!code-vb[VbRaddataTableAdapters#8](../data-tools/codesnippet/VisualBasic/create-parameterized-tableadapter-queries_1.vb)]  

 Null 값을 허용 하는 쿼리를 사용할 수 있도록 합니다.

1.  에 **데이터 집합 디자이너**, null 매개 변수 값을 허용 하는 TableAdapter 쿼리를 선택 합니다.  
  
2.  에 **속성** 창에서 **매개 변수**, 다음 줄임표 (**...** ) 버튼을 클릭은 **매개 변수 컬렉션 편집기**합니다.  
  
3.  Null 값을 허용 하는 매개 변수를 선택 하 고 설정 된 **AllowDbNull** 속성을 `true`합니다.  
  
## <a name="see-also"></a>참고 항목  
 [TableAdapter를 사용하여 데이터 집합 채우기](../data-tools/fill-datasets-by-using-tableadapters.md)