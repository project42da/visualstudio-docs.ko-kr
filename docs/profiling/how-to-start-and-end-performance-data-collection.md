---
title: "방법: 프로파일링 시작 및 종료 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.performance.wizard.summarypage"
helpviewer_keywords: 
  - "프로파일링 도구, 세션 시작"
  - "성능 세션, 시작"
  - "성능 세션, 종료"
  - "프로파일링 도구, 세션 종료"
ms.assetid: 9f6eb0d5-d9e9-4bec-b627-445065610bce
caps.latest.revision: 12
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 12
---
# 방법: 프로파일링 시작 및 종료
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

프로파일링을 시작하기 전에 프로파일링할 대상 이진 파일을 성능 세션에 추가해야 합니다.  대상을 추가하려면 **성능 탐색기**에서 **대상**을 마우스 오른쪽 단추로 클릭한 다음 **대상 이진 파일 추가**를 클릭합니다.  **대상 이진 파일 추가** 대화 상자에서 파일 이름을 선택한 다음 **열기**를 클릭합니다.  새 이진 파일이 추가됩니다.  
  
### 프로파일링을 시작하려면  
  
1.  **성능 탐색기** 창에서 성능 세션 이름을 마우스 오른쪽 단추로 클릭하고 다음 옵션 중 하나를 선택합니다.  
  
    -   **프로파일링 시작** \- 응용 프로그램을 시작한 다음 즉시 프로파일링을 시작합니다.  
  
    -   **일시 중지된 프로파일링 시작** \- 응용 프로그램을 시작하지만 프로파일링은 시작하지 않습니다.  프로파일링을 시작하려면 **데이터 수집 제어** 창에서 **수집 다시 시작**을 선택해야 합니다.  자세한 내용은 [방법: 프로파일링 일시 중지 및 다시 시작](../Topic/How%20to:%20Pause%20and%20Resume%20Performance%20Data%20Collection.md)을 참조하십시오.  
  
### 프로파일링을 종료하려면  
  
-   프로파일링 세션을 종료할 때는 응용 프로그램을 종료하는 것이 좋습니다.  프로파일링을 즉시 중지하려면 **성능 탐색기** 도구 모음에서 **중지**를 클릭합니다.  
  
## 참고 항목  
 [데이터 수집 제어](../profiling/controlling-data-collection.md)   
 [방법: 프로파일링 일시 중지 및 다시 시작](../Topic/How%20to:%20Pause%20and%20Resume%20Performance%20Data%20Collection.md)