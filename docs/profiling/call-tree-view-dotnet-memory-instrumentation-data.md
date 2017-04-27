---
title: "호출 트리 뷰 - 프로파일러 .NET 메모리 계측 데이터 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "호출 트리 뷰"
ms.assetid: dd359707-245a-4a36-8305-2e980b9edd53
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 호출 트리 뷰 - 프로파일러 .NET 메모리 계측 데이터
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

계측 방법을 사용하여 수집된 .NET 메모리 할당 프로파일링 데이터의 호출 트리 뷰에는 프로파일링되는 응용 프로그램에서 이동된 함수 실행 경로가 표시됩니다.  트리의 루트는 응용 프로그램 또는 구성 요소에 대한 진입점입니다.  각 함수 노드에는 해당 함수가 호출한 모든 함수와 해당 함수에 대한 .NET 메모리 및 타이밍 데이터가 나열됩니다.  
  
 호출 트리 뷰의 값은 호출 트리의 부모 함수가 호출한 함수 인스턴스에 대한 값입니다.  백분율 값은 프로파일링 실행 시의 총 할당 수 또는 크기와 해당 함수 인스턴스 값을 비교하여 계산됩니다.  
  
## 실행 부하 과다 경로 강조 표시  
 호출 트리 뷰에서는 가장 큰 메모리 개체나 가장 많은 메모리 개체를 만든 프로세스 또는 함수의 실행 경로를 확장하여 강조 표시할 수 있습니다.  가장 많이 실행되는 경로를 표시하려면 프로세스 또는 함수를 마우스 오른쪽 단추로 클릭하고 **실행 부하 과다 경로 확장**을 클릭합니다.  
  
## 호출 트리 루트 노드 설정  
 프로파일링 실행 시 각 프로세스는 루트 노드로 표시됩니다.  시작 노드로 설정할 노드를 마우스 오른쪽 단추로 클릭한 다음 **루트 설정**을 선택하여 호출 트리 뷰의 시작 노드를 설정할 수 있습니다.  
  
 루트 노드를 설정하면 선택한 노드의 하위 트리를 제외한 다른 모든 항목이 뷰에서 제거됩니다.  호출 트리 뷰 창을 마우스 오른쪽 단추로 클릭하고 **루트 다시 설정**을 선택하여 루트 노드를 보고 있던 노드로 다시 설정할 수 있습니다.  
  
## 일반  
  
|열|설명|  
|-------|--------|  
|**함수 이름**|함수의 이름.|  
|**함수 주소**|함수의 주소입니다.|  
|**함수 줄 번호**|소스 파일에서 이 함수가 시작되는 줄 번호입니다.|  
|**호출 수**|이 함수에 대한 총 호출 수입니다.|  
|**소스 파일**|이 함수의 정의가 포함된 소스 파일입니다.|  
|**모듈 이름**|함수가 포함된 모듈의 이름입니다.|  
|**모듈 경로**|함수가 포함된 모듈의 경로입니다.|  
|**프로세스 ID**|프로파일링 실행의 PID\(프로세스 ID\)입니다.|  
|**프로세스 이름**|프로세스에 할당된 이름입니다.|  
|**시간 제외 프로브 오버헤드**|계측으로 인한 이 함수의 시간 오버헤드입니다.  모든 전용 시간에서 프로브 오버헤드를 뺀 값입니다.|  
|**시간 포괄 프로브 오버헤드**|계측으로 인한 이 함수와 해당 자식 함수의 시간 오버헤드입니다.  모든 포괄 시간에서 프로브 오버헤드를 뺀 값입니다.|  
|**형식**|함수의 컨텍스트입니다.<br /><br /> -   **0** \- 현재 함수<br />-   **1** \- 현재 함수를 호출하는 함수<br />-   **2** \- 현재 함수가 호출하는 함수<br /><br /> [VSPerfReport](../profiling/vsperfreport.md) 명령줄 보고서에서만 표시됩니다.|  
|**루트 함수 이름**|현재 함수의 이름입니다.  [VSPerfReport](../profiling/vsperfreport.md) 명령줄 보고서에서만 표시됩니다.|  
  
## .NET 메모리 값  
 함수의 포함 .NET 메모리 값은 해당 함수와 이 함수가 호출한 함수에 의해 만들어진 개체의 수\(할당\) 및 크기\(바이트\)를 나타냅니다.  
  
 제외 .NET 메모리 값은 해당 함수 본문의 코드\(이 함수가 호출한 함수 제외\)에 의해 만들어진 개체의 수 및 크기를 나타냅니다.  
  
|열|설명|  
|-------|--------|  
|**포괄 할당**|호출 트리의 부모 함수가 호출한 이 함수의 인스턴스에 의해 할당된 개체 수입니다.  여기에는 자식 함수에 의한 할당이 포함됩니다.|  
|**포함 할당 비율\(%\)**|프로파일링 실행 시 만들어진 전체 개체 중 호출 트리의 부모 함수에 의해 호출된 해당 함수 인스턴스의 포함 할당이었던 개체의 백분율입니다.|  
|**제외 할당**|호출 트리의 부모 함수가 호출한 이 함수의 인스턴스에 의해 할당된 개체 수입니다.  여기에는 자식 함수에 의한 할당이 포함되지 않습니다.|  
|**제외 할당 비율\(%\)**|프로파일링 실행 시 만들어진 전체 개체 중 호출 트리의 부모 함수에 의해 호출된 해당 함수 인스턴스의 제외 할당이었던 개체의 백분율입니다.|  
  
## 경과된 포괄 시간 값  
 경과된 포괄 시간 값은 함수가 호출 스택에 있던 시간을 나타냅니다.  이 시간에는 해당 함수에 의해 호출된 자식 함수와 컨텍스트 전환 및 입\/출력 작업 등의 운영 체제 호출에서 소요된 시간이 포함됩니다.  
  
|열|설명|  
|-------|--------|  
|**경과된 포괄 시간**|호출 트리의 부모 함수가 이 함수를 호출했을 때 이 함수에 대한 모든 호출의 총 경과된 포괄 시간입니다.|  
|**경과된 포괄 시간\(%\)**|프로파일링 실행 중 총 경과된 포괄 시간 중 호출 트리의 부모 함수가 이 함수를 호출했을 때 이 함수의 총 경과된 포괄 시간에 소요된 시간의 백분율입니다.|  
|**평균 경과된 포괄 시간**|호출 트리의 부모 함수가 이 함수를 호출했을 때 이 함수에 대한 호출의 평균 경과된 포괄 시간입니다.|  
|**최대 경과된 포괄 시간**|호출 트리의 부모 함수가 이 함수를 호출했을 때 이 함수에 대한 호출의 최대 경과된 포괄 시간입니다.|  
|**최소 경과된 포괄 시간**|호출 트리의 부모 함수가 이 함수를 호출했을 때 이 함수에 대한 호출의 최소 경과된 포괄 시간입니다.|  
  
## 경과된 전용 시간 값  
 경과된 전용 시간 값은 함수가 호출 스택의 맨 위에서 직접 실행 중이던 시간을 나타냅니다.  여기에는 컨텍스트 전환 및 입\/출력 작업 등의 운영 체제 호출에서 소요된 시간이 포함됩니다.  그러나, 이 시간에는 해당 함수에 의해 호출된 함수에서 소요된 시간은 포함되지 않습니다.  
  
|열|설명|  
|-------|--------|  
|**경과된 전용 시간**|호출 트리의 부모 함수가 이 함수를 호출했을 때 이 함수에 대한 모든 호출의 총 경과된 전용 시간입니다.|  
|**경과된 전용 시간\(%\)**|프로파일링 실행 중 총 경과된 전용 시간 중 호출 트리의 부모 함수가 이 함수를 호출했을 때 이 함수의 총 경과된 전용 시간에 소요된 시간의 백분율입니다.|  
|**평균 경과된 전용 시간**|호출 트리의 부모 함수가 이 함수를 호출했을 때 이 함수에 대한 호출의 평균 경과된 전용 시간입니다.|  
|**최대 경과된 전용 시간**|호출 트리의 부모 함수가 이 함수를 호출했을 때 이 함수에 대한 호출의 최대 경과된 전용 시간입니다.|  
|**최소 경과된 전용 시간**|호출 트리의 부모 함수가 이 함수를 호출했을 때 이 함수에 대한 호출의 최소 경과된 전용 시간입니다.|  
  
## 응용 프로그램 포괄 시간 값  
 응용 프로그램 포괄 시간 값은 함수가 호출 스택에 있던 시간을 나타냅니다.  여기에는 컨텍스트 전환 및 입\/출력 작업 등의 운영 체제 호출에서 소요된 시간이 포함되지 않습니다.  여기에는 해당 함수에 의해 호출된 자식 함수에서 소요된 시간은 포함되지 않습니다.  
  
|열|설명|  
|-------|--------|  
|**응용 프로그램 포괄 시간**|호출 트리의 부모 함수가 이 함수를 호출했을 때 이 함수에 대한 모든 호출의 총 응용 프로그램 포괄 시간입니다.|  
|**응용 프로그램 포괄 시간\(%\)**|프로파일링 실행 중 총 경과된 포괄 시간 중 호출 트리의 부모 함수가 이 함수를 호출했을 때 이 함수의 총 응용 프로그램 포괄 시간에 소요된 시간의 백분율입니다.|  
|**평균 응용 프로그램 포괄 시간**|호출 트리의 부모 함수가 이 함수를 호출했을 때 이 함수에 대한 호출의 평균 응용 프로그램 포괄 시간입니다.|  
|**최대 응용 프로그램 포괄 시간**|호출 트리의 부모 함수가 이 함수를 호출했을 때 이 함수에 대한 호출의 최대 응용 프로그램 포괄 시간입니다.|  
|**최소 응용 프로그램 포괄 시간**|호출 트리의 부모 함수가 이 함수를 호출했을 때 이 함수에 대한 호출의 최소 응용 프로그램 포괄 시간입니다.|  
  
## 응용 프로그램 전용 시간 값  
 응용 프로그램 전용 시간 값은 함수에서 호출하여 자식 함수에서 소요된 시간을 제외하고 해당 함수에서 소요된 시간을 나타냅니다.  시간은 컨텍스트 전환 및 입\/출력 작업 등의 운영 체제에 대한 호출도 제외합니다.  
  
|열|설명|  
|-------|--------|  
|**응용 프로그램 전용 시간**|호출 트리의 부모 함수가 이 함수를 호출했을 때 이 함수에 대한 모든 호출의 총 응용 프로그램 전용 시간입니다.|  
|**응용 프로그램 전용 시간\(%\)**|프로파일링 실행 중 총 경과된 전용 시간 중 호출 트리의 부모 함수가 이 함수를 호출했을 때 이 함수의 총 응용 프로그램 전용 시간에 소요된 시간의 백분율입니다.|  
|**평균 응용 프로그램 전용 시간**|호출 트리의 부모 함수가 이 함수를 호출했을 때 이 함수에 대한 호출의 평균 응용 프로그램 전용 시간입니다.|  
|**최대 응용 프로그램 전용 시간**|호출 트리의 부모 함수가 이 함수를 호출했을 때 이 함수에 대한 호출의 최대 응용 프로그램 전용 시간입니다.|  
|**최소 응용 프로그램 전용 시간**|호출 트리의 부모 함수가 이 함수를 호출했을 때 이 함수에 대한 호출의 최소 응용 프로그램 전용 시간입니다.|