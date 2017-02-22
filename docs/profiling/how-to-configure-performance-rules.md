---
title: "방법: 프로파일링 도구 성능 규칙 구성 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.performance.ruleseditor"
ms.assetid: a148b468-b849-4858-880a-808a6b47e596
caps.latest.revision: 14
caps.handback.revision: 14
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 방법: 프로파일링 도구 성능 규칙 구성
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

Visual Studio 프로파일링 도구의 성능 경고는 프로파일링된 응용 프로그램에서 프로그램 실행 속도를 저하시킬 수 있는 문제를 나타냅니다.  또한 경고는 보다 유용한 데이터를 수집하도록 수집 방법을 변경해야 할 수 있음을 나타내기도 합니다.  성능 경고는 프로파일링 세션에서 자동으로 생성되며 [!INCLUDE[vs_current_short](../code-quality/includes/vs_current_short_md.md)] 에서 프로파일링 데이터 파일을 열 때 **오류 목록** 창에 표시됩니다.  현재 관심을 두고 있는 시나리오에 해당되지 않는 경고나 부정확하게 발생하는 경고도 있을 수 있습니다.  이런 경우 특정 경고를 표시하거나 숨기도록 성능 경고를 구성할 수 있습니다.  
  
### 프로파일러 성능 경고를 구성하려면  
  
1.  **도구** 메뉴에서 **옵션**을 클릭합니다.  
  
2.  **성능 도구**를 확장하고 **규칙**을 클릭합니다.  
  
3.  경고를 사용하거나 사용하지 않도록 설정하려면 경고 **ID** 또는 이름 옆의 확인란을 선택하거나 선택 취소합니다.  
  
4.  규칙의 경고 수준을 지정하려면 규칙 옆의 **동작** 셀을 클릭한 다음 경고 수준을 클릭합니다.  
  
    -   **사용 안 함** \- 규칙을 사용하지 않습니다. 규칙 ID 옆의 확인란을 선택 취소하는 것과 같은 기능을 합니다.  
  
    -   **경고** \- 규칙을 경고로 표시합니다.  
  
    -   **오류** \- 프로파일링 실행을 중지하고 규칙을 오류로 표시합니다.  
  
    -   **정보** \- 규칙을 정보용으로만 표시합니다.