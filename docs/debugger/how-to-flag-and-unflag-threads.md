---
title: "방법: 플래그 지정 및 스레드의 플래그를 해제 | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: vs-ide-debug
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- CSharp
- VB
- FSharp
- C++
helpviewer_keywords: treads, switching [debugging]
ms.assetid: 952d579d-6911-413e-b3e5-54e7e797e70c
caps.latest.revision: "33"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.openlocfilehash: d4ff3c0d06d7f668ad3d61f785320def8b9ddd0e
ms.sourcegitcommit: f40311056ea0b4677efcca74a285dbb0ce0e7974
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 10/31/2017
---
# <a name="how-to-flag-and-unflag-threads"></a>방법: 스레드에 플래그 지정 및 스레드의 플래그 해제
스레드를 사용할 때 특히 주의에서 아이콘으로 표시 하 여 제공 하려는 플래그를 설정할 수 있습니다는 **스레드**, **병렬 스택** (스레드 뷰) **병렬 조사식**, 및  **GPU 스레드** windows 합니다. 이 아이콘은 플래그 설정된 스레드를 다른 스레드와 구분하는 데 도움이 됩니다.  
  
플래그가 지정 된 스레드에서 특수 처리가 발생 하기도 **스레드** 목록에 **디버그 위치** 도구 모음 및 다른 다중 스레드 디버깅 창에서. 모든 스레드나 플래그에 플래그가 지정 된 스레드만 표시할 수 있습니다는 **스레드** 목록 또는 다른 창에서.
  
### <a name="to-flag-or-unflag-a-thread"></a>스레드에 플래그를 지정하거나 해제하려면 
  
-   에 **스레드** 또는 **병렬 조사식** 창에서 원하는 스레드를 찾아를 선택 하거나 플래그 지우기 플래그 아이콘을 클릭 합니다. 
-   에 **병렬 스택** 창, 스레드 또는 스레드를 선택 하는 그룹에 오른쪽 클릭 **플래그 / <thread>**  또는 **플래그 해제 / <thread>** 합니다.
  
### <a name="to-unflag-all-threads"></a>모든 스레드의 플래그를 해제하려면  
  
-   에 **스레드** 창에서 스레드를 마우스 오른쪽 단추로 클릭 하 고 클릭 **모든 스레드 플래그 해제**합니다.
-   에 **병렬 조사식** 창에서 플래그가 지정 된 모든 스레드, 한 다음 마우스 오른쪽 단추로 클릭 하 고 선택 **플래그 해제**합니다.  
  
### <a name="to-display-only-flagged-threads"></a>플래그가 지정된 스레드만 표시하려면  
  
-   선택 된 **스레드 스레드만 표시** 다중 스레드 디버깅 창 중 하나에 단추입니다.  
  
### <a name="to-flag-just-my-code"></a>내 코드만 플래그를 설정하려면  
  
1.  맨 위에 있는 도구 모음에서는 **스레드** 창에서 플래그 아이콘을 클릭 합니다.  
  
2.  드롭다운 목록에서 클릭 **내 코드만 플래그**합니다.  
  
### <a name="to-flag-threads-that-are-associated-with-selected-modules"></a>선택한 모듈과 연결된 스레드에 플래그를 설정하려면  
  
1.  도구 모음에서 **스레드** 창에서 플래그 아이콘을 클릭 합니다.  
  
2.  드롭다운 목록에서 클릭 **사용자 지정 모듈 선택 영역 플래그 지정**합니다.  
  
3.  에 **모듈 선택** 대화 상자에서 원하는 모듈을 선택 합니다.  
  
4.  (선택 사항) 에 **검색** 특정 모듈에 대 한 검색할 문자열을 입력 합니다.  
  
5.  **확인**을 클릭합니다.  
  
## <a name="see-also"></a>참고 항목  
 [다중 스레드 응용 프로그램 디버그](../debugger/debug-multithreaded-applications-in-visual-studio.md)   
 [다중 스레드 응용 프로그램 디버깅을 시작](../debugger/get-started-debugging-multithreaded-apps.md)  
 [연습: 스레드 창 사용 하는 다중 스레드 응용 프로그램 디버깅](../debugger/how-to-use-the-threads-window.md)