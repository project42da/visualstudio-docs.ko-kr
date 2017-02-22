---
title: "호출 트리 뷰 - 프로파일러 샘플링 데이터 | Microsoft Docs"
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
  - "샘플링 프로파일링 방법, 호출 트리 뷰"
  - "호출 트리 뷰"
ms.assetid: 5c4e8ec3-d0d3-485a-93bd-9060df4eb739
caps.latest.revision: 16
caps.handback.revision: 16
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 호출 트리 뷰 - 프로파일러 샘플링 데이터
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

호출 트리 뷰에는 프로파일링된 응용 프로그램에서 이동한 함수 실행 경로가 표시됩니다.  
  
> [!NOTE]
>  Windows 8 및 Windows Server 2012의 강화된 보안 기능으로 Visual Studio 프로파일러가 해당 플랫폼에서 데이터를 수집하는 방식에 중요한 변경 사항이 발생합니다.  Windows 스토어 응용 프로그램에는 또한 새 컬렉션 기술이 필요합니다.  [Windows 8 및 Windows Server 2012 응용 프로그램 프로파일링](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md)를 참조하십시오.  
  
 트리의 루트는 응용 프로그램 또는 구성 요소에 대한 진입점입니다.  각 함수 노드에는 호출한 모든 함수 및 이러한 함수 호출에 대한 성능 데이터가 나열됩니다.  
  
 호출 트리 뷰의 값은 호출 트리의 부모 함수가 호출한 함수 인스턴스에 대한 값입니다.  백분율 값은 프로파일링 실행 시 수집된 총 샘플 수와 해당 함수 인스턴스 값을 비교하여 계산됩니다.  
  
## 실행 부하 과다 경로 강조 표시  
 호출 트리 뷰에서는 가장 자주 샘플링된 프로세스 또는 함수의 실행 경로를 확장하여 강조 표시할 수 있습니다.  가장 많이 실행되는 경로를 표시하려면 프로세스 또는 함수를 마우스 오른쪽 단추로 클릭하고 **실행 부하 과다 경로 확장**을 클릭합니다.  
  
## 호출 트리 루트 노드 설정  
 프로파일링 실행 시 각 프로세스는 루트 노드로 표시됩니다.  호출 트리 뷰의 시작 노드를 설정하려면 시작 노드로 설정할 노드를 마우스 오른쪽 단추로 클릭하고 **루트 설정**을 선택합니다.  
  
 루트 노드를 설정하면 선택한 노드의 하위 트리를 제외한 다른 모든 항목이 뷰에서 제거됩니다.  루트 노드를 원래 노드로 다시 설정하려면 호출 트리 뷰 창을 마우스 오른쪽 단추로 클릭하고 **루트 다시 설정**을 선택합니다.  
  
|열|설명|  
|-------|--------|  
|**프로세스 ID**|프로파일링 실행의 PID\(프로세스 ID\)입니다.|  
|**프로세스 이름**|프로세스의 이름입니다.|  
|**모듈 이름**|함수가 포함된 모듈의 이름입니다.|  
|**모듈 경로**|함수가 포함된 모듈의 경로입니다.|  
|**소스 파일**|이 함수의 정의가 포함된 소스 파일입니다.|  
|**함수 이름**|함수의 정규화된 이름입니다.|  
|**함수 줄 번호**|소스 파일에서 이 함수가 시작되는 줄 번호입니다.|  
|**함수 주소**|함수의 주소입니다.|  
|**수준**|호출 트리에서 해당 함수의 깊이입니다.  [VSPerfReport](../profiling/vsperfreport.md) 명령줄 보고서에서만 표시됩니다.|  
|**제외 샘플**|이 함수가 호출 트리의 부모 함수에 의해 호출되었을 때 이 함수에서 수집된 샘플 수입니다.  여기에는 해당 함수가 호출한 함수에서 수집된 샘플이 포함되지 않습니다.|  
|**전용 샘플 비율\(%\)**|프로파일링 실행 시 수집된 전체 샘플 중 이 함수가 호출 트리의 부모 함수에 의해 호출되었을 때 수집된 이 함수의 전용 샘플의 백분율입니다.|  
|**포괄 샘플**|이 함수가 호출 트리의 부모 함수에 의해 호출되었을 때 이 함수에서 수집된 샘플 수입니다.  여기에는 해당 함수가 호출한 함수에서 수집된 샘플이 포함됩니다.|  
|**포괄 샘플 비율\(%\)**|프로파일링 실행 시 수집된 전체 샘플 중 이 함수가 호출 트리의 부모 함수에 의해 호출되었을 때 수집된 이 함수의 포괄 샘플의 백분율입니다.|  
  
## 참고 항목  
 [방법: 보고서 뷰 열 사용자 지정](../profiling/how-to-customize-report-view-columns.md)   
 [Call Tree View \- Profiler Sampling Data](../profiling/call-tree-view-sampling-data.md)   
 [호출 트리 뷰 \- 샘플링](../profiling/call-tree-view-dotnet-memory-sampling-data.md)   
 [호출 트리 뷰 \- 계측](../profiling/call-tree-view-dotnet-memory-instrumentation-data.md)   
 [호출 트리 뷰](../profiling/call-tree-view-instrumentation-data.md)