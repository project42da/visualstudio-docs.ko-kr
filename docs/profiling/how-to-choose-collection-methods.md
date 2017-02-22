---
title: "방법: 수집 방법 선택 | Microsoft Docs"
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
  - "성능 도구, 수집 방법 선택"
  - "프로파일링 도구, 수집 방법 선택"
  - "성능 컬렉션 메서드"
ms.assetid: c87cfd3a-0fc7-49ae-9c05-d8480891cc63
caps.latest.revision: 34
caps.handback.revision: 34
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# 방법: 수집 방법 선택
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

[!INCLUDE[vsprvs](../code-quality/includes/vsprvs_md.md)] 프로파일링 도구에서는 샘플링, 계측 및 동시성이라는 세 가지 방법으로 성능 데이터를 수집할 수 있습니다.  샘플링 또는 계측 방법을 사용하여 .NET 메모리 할당 및 수명 데이터를 수집할 수도 있습니다.  
  
 **요구 사항**  
  
-   [!INCLUDE[vsUltLong](../code-quality/includes/vsultlong_md.md)], [!INCLUDE[vsPreLong](../code-quality/includes/vsprelong_md.md)], [!INCLUDE[vsPro](../code-quality/includes/vspro_md.md)]  
  
 성능 세션의 **방법** 속성을 사용하여 응용 프로그램에 가장 적합한 수집 방법을 지정할 수 있습니다.  성능 마법사, 성능 탐색기 또는 성능 세션의 속성 페이지에서 수집 방법을 설정할 수 있습니다.  명령줄 도구를 사용하는 경우 자세한 내용은 [명령줄에서 프로파일링](../profiling/using-the-profiling-tools-from-the-command-line.md)을 참조하십시오.  
  
## 성능 마법사  
  
#### 성능 마법사를 사용하여 수집 방법을 선택하려면  
  
-   마법사의 첫 번째 페이지에서 다음 옵션 중 하나를 선택합니다.  
  
|옵션|설명|  
|--------|--------|  
|**CPU 샘플링**|초기 분석과 CPU 사용률 문제를 분석하는 데 유용한 응용 프로그램 통계를 수집합니다.|  
|**계측**|특정 문제에 초점을 맞춘 분석과 입\/출력 성능 문제를 분석하는 데 유용한 자세한 타이밍 데이터를 수집합니다.|  
|**.NET 메모리 할당**|샘플링 프로파일링 방법을 사용하여 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 메모리 할당 데이터를 수집합니다.|  
|**동시성**|리소스 경합 데이터를 수집합니다.|  
  
## 성능 탐색기  
  
#### 성능 탐색기를 사용하여 수집 방법을 선택하려면  
  
1.  **성능 탐색기** 도구 모음에서 **방법** 드롭다운 목록 옆에 있는 화살표를 클릭합니다.  
  
2.  원하는 수집 방법을 클릭합니다.  
  
## 성능 세션 속성 페이지  
  
#### 성능 세션 속성을 사용하여 샘플링 또는 계측 방법을 선택하려면  
  
1.  **성능 탐색기**에서 성능 세션을 선택합니다.  
  
     성능 세션 파일 이름의 확장명은 .psess입니다.  
  
2.  성능 세션을 마우스 오른쪽 단추로 클릭한 다음 **속성**을 클릭합니다.  
  
3.  **속성 페이지**에서 **일반**을 클릭합니다.  
  
4.  원하는 수집 방법을 클릭합니다.  
  
    -   샘플링 데이터를 수집할 때 사용할 수 있는 다른 옵션에 대한 자세한 내용은 [샘플링을 사용하여 성능 통계 수집](../profiling/collecting-performance-statistics-by-using-sampling.md)을 참조하십시오.  
  
    -   계측 데이터를 수집할 때 사용할 수 있는 다른 옵션에 대한 자세한 내용은 [계측을 사용하여 자세한 타이밍 데이터 수집](../profiling/collecting-detailed-timing-data-by-using-instrumentation.md)을 참조하십시오.  
  
#### 성능 세션 속성을 사용하여 .NET 메모리 데이터 수집을 선택하려면  
  
1.  **성능 탐색기**에서 성능 세션을 선택합니다.  
  
     성능 세션 파일 이름의 확장명은 .psess입니다.  
  
2.  성능 세션을 마우스 오른쪽 단추로 클릭한 다음 **속성**을 클릭합니다.  
  
3.  **속성 페이지**에서 **일반**을 클릭합니다.  
  
4.  **샘플링** 또는 **계측**을 클릭합니다.  
  
5.  **.NET 개체 할당 정보 수집**을 클릭하여 [!INCLUDE[dnprdnshort](../code-quality/includes/dnprdnshort_md.md)] 개체 할당의 크기 및 개수를 수집합니다.  
  
6.  \(선택 사항\) **추가적으로 .NET 개체 수명 정보 수집**을 클릭하여 개체 메모리가 회수된 가비지 수집 세대에 대한 데이터를 수집합니다.  
  
     .NET 메모리 데이터를 수집할 때 사용할 수 있는 다른 옵션에 대한 자세한 내용은 [.NET 메모리 할당 및 수명 데이터 수집](../profiling/collecting-dotnet-memory-allocation-and-lifetime-data.md)을 참조하십시오.  
  
#### 성능 세션 속성을 사용하여 동시성 데이터 수집을 선택하려면  
  
1.  **성능 탐색기**에서 성능 세션을 마우스 오른쪽 단추로 클릭한 다음 **속성**을 클릭합니다.  
  
2.  **속성 페이지**에서 **일반**을 클릭합니다.  
  
3.  **동시성**을 클릭합니다.  
  
## 참고 항목  
 [성능 세션 구성](../profiling/configuring-performance-sessions.md)   
 [샘플링 데이터 값 이해](../profiling/understanding-sampling-data-values.md)   
 [성능 세션 속성](../profiling/performance-session-properties.md)