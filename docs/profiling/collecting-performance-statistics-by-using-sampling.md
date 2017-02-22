---
title: "샘플링을 사용하여 성능 통계 수집 | Microsoft Docs"
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
  - "프로파일링 도구, 샘플링"
  - "샘플링 프로파일링 방법"
ms.assetid: 8e36361b-bb3d-40c6-b286-0e68c0ecb915
caps.latest.revision: 21
caps.handback.revision: 21
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 샘플링을 사용하여 성능 통계 수집
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

기본적으로 [!INCLUDE[vsPreShort](../code-quality/includes/vspreshort_md.md)] 프로파일링 도구의 샘플링 방법은 프로세서 주기 수가 10,000,000개가 될 때마다\(1GHz 컴퓨터에서 약 1\/100초마다\) 프로파일링 정보를 수집하는 방법입니다.  샘플링 방법은 프로세서 사용률 문제를 찾는 데 유용하며 대부분의 성능 확인을 시작하는 데 권장되는 방법입니다.  
  
 **요구 사항**  
  
-   [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)], [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)], [!INCLUDE[vsPro](../code-quality/includes/vspro_md.md)]  
  
> [!NOTE]
>  Windows 8 및 Windows Server 2012의 강화된 보안 기능으로 Visual Studio 프로파일러가 해당 플랫폼에서 데이터를 수집하는 방식에 중요한 변경 사항이 발생합니다.  Windows 스토어 응용 프로그램에는 또한 새 컬렉션 기술이 필요합니다.  [Windows 8 및 Windows Server 2012 응용 프로그램 프로파일링](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md)를 참조하십시오.  
  
 다음 절차 중 하나를 따라 샘플링 방법을 지정할 수 있습니다.  
  
-   프로파일링 마법사의 첫 번째 페이지에서 **CPU 샘플링\(권장\)**을 클릭합니다.  
  
-   **성능 탐색기** 도구 모음의 **방법** 목록에서 **샘플링**을 클릭합니다.  
  
-   성능 세션에 대한 속성 대화 상자의 **일반** 페이지에서 **샘플링**을 클릭합니다.  
  
## 일반 작업  
 성능 세션의 *Performance Session* **속성 페이지** 대화 상자에서는 추가 옵션을 지정할 수 있습니다.  이 대화 상자를 열려면 다음을 수행합니다.  
  
-   **성능 탐색기**에서 성능 세션 이름을 마우스 오른쪽 단추로 클릭한 다음 **속성**을 클릭합니다.  
  
 다음 표에서는 샘플링 방법을 사용하여 프로파일링할 때 *Performance Session* **속성 페이지** 대화 상자에서 지정할 수 있는 옵션과 관련된 작업을 설명합니다.  
  
|Task|관련 내용|  
|----------|-----------|  
|**일반** 페이지에서 .NET 메모리 할당 및 수명 데이터 수집을 추가하고 생성되는 프로파일링 데이터 파일\(.vsp\)에 대한 명명 세부 사항을 지정합니다.|-   [.NET 메모리 할당 및 수명 데이터 수집](../profiling/collecting-dotnet-memory-allocation-and-lifetime-data.md)<br />-   [방법: 프로파일링 데이터 파일 이름 옵션 설정](../profiling/how-to-set-performance-data-file-name-options.md)|  
|**샘플링** 페이지에서 샘플링 주기를 변경하거나, 샘플링 이벤트를 프로세서 클록 주기에서 다른 프로세서 성능 카운터로 변경하거나, 둘 모두를 변경합니다.|-   [방법: 샘플링 이벤트 선택](../Topic/How%20to:%20Choose%20Sampling%20Events.md)|  
|**시작** 페이지에서 코드 솔루션에 여러 개의 .exe 프로젝트가 포함된 경우 시작할 응용 프로그램 및 시작 순서를 지정합니다.|-   [계층 상호 작용 데이터 수집](../profiling/collecting-tier-interaction-data.md)|  
|**계층 상호 작용** 페이지에서 프로파일링 실행 시 수집되는 데이터에 ADO.NET 호출 정보를 추가합니다.|-   [계층 상호 작용 데이터 수집](../profiling/collecting-tier-interaction-data.md)|  
|**Windows 이벤트** 페이지에서 샘플링 데이터와 함께 수집할 ETW\(Windows용 이벤트 추적\) 이벤트를 하나 이상 지정합니다.|-   [방법: ETW\(Windows용 이벤트 추적\) 데이터 수집](../Topic/How%20to:%20Collect%20Event%20Tracing%20for%20Windows%20\(ETW\)%20Data.md)|  
|**Windows 카운터** 페이지에서 프로파일링 데이터에 표시로 추가할 운영 체제 성능 카운터를 하나 이상 지정합니다.|-   [방법: Windows 카운터 데이터 수집](../profiling/how-to-collect-windows-counter-data.md)|  
|**고급** 페이지에서 응용 프로그램 모듈이 여러 버전의 .NET Framework 런타임을 사용할 경우 프로파일링할 버전을 지정합니다.  기본적으로는 첫 번째로 로드되는 버전이 프로파일링됩니다.|-   [방법: 병렬 시나리오에서 프로파일링할 .NET Framework 런타임 지정](../Topic/How%20to:%20Specify%20the%20.NET%20Framework%20Runtime.md)|