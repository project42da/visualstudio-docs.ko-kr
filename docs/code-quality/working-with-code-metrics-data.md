---
title: "코드 메트릭 데이터 작업 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-code-analysis
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.codemetrics.output
helpviewer_keywords:
- code metrics results
- code metrics results window
- results window, code metrics
ms.assetid: 988193ec-b4a3-4e11-b5a1-7334979807d5
caps.latest.revision: "17"
author: gewarren
ms.author: gewarren
manager: ghogen
ms.openlocfilehash: 39d45f5d43819dc418b6378d34a19e6af1d8ee12
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="working-with-code-metrics-data"></a>코드 메트릭 데이터 작업
**코드 메트릭 결과** 코드 메트릭 분석에 의해 생성 되는 데이터 창에 표시 됩니다. 코드 메트릭 데이터 값에 대 한 자세한 내용은 참조 [코드 메트릭 값](../code-quality/code-metrics-values.md)합니다.  
  
 이 항목에는 다음과 같은 단원이 포함되어 있습니다.  
  
-   [Code Metrics Results Window](../code-quality/working-with-code-metrics-data.md#BKMK_CodeMetricsResultsWindow)  
  
-   [코드 메트릭 결과 표시](../code-quality/working-with-code-metrics-data.md#BKMK_DisplayingCodeMetricsResults)  
  
-   [코드 메트릭 결과 필터링](../code-quality/working-with-code-metrics-data.md#BKMK_FilteringCodeMetricsResults)  
  
-   [추가, 제거 및 데이터 열을 다시 정렬](../code-quality/working-with-code-metrics-data.md#BKMK_AddingRemovingandRearrangingDataColumns)  
  
-   [클립보드 또는 Excel로 데이터를 복사합니다.](../code-quality/working-with-code-metrics-data.md#BKMK_Copying_Data_to_the_Clipboard_or_Excel)  
  
-   [코드 메트릭 결과에 따라 작업 항목 만들기](../code-quality/working-with-code-metrics-data.md#BKMK_Creating_a_Work_Item_Based_on_Code_Metric_Results)  
  
##  <a name="BKMK_CodeMetricsResultsWindow"></a> Code Metrics Results Window  
 **코드 메트릭 결과** 창 위쪽 및 계산된 된 결과 표시 하는 열에 있는 도구 모음에 있습니다.  
  
|열|설명|  
|------------|-----------------|  
|**계층 구조**|**계층** 열에는 코드 계층 표시할 항목을 트리 뷰가 있습니다. 나머지 열은 계산된 결과 보여 줍니다. 원하는 대로 결과 열을 배치 하거나 숨길 수 있습니다.|  
|**유지 관리**|**유지 관리 용이성** 열에 숫자 결과 외에도 아이콘이 포함 되어 있습니다. 녹색 아이콘은 상대적으로 높은 수준의 유지 관리 용이성을 나타냅니다. 노란색 아이콘의 편의성이 보통임을 나타냅니다. 빨간색 아이콘 낮은 유지 관리 하 고 잠재적인 문제 지점을 나타냅니다. 이러한 색 표시기 AvoidUnmaintainableCode FxCop 규칙에서 사용 되는 심각도 범주에 해당 합니다. 이 규칙은 유지 관리 인덱스 경고 인덱스가 있는 경우 10 및 20, 및 오류 아니고 경고 사이의 인덱스 20 보다 높은 경우 10 보다 작으면 오류가 발생 합니다. 유지 관리 인덱스는 3 개 메트릭은의 합성: 순환 복잡성, 줄의 코드와 복잡 한 계산 합니다. 해당 값은 단위로 표시 되지 않습니다.|  
  
##  <a name="BKMK_DisplayingCodeMetricsResults"></a>코드 메트릭 결과 표시  
 코드 메트릭 결과 창 코드 메트릭 결과 생성할 때 자동으로 표시 됩니다. 또한 언제 든 지 창을 표시할 수 있습니다.  
  
#### <a name="to-display-the-code-metrics-results-window"></a>코드 메트릭 결과 창을 표시 하려면  
  
-   에 **분석** 메뉴를 클릭 하 여 **Windows** 클릭 하 고 **코드 메트릭 결과**합니다.  
  
     \- 또는 -  
  
-   에 **보기** 메뉴에서 **다른 창** 클릭 하 고 **코드 메트릭 결과**합니다.  
  
     코드 메트릭 결과 창에는 결과 포함 하는 경우에 표시 됩니다.  
  
#### <a name="to-view-code-metrics-details"></a>코드 메트릭 세부 정보를 보려면  
  
-   코드 메트릭 결과 생성 된 경우에서 트리를 확장 된 **계층** 열입니다.  
  
##  <a name="BKMK_FilteringCodeMetricsResults"></a>코드 메트릭 결과 필터링  
 에 표시 되는 결과 필터링 할 수 있습니다는 **코드 메트릭 결과** 맨 위에 있는 도구 모음을 사용 하 여 창. 예를 들어 다음 65 아래 유지 관리 인덱스가 결과만 하는 것이 좋습니다.  
  
 **필터** 드롭다운 목록 상자에 결과 열 이름이 포함 되어 있습니다. 필터가 정의 된 들여쓰기 된 목록 맨 아래에 추가 됩니다. 목록 정의 된 마지막 10 개의 필터를 포함할 수 있습니다.  
  
#### <a name="to-filter-the-code-metrics-results"></a>코드 메트릭 결과 필터링 하려면  
  
1.  **필터** 목록에서 열 이름을 선택 합니다.  
  
2.  **Min**를 표시할 최소 값을 입력 합니다.  
  
3.  **최대**를 표시할 최대 값을 입력 합니다.  
  
4.  클릭는 **필터 적용** 단추입니다.  
  
5.  결과 정보를 보려면 계층 구조 트리를 확장 합니다.  
  
##  <a name="BKMK_AddingRemovingandRearrangingDataColumns"></a>추가, 제거 및 데이터 열을 다시 정렬  
 추가 하거나 제거 결과의 열은 **코드 메트릭 결과** 창. 또한 원하는 순서로 표시 되도록 결과 열을 다시 정렬할 수 있습니다.  
  
#### <a name="to-remove-a-column"></a>열 제거 하려면  
  
1.  클릭는 **열 추가/제거** 단추입니다.  
  
     \- 또는 -  
  
     열 머리글을 마우스 오른쪽 단추로 누른 **열 추가/제거**합니다.  
  
2.  에 **열 추가/제거** 대화 상자에서 확인란의 선택을 취소는 열에 대 한 제거 하 고 클릭 하려는 **확인**합니다.  
  
#### <a name="to-add-a-previously-removed-column"></a>이전에 제거한 열을 추가 하려면  
  
1.  클릭는 **열 추가/제거** 단추입니다.  
  
     \- 또는 -  
  
     열 머리글을 마우스 오른쪽 단추로 누른 **열 추가/제거**합니다.  
  
2.  에 **열 추가/제거** 대화 상자에서 추가 하 고 클릭 하려는 열에 대 한 확인란을 선택 **확인**합니다.  
  
#### <a name="to-rearrange-columns"></a>열 다시 정렬 하려면  
  
1.  클릭는 **열 추가/제거** 단추입니다.  
  
     \- 또는 -  
  
     열 머리글을 마우스 오른쪽 단추로 누른 **열 추가/제거**합니다.  
  
2.  에 **열 추가/제거** 대화 상자를 이동한 다음 위쪽 화살표 또는 아래쪽 화살표를 클릭 하려는 열을 선택 합니다.  
  
3.  열 원하는 위치에 배치 됩니다을 클릭 하 여 **확인**합니다.  
  
##  <a name="BKMK_Copying_Data_to_the_Clipboard_or_Excel"></a>클립보드 또는 Excel로 데이터를 복사합니다.  
 선택한 이름 및 각 데이터 열의 값에 대 한 한 줄을 포함 하는 텍스트 문자열로 코드 메트릭 데이터의 선택 된 행을 클립보드로 복사 합니다. 클릭할 수도 있습니다 **Microsoft Excel에서 목록 열기** 코드 메트릭 결과의 모든 Excel 스프레드시트를 내보내려면  
  
##  <a name="BKMK_Creating_a_Work_Item_Based_on_Code_Metric_Results"></a>코드 메트릭 결과에 따라 작업 항목 만들기  
 만들 수는 [!INCLUDE[esprfound](../code-quality/includes/esprfound_md.md)] 기반으로 하는 작업 항목으로 인해는 **코드 메트릭 결과** 창. 작업 항목을 만들 때 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 에 제목을 자동으로 입력 된 **제목** 필드 코드 메트릭 데이터는 **기록** 탭 합니다.  
  
 작업 항목을 만드는 방법에 대 한 자세한 내용은 참조 [만들기 작업 항목 &#91; redirected &#93;](http://msdn.microsoft.com/en-us/24b2e064-16ac-4bf0-8de4-98a1f48b8c4b)합니다.  
  
#### <a name="to-create-a-work-item-based-on-a-result"></a>결과에 따라 작업 항목을 만들려면  
  
1.  결과 마우스 오른쪽 단추로 클릭 합니다.  
  
2.  가리킨 **작업 항목 만들기**를 가리킨 다음 만들려는 작업 항목의 유형을 클릭 하 고 (**버그**, **작업**, 등).  
  
3.  모든 필수 필드에 입력 하 여 작업 항목 폼을 완료 합니다.  
  
4.  에 **파일** 메뉴를 클릭 하 여 **모두 저장** 작업 항목을 저장 합니다.  
  
#### <a name="to-create-a-bug-based-on-a-result"></a>결과에 따라 버그를 만들려면  
  
1.  선택 결과 클릭 합니다.  
  
2.  클릭는 **작업 항목 만들기** 단추입니다.  
  
3.  모든 필수 필드에 입력 하 여 작업 항목 폼을 완료 합니다.  
  
4.  에 **파일** 메뉴를 클릭 하 여 **모두 저장** 작업 항목을 저장 합니다.  
  
## <a name="see-also"></a>참고 항목  
 [복잡성 및 관리 코드의 유지 관리 용이성 측정](../code-quality/measuring-complexity-and-maintainability-of-managed-code.md)   
 [방법: 코드 메트릭 데이터 생성](../code-quality/how-to-generate-code-metrics-data.md)