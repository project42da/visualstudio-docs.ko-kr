---
title: "GPU 스레드 디버거에서 보기 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- vs.debug.gputthreads
- vs.debug.gputhreads
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords: debugger, GPU threads window
ms.assetid: c647c502-a9f0-48e0-a430-976744a5fa51
caps.latest.revision: "13"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: 23bb4ee4550f70681152fc14cc66a642597125ad
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-use-the-gpu-threads-window"></a>방법: GPU 스레드 창 사용
GPU 스레드 창에서 디버깅 중인 응용 프로그램의 GPU에서 실행되는 스레드를 검사하고 관련 작업을 수행할 수 있습니다. GPU에서 실행 되는 응용 프로그램에 대 한 자세한 내용은 참조 [c + + AMP 개요](/cpp/parallel/amp/cpp-amp-overview)합니다.  
  
 GPU 스레드 창에는 각 행이 모든 열에서 값이 동일한 GPU 스레드의 집합을 나타내는 테이블이 포함되어 있습니다. 열에 있는 항목의 정렬, 순서 변경, 제거 및 그룹화를 수행할 수 있습니다. GPU 스레드 창에서 스레드에 플래그를 지정하거나 해제할 수 있으며 스레드를 중지(일시 중단)하거나 재개(다시 시작)할 수 있습니다. 다음과 같은 열이 GPU 스레드 창에 표시됩니다.  
  
-   특히 주의할 스레드를 표시할 수 있는 플래그 열  
  
-   현재 스레드 열-노란색 화살표는 현재 스레드를 나타냅니다.  
  
-   **스레드 수가** 열-동일한 위치에 스레드 수를 표시 합니다.  
  
-   **줄** 열-각 스레드 그룹이 위치한 코드 줄을 표시 합니다.  
  
-   **주소** 열-각 스레드 그룹이 위치한 명령 주소를 표시 합니다. 기본적으로 이 열은 숨겨집니다.  
  
-   **위치** 소스 코드의 위치를 나타내는 열입니다.  
  
-   **상태** 열-스레드가 활성화, 차단, 시작 안 됨 또는 완료 여부를 표시 합니다.  
  
-   **타일** 열 행의 스레드에 대 한 타일 인덱스를 표시 합니다.  
  
 테이블의 머리글은 표시되고 있는 타일과 스레드를 보여 줍니다.  
  
 [!INCLUDE[note_settings_general](../data-tools/includes/note_settings_general_md.md)]  
  
### <a name="to-display-the-gpu-threads-window"></a>GPU 스레드 창을 표시하려면  
  
1.  **솔루션 탐색기**에서 프로젝트의 바로 가기 메뉴를 열고 **속성**을 선택합니다.  
  
2.  에 **속성 페이지** 프로젝트에 대 한 창에서 **구성 속성**, 선택 **디버깅**합니다.  
  
3.  에 **실행할 디버거** 목록에서 **로컬 Windows 디버거**합니다. 에 **디버거 형식** 목록에서 **GPU 전용**합니다. GPU에서 실행되는 코드의 중단점에서 중단하려면 이 디버거를 선택해야 합니다.  
  
4.  **확인** 단추를 선택합니다.  
  
5.  GPU 코드에서 중단점을 설정합니다.  
  
6.  메뉴 모음에서 **디버그**, **디버깅 시작**합니다. 응용 프로그램이 중단점에 도달할 때까지 기다립니다.  
  
7.  메뉴 모음을 하나 선택 **디버그**, **Windows**, **GPU 스레드**합니다.  
  
### <a name="to-switch-to-a-different-thread"></a>다른 스레드로 전환 하려면  
  
-   열을 두 번 클릭합니다. 키보드에서는 행을 선택하고 Enter 키를 선택합니다.  
  
### <a name="to-display-a-particular-tile-and-thread"></a>특정 타일 및 스레드를 표시하려면  
  
1.  선택 된 **스레드 전환기 확장** GPU 스레드 창에서 단추입니다.  
  
2.  텍스트 상자에 타일 및 스레드 값을 입력합니다.  
  
3.  위에 화살표가 있는 단추를 선택합니다.  
  
### <a name="to-display-or-hide-a-column"></a>열을 표시하거나 숨기려면  
  
-   GPU 스레드 창에 대 한 바로 가기 메뉴를 열고 **열**을 표시 하거나 숨길 열을 선택 합니다.  
  
### <a name="to-sort-by-a-column"></a>열을 기준으로 정렬하려면  
  
-   열 머리글을 선택합니다.  
  
### <a name="to-group-threads"></a>스레드를 그룹화하려면  
  
-   GPU 스레드 창에 대 한 바로 가기 메뉴를 열고 **Group By**, 표시 된 열 이름 중 하나를 선택 합니다. 선택 **None** 스레드 그룹을 해제 합니다.  
  
### <a name="to-freeze-or-thaw-a-row-of-threads"></a>스레드의 행을 중지하거나 재개하려면  
  
-   행에 대 한 바로 가기 메뉴를 열고 **고정** 또는 **재개**합니다.  
  
### <a name="to-flag-or-unflag-a-row-of-threads"></a>스레드의 행에 플래그를 지정하거나 해제하려면  
  
-   스레드에 대 한 플래그 열을 선택 하거나 스레드에 대 한 바로 가기 메뉴를 열고 선택한 **플래그** 또는 **플래그 해제**합니다.  
  
### <a name="to-display-only-flagged-threads"></a>플래그가 지정된 스레드만 표시하려면  
  
-   GPU 스레드 창에서 플래그 단추를 선택합니다.  
  
## <a name="see-also"></a>참고 항목  
 [다중 스레드 응용 프로그램 디버그](../debugger/debug-multithreaded-applications-in-visual-studio.md)   
 [방법: 병렬 조사식 창 사용](../debugger/how-to-use-the-parallel-watch-window.md)   
 [연습: C++ AMP 응용 프로그램 디버깅](/cpp/parallel/amp/walkthrough-debugging-a-cpp-amp-application)