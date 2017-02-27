---
title: "Visual Studio IDE를 사용하여 계층 상호 작용 데이터 수집 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-ide-debug"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vs.performance.property.tierinteraction"
helpviewer_keywords: 
  - "프로파일링 도구, ADO.NET 프로파일링"
  - "계층 상호 작용 프로파일링 방법"
  - "프로파일링 도구, 계층 상호 작용 방법"
  - "ADO.NET 성능 프로파일링"
ms.assetid: 47a944c2-3098-497c-8fc7-e1f43d750bbc
caps.latest.revision: 13
author: "mikejo5000"
ms.author: "mikejo"
manager: "ghogen"
caps.handback.revision: 13
---
# Visual Studio IDE를 사용하여 계층 상호 작용 데이터 수집
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

계층 상호 작용 프로파일링에서는 ADO.NET 서비스를 통해 데이터베이스와 통신하는 다중 계층 응용 프로그램의 함수 실행 시간에 대한 추가 정보를 제공합니다.  동기 함수 호출에 대한 데이터만 수집됩니다.  
  
 **Visual Studio 버전**  
  
 Visual Studio Ultimate, Visual Studio Premium 또는 Visual Studio Professional을 사용하여 계층 상호 작용 프로 파일링 데이터를 수집할 수 있습니다.  그러나 VS Ultimate 및 VS Premium 에서만 계층 상호 작용 프로 파일링 데이터를 볼 수 있습니다.  
  
 **Windows 8 및 Windows Server 2012**  
  
 Windows 8 데스크톱 응용 프로그램 및 Windows Server 2012 응용 프로그램 계층 상호 작용 데이터를 수집 하려면 계측 방법을 사용 해야 합니다.  Windows 스토어 응용 프로그램에 대한 계층 상호 작용 데이터는 수집할 수 없습니다.  [Windows 8 및 Windows Server 2012 응용 프로그램 프로파일링](../profiling/performance-tools-on-windows-8-and-windows-server-2012-applications.md)를 참조하십시오.  다른 지원 되는 버전의 Windows에서 모든 프로 파일링 방법에 계층 상호 작용 데이터를 포함할 수 있습니다.  
  
 **성능 마법사**  
  
 성능 마법사의 버그 때문에, 성능 탐색기에서 프로 파일링을 실행하기 위해 계층 상호 작용 데이터 수집 옵션을 더해야 합니다.  또한 성능 탐색창의 대상 노드에 웹 사이트나 실행 파일, 또는 프로젝트를 반드시 추가해야 합니다  
  
### 성능 세션 속성 페이지를 사용하여 프로파일링 데이터에 계층 상호 작용을 추가하려면  
  
1.  성능 탐색기에서, 상황에 맞는 메뉴에서 **속성** 을 선택합니다.  
  
2.  **계층 상호 작용** 페이지를 선택하고 **계층 상호작용 프로파일링 사용** 확인란을 선택합니다.  
  
3.  성능 탐색기에서, **대상** 노드를 선택한 다음 프로젝트, 실행 파일, 또는 프로 파일링 할 웹 사이트를 지정 합니다.  
  
## 참고 항목  
 [계층 상호 작용 뷰](../profiling/tier-interactions-view.md)