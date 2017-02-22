---
title: "DA0030: 데이터베이스 프로젝트에 대한 계층 상호 작용 측정값 수집 | Microsoft Docs"
ms.custom: ""
ms.date: "12/03/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.performance.DA0030"
  - "vs.performance.rules.DA0030"
  - "vs.performance.30"
ms.assetid: 42b2f69d-0cfa-4854-82c4-589c3d8b4557
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
---
# DA0030: 데이터베이스 프로젝트에 대한 계층 상호 작용 측정값 수집
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|규칙 ID|DA0030|  
|범주|프로파일링 도구 사용|  
|프로파일링 방법|샘플링|  
|메시지|다계층 응용 프로그램의 상호 작용 측정값을 수집하면 데이터베이스 사용 패턴과 주요 데이터 액세스 지연을 파악하는 데 도움이 됩니다.  계층 상호 작용 프로파일링 옵션을 사용하면서 응용 프로그램을 다시 프로파일링해 보십시오.|  
|규칙 유형|정보|  
  
## 원인  
 <xref:System.Data> 메서드에 대한 호출이 프로파일링 데이터의 상당 비율을 차지하며, 프로파일링 실행 시 계층 상호 작용 데이터를 수집하지 않았습니다.  프로파일링을 다시 실행하고 계층 상호 작용 데이터를 추가하는 것이 좋습니다.  
  
## 규칙 설명  
 이 규칙은 <xref:System.Data.Linq> <xref:System.Data.Linq> 등의 System.Data 네임스페이스에 있는 함수에서 상당한 양의 활동이 수행될 때마다 발생합니다.  
  
 다중 계층 응용 프로그램에서는 프레젠테이션 및 데이터 계층에 계층적 서비스를 사용합니다.  데이터 계층은 Microsoft SQL Server와 같은 데이터베이스 관리 시스템을 실행하는 별도의 프로세스인 경우가 많습니다.  데이터 계층은 응용 프로그램의 나머지 계층과는 다른 컴퓨터에서 실행될 수도 있습니다.  샘플링 프로필에서는 out\-of\-process 또는 원격으로 실행되는 함수 및 서비스에 대한 정보를 거의 제공하지 않습니다.  
  
 프로파일링 도구에서는 ADO.NET 서비스에 대한 비동기 호출을 사용하여 Microsoft SQL Server 데이터 계층과 상호 작용하는 다중 계층 응용 프로그램에 대한 타이밍 정보를 수집할 수 있습니다.  단, 계층 상호 작용 프로파일링을 명시적으로 설정해야 합니다.  이 프로파일링은 기본적으로 설정되어 있지 않습니다.  
  
## 위반 문제를 해결하는 방법  
 이 규칙은 단지 정보용이며 수정 작업이 필요하지 않을 수 있습니다.  
  
 Visual Studio IDE에서 프로파일링 데이터에 계층 상호 작용 데이터를 추가하는 방법에 대한 자세한 내용은 [계층 상호 작용 데이터 수집](../profiling/collecting-tier-interaction-data.md)을 참조하십시오.  명령줄에서 계층 상호 작용 데이터를 추가하는 방법에 대한 자세한 내용은 [계층 상호 작용 데이터 수집](../profiling/adding-tier-interaction-data-from-the-command-line.md)를 참조하십시오.