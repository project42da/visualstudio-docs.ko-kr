---
title: "디버거에서 스레드를 보고 | Microsoft Docs"
ms.custom: 
ms.date: 04/25/2017
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vs.debug.threads
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords:
- threading [Visual Studio], debugging
- Thread.Name property
- debugger, Threads window
- SetThreadName function
- Threads window
- '@TIB'
- debugging [Visual Studio], threads
ms.assetid: 590ffd57-0556-43d8-8962-ee27e5b2b7d7
caps.latest.revision: "44"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 64d9eccdf57388428bfcd7ba5e43f75087bcf0bf
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="view-threads-in-the-debugger-in-visual-studio-using-the-threads-window"></a>스레드 창을 사용 하 여 Visual Studio의 디버거에서 스레드 뷰
에 **스레드** 창을 검토 하 고 수 디버깅 중인 응용 프로그램의에서 스레드를 사용 합니다. 사용 하는 방법에 대 한 단계별 지침에 대 한는 **스레드** 창 참조 [연습: 스레드 창 사용 하 여 디버깅](../debugger/how-to-use-the-threads-window.md)합니다.
  
 **스레드** 창에 각 행이 응용 프로그램에서 스레드를 나타내는 테이블이 있습니다. 기본적으로 이 테이블에는 응용 프로그램의 모든 스레드가 나열되지만 목록을 필터링하여 관심 있는 스레드만 표시할 수 있습니다. 열마다 다른 유형의 정보가 있습니다. 일부 열을 숨길 수도 있습니다. 모든 열을 표시하면 왼쪽부터 다음 정보가 나타납니다.  
  
-   플래그 열 - 주의해야 할 스레드에 표시할 수 있습니다. 스레드에 플래그를 지정 하는 방법에 대 한 정보를 참조 하십시오. [하는 방법: 플래그 및 스레드의 플래그 해제](../debugger/how-to-flag-and-unflag-threads.md)합니다.  
  
-   현재 스레드 열-노란색 화살표는 (화살표 개요-현재 스레드에 대 한 현재 디버거 컨텍스트를 나타냄) 현재 스레드를 나타냅니다.
  
-   **ID** 열-각 스레드에 대 한 id 번호를 포함 합니다.  
  
-   **관리 ID** 관리 되는 스레드의 관리 식별 번호가 포함 된 열입니다.  
  
-   **범주** 사용자 인터페이스 스레드, 원격 프로시저 호출 처리기 또는 작업자 스레드로 스레드가 분류 열입니다. 특정 범주는 응용 프로그램의 주 스레드를 식별합니다.  
  
-   **이름** 열, 있는 경우 또는 각 스레드가 이름으로 식별 \<이름 없음 >.  
  
-   **위치** 열-스레드가 실행 되 고 있는 표시 됩니다. 이 위치를 확장하여 스레드의 전체 호출 스택을 표시할 수 있습니다.  
  
-   **우선 순위** 시스템에서 각 스레드에 할당 하는 우선 순위가 포함 된 열입니다.  
  
-   **선호도 마스크** 열 (일반적으로 숨김) 고급 열입니다. 이 열에는 각 스레드에 대한 프로세서 선호도 마스크가 표시됩니다. 다중 프로세서 시스템에서는 선호도 마스크에 따라 스레드가 실행될 수 있는 프로세서가 결정됩니다.  
  
-   **일시 중단 횟수** 일시 중단된 횟수를 포함 하 고 일반적으로 숨겨지는 열 (일반적으로 숨김). 이 횟수에 따라 스레드를 실행할 수 있는지 여부가 결정됩니다. 일시 중단 횟수에 대한 설명은 이 항목의 뒷부분에 나오는 "스레드 중지 및 재개"를 참조하십시오.  
  
-   **프로세스 이름** (일반적으로 숨김) न व ो भ 각 스레드에 속해 있는 프로세스를 포함 합니다. 이 열 여러 프로세스를 디버깅할 때 유용할 수 있습니다.  
  
### <a name="to-display-the-threads-window-in-break-mode-or-run-mode"></a>중단 모드나 실행 모드에서 스레드 창을 표시하려면  
  
-   디버깅 하는 동안 선택 된 **디버그** 메뉴에서 **Windows**, 클릭 하 고 **스레드**합니다.  
  
### <a name="to-display-or-hide-a-column"></a>열을 표시하거나 숨기려면  
  
-   맨 위에 있는 도구 모음에는 **스레드** 창 클릭 **열**다음 선택 하거나 취소를 표시 하거나 숨길 열의 이름입니다.    

## <a name="display-flagged-threads"></a>플래그가 지정 된 스레드 표시  
 스레드를 사용할 때 특히 주의에서 아이콘으로 표시 하 여 제공 하려는 플래그를 설정할 수 있습니다는 **스레드** 창. 자세한 내용은 참조 [하는 방법: 플래그 및 스레드의 플래그 해제](../debugger/how-to-flag-and-unflag-threads.md)합니다. 에 **스레드** 창 모든 스레드 또는 플래그가 지정 된 스레드만 표시 하도록 선택할 수 있습니다.  
  
#### <a name="to-display-only-flagged-threads"></a>플래그가 지정된 스레드만 표시하려면  
  
-   선택 된 **스레드 스레드만 표시** 맨 위에 있는 단추는 **스레드** 창. (흐리게 표시 되 면 해야 먼저 일부 스레드에 플래그를 설정 합니다.) 

## <a name="freeze-and-thaw-threads"></a>고정 및 스레드를 고정 해제  
 스레드를 중지하면 리소스를 사용할 수 있어도 스레드 실행이 시작되지 않습니다.  
  
 네이티브 코드에서 일시 중단 하거나 Windows 함수를 호출 하 여 스레드를 다시 시작할 수 있습니다 `SuspendThread` 및 `ResumeThread` 또는 MFC 함수 [CWinThread::SuspendThread](/cpp/mfc/reference/CWinThread-class.md#cwinthread__suspendthread) 및 [CWinThread::ResumeThread](/cpp/mfc/reference/CWinThread-class.md#cwinthread__resumethread). 호출 하는 경우 `SuspendThread` 또는 `ResumeThread`를 변경 하면는 *일시 중단 횟수*, 표시 되는 **스레드** 창. 그러나 네이티브 스레드를 중지하거나 재개하는 경우에는 일시 중단된 횟수를 변경하지 않습니다. 네이티브 코드에서는 스레드가 재개되고 일시 중단된 횟수가 0인 경우 이외에는 스레드를 실행할 수 없습니다.  
  
 관리 코드에서는 스레드를 중지하거나 재개하면 일시 중단된 횟수가 변경됩니다. 관리 코드에서는 중지된 스레드의 일시 중단된 횟수가 1입니다. 네이티브 코드에서 중지된 스레드의 일시 중단된 횟수는 0입니다. 단, `SuspendThread` 호출로 인해 스레드가 일시 중단된 경우는 예외입니다.  
  
> [!NOTE]
>  네이티브 코드에서 관리 코드로의 호출을 디버깅할 때 관리 코드는 이를 호출한 네이티브 코드와 동일한 실제 스레드에서 실행됩니다. 네이티브 스레드를 일시 중단하거나 중지하면 관리 코드도 중지됩니다.  
  
#### <a name="to-freeze-or-thaw-execution-of-a-thread"></a>스레드 실행을 중지하거나 재개하려면  
  
-   맨 위에 있는 도구 모음에는 **스레드** 창 클릭 **스레드 중지** 또는 **스레드 재개**합니다.  
  
     이 작업에서 선택 된 스레드에만 적용는 **스레드** 창. 

### <a name="switch-to-another-thread"></a>다른 스레드로 전환 

노란색 화살표는 현재 스레드 (및 실행 포인터의 위치)를 나타냅니다. 끝이 굽은 녹색 화살표가 비현재 스레드는 현재 디버거 컨텍스트를 나타냅니다.

#### <a name="to-switch-to-another-thread"></a>다른 스레드로 전환 하려면  
  
-   다음 단계 중 하나를 수행합니다.  
  
    -   스레드를 두 번 클릭합니다.  
  
    -   스레드를 마우스 오른쪽 단추로 클릭 하 고 클릭 **스레드로 전환**합니다.

## <a name="group-and-sort-threads"></a>그룹 및 정렬 스레드  
 스레드를 그룹화하면 테이블에 각 그룹의 제목이 나타납니다. 제목에는 "작업자 스레드" 또는 "플래그가 해제된 스레드" 등의 그룹 설명과 트리 컨트롤이 포함됩니다. 각 그룹의 멤버 스레드가 그룹 제목 아래에 나타납니다. 그룹에 대한 멤버 스레드를 숨기려면 트리 컨트롤을 사용하여 그룹을 축소합니다.  
  
 그룹화가 정렬보다 우선하기 때문에 예를 들어 스레드를 범주별로 그룹화한 다음 각 범주 내의 ID로 정렬할 수 있습니다.  
  
#### <a name="to-sort-threads"></a>스레드를 정렬하려면  
  
1.  맨 위에 있는 도구 모음에는 **스레드** 창 열 맨 위에 있는 단추를 클릭 합니다.  
  
     이제 해당 열의 값으로 스레드가 정렬됩니다.  
  
2.  정렬 순서를 역순으로 바꾸려면 동일한 단추를 다시 클릭합니다.  
  
     목록 맨 위에 나타난 스레드가 이제 맨 아래에 나타납니다.  
  
#### <a name="to-group-threads"></a>스레드를 그룹화하려면  
  
-   에 **스레드** 창 도구 모음을 클릭는 **기준으로 그룹화** 목록 스레드를 그룹화 하려는 조건을 클릭 합니다.  
  
#### <a name="to-sort-threads-within-groups"></a>그룹 내에서 스레드를 정렬하려면  
  
1.  맨 위에 있는 도구 모음에는 **스레드** 창 클릭는 **기준으로 그룹화** 목록 스레드를 그룹화 하려는 조건을 클릭 합니다.  
  
2.  에 **스레드** 창 열 맨 위에 있는 단추를 클릭 합니다.  
  
     이제 해당 열의 값으로 스레드가 정렬됩니다.  
  
#### <a name="to-expand-or-collapse-all-groups"></a>모든 그룹을 확장하거나 축소하려면  
  
-   맨 위에 있는 도구 모음에는 **스레드** 창 클릭 **그룹 확장** 또는 **그룹 축소**합니다.  
  
## <a name="search-for-specific-threads"></a>특정 스레드 검색  
 [!INCLUDE[vs_dev11_long](../data-tools/includes/vs_dev11_long_md.md)]에서 지정된 문자열과 일치하는 스레드를 검색할 수 있습니다. 스레드에 대 한 검색 하는 경우는 **스레드** 창, 창에는 모든 열에 검색 문자열과 일치 하는 모든 스레드가 표시 됩니다. 정보에 있는 호출 스택의 위쪽에 나타나는 스레드 위치가 포함 됩니다는 **위치** 열입니다. 하지만 기본적으로 전체 호출 스택을 검색 되지 않습니다.  
  
#### <a name="to-search-for-specific-threads"></a>특정 스레드를 검색하려면  
  
-   맨 위에 있는 도구 모음에는 **스레드** 창으로 돌아가서는 **검색** 상자:  
  
    -   검색 문자열을 입력하고 Enter 키를 누릅니다.  
  
         \- 또는 -  
  
    -   드롭다운 목록 옆에 클릭는 **검색** 상자 하 고 이전 검색에서 검색 문자열을 선택 합니다.  
  
-   (선택 사항) 전체 호출 스택을 검색에 포함 시키려면 선택 **호출 스택 검색**합니다.   
  
## <a name="display-thread-call-stacks-and-switching-between-frames"></a>스레드 호출 스택 표시 및 프레임 간 전환  
다중 스레드 프로그램에서 각 스레드에는 자신의 고유한 호출 스택이 있습니다. **스레드** 창은 이러한 스택을 볼 수는 편리한 방법을 제공 합니다.

> [!TIP]
> 각 스레드에 대 한 호출 스택 시각적 사용는 [병렬 스택](../debugger/get-started-debugging-multithreaded-apps.md) 창.
  
#### <a name="to-view-the-call-stack-of-a-thread"></a>스레드의 호출 스택을 보려면  
  
-   에 **위치** 열에서 스레드 위치 옆에 있는 역된 삼각형을 클릭 합니다.  
  
     위치가 확장되어 스레드의 전체 호출 스택이 표시됩니다.  
  
#### <a name="to-view-or-collapse-the-call-stacks-of-all-threads"></a>모든 스레드의 호출 스택을 보거나 축소하려면  
  
-   맨 위에 있는 도구 모음에는 **스레드** 창 클릭 **호출 스택 확장** 또는 **호출 스택 축소**합니다.  
  
## <a name="see-also"></a>참고 항목  
 [다중 스레드 응용 프로그램 디버그](../debugger/debug-multithreaded-applications-in-visual-studio.md)   
 [다중 스레드 응용 프로그램 디버깅을 시작](../debugger/get-started-debugging-multithreaded-apps.md)