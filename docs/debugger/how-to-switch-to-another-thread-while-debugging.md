---
title: "방법: 디버깅 중 다른 스레드로 전환 | Microsoft Docs"
ms.custom: 
ms.date: 04/27/2017
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
helpviewer_keywords: threads, switching [debugging]
ms.assetid: 5cd76c52-76fa-4fcc-b37e-e9f0ecac0e9e
caps.latest.revision: "26"
author: mikejo5000
ms.author: mikejo
manager: ghogen
ms.workload: multiple
ms.openlocfilehash: 0710bad95484ada62faa042edabf5b76ac459558
ms.sourcegitcommit: 9357209350167e1eb7e50b483e44893735d90589
ms.translationtype: MT
ms.contentlocale: ko-KR
ms.lasthandoff: 01/05/2018
---
# <a name="how-to-switch-to-another-thread-while-debugging-in-visual-studio"></a>방법: Visual Studio에서 디버깅 하는 동안 다른 스레드로 전환
다중 스레드 응용 프로그램을 디버깅할 때는 다른 스레드에 있는 작업 한 스레드에서 전환 하려면 여러 가지 방법 중 하나를 사용할 수 있습니다.

> [!NOTE]
> 스레드 실행 순서를 제어 하려는 경우 해야 [고정 및 스레드를 고정 해제](../debugger/get-started-debugging-multithreaded-apps.md)합니다.

코드 편집기와 여러 가지 다중 스레드 디버깅 창에서 스레드를 검사 하는 경우 노란색 화살표는 현재 스레드를 나타냅니다. 끝이 굽은 녹색 화살표가 비현재 스레드가 현재 디버거 컨텍스트에 있음을 나타냅니다.
  
### <a name="to-switch-to-any-thread-that-appears"></a>나타나는 스레드로 전환 하려면 
  
-   에 **스레드** 또는 **병렬 조사식** 창에서 스레드를 두 번 클릭 합니다.  
  
### <a name="to-switch-to-a-thread-in-a-source-window"></a>소스 창에서 스레드를 전환하려면  
  
-   왼쪽된 여백에서 스레드 마커 아이콘을 마우스 오른쪽 단추로 ![스레드 마커](../debugger/media/dbg-thread-marker.png "ThreadMarker"), 가리킨 **전환할**를 전환 하려면 해당 스레드의 이름을 클릭 하 고 . 특정 위치의 스레드만 바로 가기 메뉴에 표시됩니다.  
  
     없는 스레드 마커 나타나면 마우스 오른쪽 단추로 클릭는 **스레드** 창 확인 **소스의 스레드 표시** 을 선택 합니다.  
  
### <a name="to-switch-to-a-thread-in-the-debug-location-toolbar"></a>디버그 위치 도구 모음에서 스레드로 전환하려면  
  
1.  에 **디버그 위치** 도구 모음에서 클릭 된 **스레드** 목록입니다.  
  
2.  목록에서 전환할 스레드를 클릭합니다.  
  
## <a name="see-also"></a>참고 항목  
 [다중 스레드 응용 프로그램 디버그](../debugger/debug-multithreaded-applications-in-visual-studio.md)
