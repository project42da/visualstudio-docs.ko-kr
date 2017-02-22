---
title: "리소스 정보 뷰 - 프로파일러 경합 데이터 | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.performance.view.resourcedetails"
helpviewer_keywords: 
  - "리소스 정보 뷰"
ms.assetid: a4ecfe1c-abbc-4fb3-9ab2-34de50486901
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 리소스 정보 뷰 - 프로파일러 경합 데이터
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

리소스 정보 뷰에서는 선택한 리소스에 대한 경합으로 인해 발생한 차단 이벤트를 시간 표시 그래프로 보여 줍니다.  차단 이벤트는 다른 스레드에서 리소스에 대한 액세스를 잠가 스레드의 실행이 일시 중단되었을 때 발생합니다.  
  
 이 뷰에서는 각 스레드의 실행 시간을 가로 막대로 나타내고 각 차단 이벤트를 스레드 시간 표시 막대 위에 세로 막대로 나타냅니다.  필요한 경우 시간 표시 막대의 한 부분을 확대하여 개별 이벤트를 볼 수 있습니다.  이벤트를 초래한 함수의 실행 경로\(호출 스택\)를 보려면 해당 이벤트 막대를 클릭합니다.  그러면 **호출 스택** 창에 해당 함수가 나타납니다.  함수의 소스 코드를 사용할 수 있는 경우 함수 이름을 클릭하여 [!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)]의 인터페이스에서 소스 파일을 편집할 수 있습니다.  
  
## 절차  
  
#### 시간 표시 막대 세그먼트를 확대하려면  
  
-   시간 표시 막대의 원하는 영역 위로 마우스 포인터를 끕니다.  
  
     마우스 단추를 놓으면 뷰에서 선택한 시간 세그먼트가 확대됩니다.  이 과정을 반복하여 해당 세그먼트를 더 크게 확대할 수 있습니다.  시간 스크롤 막대 위의 스크롤 상자는 뷰에 표시된 시간 세그먼트의 상대 크기를 나타냅니다.  
  
#### 시간 표시 막대를 축소하려면  
  
-   다음 단계 중 하나를 수행합니다.  
  
    -   **축소**를 클릭하여 이전 확대\/축소 수준으로 돌아갑니다.  
  
    -   **확대\/축소 다시 설정**을 클릭하여 뷰의 시간 표시 막대를 모두 표시합니다.  
  
#### 이벤트의 호출 스택을 보려면  
  
-   시간 표시 그래프에서 이벤트 막대를 클릭합니다.  
  
#### 호출 스택에 있는 함수의 소스 코드를 보거나 편집하려면  
  
-   **호출 스택** 창에서 해당 함수 이름을 클릭합니다.  
  
 함수 소스 코드는 현재 프로젝트의 일부여야 합니다.  
  
#### 리소스에 대한 경합 이벤트의 호출 트리를 보려면  
  
-   시간 표시 그래프에서 **합계**를 클릭합니다.  
  
     해당 리소스에 대한 경합 뷰가 나타납니다.  자세한 내용은 [리소스 경합 뷰](../profiling/resource-contentions-view-contention-data.md)을 참조하십시오.  
  
#### 스레드의 모든 경합 이벤트를 보려면  
  
-   시간 표시 그래프에서 스레드의 이름 또는 ID를 클릭합니다.  
  
     선택한 스레드에 대한 스레드 정보 뷰가 나타납니다.  자세한 내용은 [스레드 정보 뷰](../profiling/thread-details-view-contention-data.md)을 참조하십시오.