---
title: "스레드 및 프로세스 동시성 데이터 수집 | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "동시성 프로파일링 방법"
  - "프로파일링 도구, 동시성 방법"
ms.assetid: fa03d381-a9ee-408c-876d-05111e29225b
caps.latest.revision: 14
caps.handback.revision: 14
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 스레드 및 프로세스 동시성 데이터 수집
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 프로 파일링 도구의 동시성 프로 파일링 방법을 사용하면 함수가 프로 파일링된 응용 프로그램 리소스에 대한 액세스를 대기하는 모든 동기화 이벤트에 대한 정보를 포함하는 리소스 경합 데이터를 수집할 수 있습니다.  
  
 **요구 사항**  
  
-   [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)], [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)], [!INCLUDE[vsPro](../code-quality/includes/vspro_md.md)]  
  
 다음 절차 중 하나를 따라 동시성 프로파일링 방법을 지정할 수 있습니다.  
  
-   프로파일링 마법사의 첫번째 페이지에서 **동시성** 을 클릭합니다.  
  
-   성능 세션에 대한 속성 대화 상자의 **일반** 페이지에서 **동시성**을 클릭합니다.  
  
-   **성능 탐색기** 도구 모음의 **방법** 목록에서 **동시성**을 클릭합니다.  
  
## 일반 작업  
 성능 세션의 *Performance Session* **속성 페이지** 대화 상자에서는 추가 옵션을 지정할 수 있습니다.  이 대화 상자를 열려면 다음을 수행합니다.  
  
-   **성능 탐색기**에서 성능 세션 이름을 마우스 오른쪽 단추로 클릭한 다음 **속성**을 클릭합니다.  
  
 다음 표에서는 동시성 방법을 사용하여 프로파일링 할 때 *Performance Session* **속성 페이지** 대화 상자에서 지정할 수 있는 옵션과 관련된 작업을 설명합니다.  
  
|Task|관련 내용|  
|----------|-----------|  
|**일반** 페이지에서 생성된 프로파일링 데이터 파일\(.vsp\)에 대한 명명 세부 사항을 지정합니다.|-   [방법: 프로파일링 데이터 파일 이름 옵션 설정](../profiling/how-to-set-performance-data-file-name-options.md)|  
|**시작** 페이지에서 코드 솔루션에 여러 개의 .exe 프로젝트가 포함된 경우 시작할 응용 프로그램을 지정합니다.|-   [방법: 시작할 이진 파일 지정](../profiling/how-to-specify-the-binary-to-start.md)|  
|**계층 상호 작용** 페이지에서 프로파일링 실행에 ADO.NET 호출 데이터를 추가합니다.|-   [계층 상호 작용 데이터 수집](../profiling/collecting-tier-interaction-data.md)|  
|**Windows 카운터** 페이지에서 프로파일링 데이터에 표시로 추가할 운영 체제 성능 카운터를 하나 이상 지정합니다.|-   [방법: Windows 카운터 데이터 수집](../profiling/how-to-collect-windows-counter-data.md)|  
|**고급** 페이지에서 응용 프로그램 모듈이 여러 버전의 .NET Framework 런타임을 사용할 경우 프로파일링할 버전을 지정합니다.  기본적으로는 첫 번째로 로드되는 버전이 프로파일링됩니다.|-   [방법: 병렬 시나리오에서 프로파일링할 .NET Framework 런타임 지정](../Topic/How%20to:%20Specify%20the%20.NET%20Framework%20Runtime.md)|