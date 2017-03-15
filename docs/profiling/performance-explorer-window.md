---
title: "성능 탐색기 창 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.performanceexplorer"
  - "vs.performance.explorer"
helpviewer_keywords: 
  - "성능 도구, 성능 탐색기"
ms.assetid: cb6a6efc-93a5-49a2-8d03-6969b5f3b6d7
caps.latest.revision: 20
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 20
---
# 성능 탐색기 창
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] IDE\(통합 개발 환경\)의 **성능 탐색기** 창에서는 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 프로파일링 도구를 사용하여 성능 세션을 구성 및 시작할 수 있습니다.  
  
 **요구 사항**  
  
-   [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)], [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)], [!INCLUDE[vsPro](../code-quality/includes/vspro_md.md)]  
  
## 성능 탐색기 도구 모음  
 다음은 **성능 탐색기** 도구 모음에서 사용할 수 있는 옵션입니다.  
  
-   **성능 마법사 시작** \- 성능 탐색기 창에 새 성능 세션을 추가할 성능 마법사를 표시합니다.  
  
-   **새 성능 세션** \- 성능 탐색기 창에 빈 성능 세션을 추가합니다.  
  
-   **시작** \- **시작** 명령 단추 목록을 사용하면 프로파일링을 즉시 사용하거나\(**프로파일링 시작**\) 프로파일링이 일시 중지된\(**일시 중지된 프로파일링 시작**\) 대상 애플리케이션을 시작할 수 있습니다.  
  
-   **방법** \- 세션의 프로파일링 방법이 샘플링인지 계측인지를 지정합니다.  
  
-   **중지** \- 대상 응용 프로그램과 프로파일러를 즉시 종료합니다.  
  
-   **연결\/분리** \- **프로세스에 프로파일러 연결** 대화 상자를 표시하여 프로파일러를 연결할 실행 중인 프로세스를 선택합니다.  
  
## 성능 탐색기 창  
 **성능 탐색기** 창에는 하나 이상의 성능 세션에 대한 이진 파일 및 보고서 데이터 파일을 표시하는 트리 컨트롤이 들어 있습니다.  
  
-   **세션 이름** \- 트리 컨트롤의 루트에는 세션의 이름이 포함됩니다.  세션 이름을 마우스 오른쪽 단추로 클릭하여 세션 속성을 설정하거나 대상 응용 프로그램 및 프로파일러를 시작합니다.  
  
-   **대상** \- 세션에서 프로파일링할 이진 파일의 이름을 표시합니다.  **대상**을 마우스 오른쪽 단추로 클릭하여 이진 파일, [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 프로젝트 또는 웹 사이트를 추가 또는 제거합니다.  개별 이진 파일의 속성을 설정하려면 대상 이름을 마우스 오른쪽 단추로 클릭합니다.  
  
-   **보고서** \- 세션에 대해 생성되는 프로파일러 데이터 파일의 이름을 표시합니다.  **보고서**를 마우스 오른쪽 단추로 클릭하여 기존 보고서를 추가하거나 두 개의 프로파일러 데이터 파일을 비교합니다.  프로파일러 데이터 파일을 열거나, 제거하거나, 내보내려면 보고서 이름을 마우스 오른쪽 단추로 클릭합니다.  
  
## 참고 항목  
 [개요](../profiling/overviews-performance-tools.md)   
 [성능 세션 구성](../profiling/configuring-performance-sessions.md)   
 [데이터 수집 제어](../profiling/controlling-data-collection.md)