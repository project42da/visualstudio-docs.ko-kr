---
title: "만들기 및 Tableadapter를 구성 | Microsoft Docs"
ms.custom: 
ms.date: 09/01/2017
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- table adapters, creating
- creating TableAdapters
- data [Visual Studio], creating data components
- data [Visual Studio], TableAdapters
- data [Visual Studio], creating table adapters
ms.assetid: 08630d69-0d6c-4e8f-b42d-2922f45f8415
caps.latest.revision: "28"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.technology: vs-data-tools
ms.workload: data-storage
ms.openlocfilehash: 3c9b501b78a82a94b81b2a29c86fd07a7a0d7f98
ms.sourcegitcommit: 32f1a690fc445f9586d53698fc82c7debd784eeb
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 12/22/2017
---
# <a name="create-and-configure-tableadapters"></a>만들기 및 Tableadapter를 구성 합니다.
Tableadapter 응용 프로그램과 데이터베이스 간에 통신을 제공합니다. 데이터베이스, 실행된 된 쿼리 또는 저장된 프로시저에 연결 하 고 새 데이터를 반환 하거나 테이블 또는 기존 채우기 <xref:System.Data.DataTable> 반환 된 데이터를 사용 합니다. Tableadapter는 데이터베이스에 다시 응용 프로그램에서 업데이트 된 데이터를 보낼 수도 있습니다.  
  
Tableadapter는 다음 작업 중 하나를 수행할 때 사용자에 대 한 생성 됩니다.  
  
-   실행 된 [데이터 소스 구성 마법사](../data-tools/media/data-source-configuration-wizard.png) 중 하나를 선택 하 고는 **데이터베이스** 또는 **웹 서비스** 데이터 원본 유형입니다.  
  
-   데이터베이스 개체를 끌어 **서버 탐색기** 에 **데이터 집합 디자이너**합니다.  
  
새 TableAdapter를 만들 수 있고에 빈 영역을 도구 상자에서 TableAdapter로 끌어서 데이터 원본을 구성 하면는 **데이터 집합 디자이너** 화면입니다.  
  
Tableadapter에 대 한 소개를 참조 하십시오. [Tableadapter를 사용 하 여 데이터 집합을 채울](../data-tools/fill-datasets-by-using-tableadapters.md)합니다.  
  
[!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
## <a name="use-the-tableadapter-configuration-wizard"></a>TableAdapter 구성 마법사를 사용 하 여  
실행 된 **TableAdapter 구성 마법사** 만들거나 Tableadapter 및 관련된 Datatable 편집 합니다. 마우스 오른쪽 단추로 클릭 하 여 기존 TableAdapter를 구성할 수 있습니다는 **데이터 집합 디자이너**합니다.  
  
![테이블 어댑터 구성 마법사 raddata](../data-tools/media/raddata-table-adapter-configuration-wizard.png "raddata 테이블 어댑터 구성 마법사")  
  
도구 상자에서 새 TableAdapter를 끌면 때는 **데이터 집합 디자이너** 이며에 초점을 맞추고 마법사가 시작 표시 되는 TableAdapter를 원본 데이터를 지정할 수 있습니다 메시지에 연결 해야 합니다. 다음 페이지에서 마법사는 SQL 문 또는 저장된 프로시저는 데이터베이스와 통신에 사용할 명령의 종류 요청 합니다. (표시 되지 않습니다이 이미 데이터 원본에 연결 되어 있는 TableAdapter를 구성 하는 경우.)  
  
-   데이터베이스에 대 한 올바른 권한이 있는 경우 기본 데이터베이스에 새 저장된 프로시저를 만드는 하는 옵션이 있습니다. 이러한 사용 권한은 없는 경우 옵션 되지 않습니다.  
  
-   에 대 한 기존 저장된 프로시저를 실행할 수도 있습니다는 **선택**, **삽입**, **업데이트**, 및 **삭제** 명령에는 TableAdapter입니다. 에 할당 된 저장된 프로시저는 **업데이트** 명령, 예를 들어 실행 되는 경우는 `TableAdapter.Update()` 메서드를 호출 합니다.  
  
선택한 저장 프로시저에서 데이터 테이블의 해당 열로 매개 변수를 매핑합니다. 예를 들어, 명명 된 매개 변수를 허용 하는 저장된 프로시저 `@CompanyName` 로 전달 하는 `CompanyName` 테이블의 열이 설정의 **원본 열** 의 `@CompanyName` 매개 변수를 `CompanyName`합니다.  
  
> [!NOTE]
>  SELECT 명령에 할당 된 저장된 프로시저는 TableAdapter의 메서드 이름을 지정 하는 마법사의 다음 단계에서 호출 하 여 실행 됩니다. 기본 방법은 `Fill`이므로 SELECT 프로시저를 실행 하려면 일반적으로 사용 되는 코드는 `TableAdapter.Fill(tableName)`합니다. 기본 이름을 변경 하면 `Fill`, 대체 `Fill` 이름의 할당 하 고이 "TableAdapter" TableAdapter의 실제 이름으로 바꿀 (예를 들어 `CustomersTableAdapter`).  
  
-   선택 하 고 **업데이트를 데이터베이스로 직접 보내는 메서드 만들기** 옵션은 설정에 해당 하는 `GenerateDBDirectMethods` 속성을 true로 합니다. 원래 SQL 문에서 충분 한 정보를 제공 하지 않거나 쿼리가 업데이트할 수 없는 쿼리인 경우에 옵션이 제공 되지 않습니다. 이에 해당할 수 있습니다, 예를 들어 **조인** 쿼리 및 단일 (스칼라) 값을 반환 하는 쿼리 합니다.  
  
**고급 옵션** 마법사를 사용 하도록 설정할 수 있습니다.  
- 에 정의 된 SELECT 문에 기반한 INSERT, UPDATE 및 DELETE 문 생성는 **SQL 문 생성** 페이지
- 낙관적 동시성 사용
- 삽입 후 데이터 테이블을 새로 고칠지 여부를 지정 하 고 UPDATE 문이 실행 된  
  
## <a name="configure-a-tableadapters-fill-method"></a>TableAdapter의 Fill 메서드를 구성 합니다.  
경우에 따라 다음 TableAdapter의 테이블의 스키마를 변경 하는 것이 좋습니다. 이 작업을 수행 하려면 TableAdapter의 기본 수정 `Fill` 메서드. Tableadapter 주를 사용 하 여 만들어진 `Fill` 관련된 데이터 테이블의 스키마를 정의 하는 방법입니다. 주 `Fill` 메서드 기반 쿼리 또는 저장된 프로시저를 TableAdapter를 처음 구성할 때 입력 했던으로 합니다. 이것은 데이터 집합 디자이너에서 데이터 테이블에서 첫 번째 (최상위) 메서드입니다.  
  
![여러 개의 쿼리를 사용 하 여 TableAdapter](../data-tools/media/tableadapter.gif "TableAdapter")  
  
TableAdapter에 수행한 모든 변경 내용을 주 `Fill` 메서드는 연결 된 데이터 테이블의 스키마에 반영 됩니다. 예를 들어 기본에서 쿼리에서 열이 제거 `Fill` 메서드도 연결 된 데이터 테이블에서 열을 제거 합니다. 또한 주에서 열을 제거 `Fill` 메서드 쿼리에서 해당 TableAdapter에 대 한 열을 제거 합니다.  
  
만들고 TableAdapter에 대 한 추가 쿼리를 편집할 TableAdapter 쿼리 구성 마법사를 사용할 수 있습니다. 이러한 추가 쿼리는 스칼라 값을 반환 하지 않는 한 테이블 스키마를 준수 해야 합니다.  각 추가 쿼리에 지정 된 이름이 있습니다.  
 
다음 예에서는 라는 추가 쿼리를 호출 하는 방법을 보여 줍니다. `FillByCity`:  
 
`CustomersTableAdapter.FillByCity(NorthwindDataSet.Customers, "Seattle")`  
  
#### <a name="to-start-the-tableadapter-query-configuration-wizard-with-a-new-query"></a>새 쿼리를 통해 TableAdapter 쿼리 구성 마법사를 시작 하려면  
  
1.  데이터 집합을 열고는 **데이터 집합 디자이너**합니다.  
  
2.  끌어 새 쿼리를 만드는 경우는 **쿼리** 에서 개체는 **데이터 집합** 탭은 **도구 상자** 에 <xref:System.Data.DataTable>, 선택 또는 **쿼리 추가**TableAdapter의 바로 가기 메뉴에서 합니다. 끌 수도 있습니다는 **쿼리** 개체의 빈 영역에는 **데이터 집합 디자이너**, 없이 연결 된 TableAdapter를 만드는 <xref:System.Data.DataTable>합니다. 이러한 쿼리를 실행된 UPDATE, INSERT 또는 단일 (스칼라) 값을 반환 하거나 데이터베이스에 대해 명령을 삭제만 수 있습니다.  
  
3.  에 **데이터 연결 선택** 화면을 선택 하거나 쿼리에 사용 하는 연결을 만듭니다.  
  
    > [!NOTE]
    >  이 화면 디자이너를 사용 하려면 적절 한 연결을 확인할 수 없는 경우 또는 사용할 수 있는 연결이 없는 경우에 나타납니다.  
  
4.  에 **명령 유형을 선택** 화면에서의 데이터베이스에서 데이터를 가져오는 다음 방법 중에서 선택 합니다.  
  
    -   **SQL 문을 사용 하 여** 데이터베이스에서 데이터를 선택 하는 SQL 문을 입력할 수 있습니다.  
  
    -   **새 저장된 프로시저 만들기** 하면 마법사가 새 만들 수 있습니다. 저장 프로시저 (데이터베이스) 지정 된 SELECT 문을 기반 합니다.  
  
    -   **기존 저장된 프로시저를 사용 하 여** 쿼리를 실행 하는 경우 기존 저장된 프로시저를 실행할 수 있습니다.  
  
#### <a name="to-start-the-tableadapter-query-configuration-wizard-on-an-existing-query"></a>기존 쿼리에 TableAdapter 쿼리 구성 마법사를 시작 하려면  
  
-   기존 TableAdapter 쿼리를 편집 하는 쿼리를 마우스 오른쪽 단추로 클릭 한 다음 선택 **구성** 바로 가기 메뉴에서.  
  
    > [!NOTE]
    >  TableAdapter를 재구성 하는 TableAdapter의 주 쿼리를 마우스 오른쪽 단추로 클릭 하 고 <xref:System.Data.DataTable> 스키마입니다. 하지만 선택한 쿼리를 구성 TableAdapter에는 추가 쿼리를 마우스 오른쪽 단추로 클릭 합니다. **TableAdapter 구성 마법사** TableAdapter 쿼리 구성 마법사는 선택한 쿼리를 재구성 하는 동안에 TableAdapter 정의 다시 구성 합니다.  
  
#### <a name="to-add-a-global--query-to-a-tableadapter"></a>전역 쿼리는 TableAdapter를 추가 하려면  
  
-   *전역 쿼리* 는 단일 (스칼라) 값 또는 값을 반환 하는 SQL 쿼리입니다. 일반적으로 전역 함수 삽입, 업데이트, 삭제와 같은 데이터베이스 작업을 수행 합니다. 테이블이 나 특정 순서에 있는 모든 항목에 대 한 총 청구 요금에는 고객 수 같은 정보를 집계할 수도 있습니다.  
  
     전역 쿼리 끌어 추가 **쿼리** 에서 개체는 **데이터 집합** 탭은 **도구 상자** 의 빈 영역에는 **데이터 집합 디자이너**.  
  
-   예를 들어 원하는 작업을 수행 하는 쿼리를 제공 `SELECT COUNT(*) AS CustomerCount FROM Customers`합니다.  
  
    > [!NOTE]
    >  끌어는 **쿼리** 에 직접 드롭하면 개체는 **데이터 집합 디자이너** 스칼라 (단일) 값만 반환 하는 메서드를 만듭니다. 쿼리 또는 저장된 프로시저를 선택 하면 단일 값 보다 더 반환할 수 있습니다, 하는 동안 마법사에 의해 만들어진 메서드만 단일 값을 반환 합니다. 예를 들어 쿼리에서 반환된 된 데이터의 첫 번째 행의 첫 번째 열을 반환할 수 있습니다.

## <a name="see-also"></a>참고 항목
[TableAdapter를 사용하여 데이터 집합 채우기](../data-tools/fill-datasets-by-using-tableadapters.md)