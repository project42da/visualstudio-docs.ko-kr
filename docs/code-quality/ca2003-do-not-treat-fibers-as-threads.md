---
title: "CA2003: 파이버를 스레드로 취급하지 마십시오. | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "vs-devops-test"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CA2003"
  - "DoNotTreatFibersAsThreads"
helpviewer_keywords: 
  - "CA2003"
  - "DoNotTreatFibersAsThreads"
ms.assetid: 15398fb1-f384-4bcc-ad93-00e1c0fa9ddf
caps.latest.revision: 16
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
caps.handback.revision: 16
---
# CA2003: 파이버를 스레드로 취급하지 마십시오.
[!INCLUDE[vs2017banner](../code-quality/includes/vs2017banner.md)]

|||  
|-|-|  
|TypeName|DoNotTreatFibersAsThreads|  
|CheckId|CA2003|  
|범주|Microsoft.Reliability|  
|변경 수준|주요 변경 아님|  
  
## 원인  
 관리되는 스레드가 Win32 스레드처럼 취급됩니다.  
  
## 규칙 설명  
 관리되는 스레드가 Win32 스레드로 가정하지 않음  파이버입니다.  CLR\(공용 언어 런타임\)은 관리되는 스레드를 SQL이 소유한 실제 스레드의 컨텍스트에서 파이버로 실행합니다.  이러한 스레드는 AppDomains 전체에서 공유되며 SQL Server 프로세스의 데이터베이스에서도 공유될 수 있습니다.  관리되는 스레드의 로컬 저장소를 사용하면 이러한 문제를 해결할 수 있지만, 관리되지 않는 스레드의 로컬 저장소를 사용할 수 없거나 코드가 현재 OS 스레드에서 다시 실행된다고 간주할 수 없습니다.  스레드 로캘과 같은 설정은 변경하지 마십시오.  CreateCriticalSection 또는 CreateMutex는 잠금 상태로 들어간 스레드를 해제하도록 요구하므로 P\/Invoke를 통해 CreateCriticalSection 또는 CreateMutex를 호출하지 마십시오.  이것은 파이버를 사용하는 경우에는 문제가 되지 않으므로 Win32 임계 영역 및 뮤텍스는 SQL에서 쓸모 없게 됩니다.  관리되는 System.Thread 개체에 대한 대부분의 상태를 안전하게 사용할 수 있습니다.  여기에는 관리되는 스레드 로컬 저장소 및 스레드의 현재 사용자 인터페이스\(UI\) 문화권이 포함되어 있습니다.  하지만 프로그래밍 모델로 인해 SQL을 사용할 때는 스레드의 현재 문화권을 변경할 수 없습니다. 이 내용은 새로운 권한을 통해 적용됩니다.  
  
## 위반 문제를 해결하는 방법  
 스레드의 사용을 검사하여 그에 따라 코드를 변경합니다.  
  
## 경고를 표시하지 않는 경우  
 이 규칙에서는 경고를 표시해야 합니다.